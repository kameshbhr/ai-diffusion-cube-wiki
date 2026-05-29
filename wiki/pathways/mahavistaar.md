# MahaVistaar — Pathway

**Deployment:** MahaVistaar Agricultural Advisory System
**Contributor:** Commissioner of Agriculture, Government of Maharashtra / EkStep Foundation
**Sector:** Agriculture
**Geography:** Maharashtra, India
**Actor type:** Government
**Journey stage:** Scaling
**Dimensions covered:** A, B, C, D, E, F
**Horizontal or vertical:** Vertical (sector-specific)
**Deployment status:** Active
**Last updated:** 2026-05-28
**Contact for peer connection:** EkStep Foundation — [ekstep.org](https://ekstep.org)

## Summary

MahaVistaar is an AI-powered agricultural advisory system deployed by the Commissioner of Agriculture, Government of Maharashtra, serving Maharashtra's 1.5 crore farmers through voice telephony, smartphone app, WhatsApp, and web. Delivered in nine months from inception to live system, the deployment answered 1.67 million questions from 342,000+ unique users and generates 17 lakh daily proactive alerts. As the anchor deployment of the OpenAgriNet (OAN) digital public goods architecture, this pathway documents how a state government can take an AI advisory system from pilot to scale, the cost dynamics of migrating from commercial to self-hosted LLM serving, and the ecosystem design required to sustain a system answering 440,000+ queries per month.

---

## A — Problem Orientation

*What you build on.*

**Who were you trying to serve, and what specific problem were you solving for them?**
The deployment targets Maharashtra's 1.5 crore farmers, the majority of whom are smallholders with limited access to timely, personalised agricultural advice. Farmers face decisions — pest management, optimal sowing windows, scheme eligibility, mandi price movements — that change week to week, but the extension officer network cannot deliver timely, individualised advice at that cadence or scale.

**What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?**
Farmers communicate in Marathi, Hindi, Bhili, and English; many have low digital literacy and limited smartphone access. The system was built voice-first, delivered over standard telephony via short code 155313, but extended to smartphone app, WhatsApp, and web to serve users with varying device access. Bhashini ASR/TTS components handle spoken input and output across all four languages, enabling use without text literacy in the primary channels.

**Was there data already available to start with, or did you have to build or collect it first?**
The deployment drew on existing institutional data — state agricultural databases, ICAR knowledge repositories, weather service feeds, and mandi price data. A federated architecture was adopted: the AI connects to data where it lives at query time rather than copying it into a central store. This avoided the institutional and compliance cost of data migration while enabling real-time answers.

**Why did this problem need AI — what would a non-AI solution have missed?**
The extension officer network in Maharashtra cannot deliver personalised advice to 1.5 crore farmers at the cadence required. A non-AI solution faces a hard ceiling at the number of human officers available. AI enables the system to handle thousands of concurrent voice calls, generate personalised answers from multiple real-time data sources, and shift from reactive query-answering to proactive advisory — sending outbound pest alerts or weather warnings to farmers in affected geographies before they call in.

**What would a harmful or wrong AI output look like in your context — and how did that shape what you built?**
A wrong pesticide recommendation could lead to crop failure or direct health risk from misapplication. Incorrect scheme eligibility information could cause a farmer to miss an entitlement. Inaccurate mandi pricing at the point of sale affects a farmer's bargaining position in a transaction they cannot repeat that day. A voice-delivered answer through a government short code carries implicit institutional authority — farmers are more likely to act on it without cross-checking than they would on a text result from a generic web search. This elevated harm potential shaped two architectural decisions: deploying an independent moderation model (GPT-OSS Safeguard 20B) that cannot be compromised by the same prompt injection affecting the primary model, and requiring that answers be traceable to named source databases so the moderation layer can verify claims before delivery.

**Did your understanding of the problem change after you started — and if so, how?**
The deployment evolved from a reactive query system (farmers call in with questions) toward a proactive advisory model (system pushes relevant alerts to farmers based on their location and crops). This shift was enabled by integrating crop registry and location data that was not part of the original design.

**Is there anything about your users you assumed early on that turned out to be wrong?**
Not documented.

---

## B — Architecture

*What you build with.*

**Did users interact through voice, an app, or something else — and what drove that choice?**
Users interact through four channels: voice telephony (short code 155313), smartphone app, WhatsApp, and web. The voice channel was the primary design driver — voice over basic telephony reaches farmers regardless of smartphone ownership, data plan availability, or digital literacy, and was non-negotiable for inclusion. Multi-channel delivery was added to serve the broader population with varying levels of device access. The interface layer transcribes speech (Bhashini ASR), processes the query through the AI decision engine, and returns a spoken response (Bhashini TTS) in Marathi, Hindi, Bhili, or English.

**Did you bring data together into one place or connect to it where it lived — and why?**
Data remains federated — the AI connects to data sources (agricultural databases, weather feeds, mandi prices, pest alerts) at query time rather than copying them into a central repository. This approach preserves data sovereignty for institutional data owners and avoids the institutional cost and compliance risk of centralised data migration. The trade-off is query latency, which is managed through caching of high-frequency data.

**What did you build yourself versus use something that already existed?**
Built: the OAN DPG layer (reusable across future deployments), the fine-tuned Qwen3.5-27B agricultural advisory model, the 7-layer system architecture, and the deployment-specific configuration for Maharashtra (crops, schemes, language). Used existing: Bhashini ASR/TTS (AI4Bharat), Karya voice data, ICAR knowledge repositories, Beckn protocol for ecosystem interoperability, and the state agriculture department's data infrastructure.

**How did you avoid being locked into a single vendor?**
The architecture explicitly separates the DPG layer (reusable, open-source code) from the deployment instance (Maharashtra-specific configuration). The LLM serving stack migrated off Azure GPT-4.1 (commercial API) to self-hosted fine-tuned Qwen3.5-27B on 4×H100 GPUs running vLLM with tensor parallelism (TP=4), reducing per-query LLM cost from ₹9.4 to ₹0.05. This migration demonstrates that the architecture does not require a commercial LLM API. The Beckn protocol ensures ecosystem interoperability without locking into any single partner's standards.

**Did any data source or system integration turn out to be harder than expected?**
Weather station coverage presented a gap: some locations lacked nearby monitoring stations, requiring the system to expand search radii to find the nearest available data point. This introduced a latency and accuracy trade-off for weather queries in those areas, managed through a tiered search strategy with a defined radius limit.

**What was your design policy for handling peak load — did you queue requests or route to fallback instantly, and why?**
The system routes instantly to Azure OpenAI as a fallback when self-hosted concurrency reaches 100 simultaneous calls — it never queues requests. The design principle is latency over queue depth: a farmer who calls and experiences silence or a long wait is more likely to hang up and distrust the system than one routed immediately to a backup that answers in comparable time. The 100-call threshold is stored in an environment variable, tunable via Langfuse without redeployment.

**What infrastructure constraint did you hit that you didn't anticipate, and how did you resolve it?**
The binding constraint was concurrency, not latency. The 27B FP16 model requires approximately 54GB for weights, leaving roughly 26GB for KV cache on a single H100 (80GB) — enough for approximately 12 concurrent requests before quality degrades. Tensor parallelism at TP=4 pools KV cache across four GPUs to approximately 260GB, supporting 80–100 concurrent requests. The 8-GPU node divides as: 4 GPUs for the main LLM (TP=4), 2 for the moderation model, and 2 idle — because TP must operate in powers of two, TP=2 is insufficient for the 27B model, and TP=8 is the natural next step when additional concurrent capacity is required.

**Did the AI ever give a wrong or harmful answer to a user — and how did you catch and handle it?**
The deployment uses a dual-model architecture: the primary Qwen3.5-27B advisory model and an independent GPT-OSS Safeguard 20B moderation model that evaluates every output before it reaches the user. The safeguard model operates independently — it cannot be influenced by the same prompt injection that might affect the primary model. If the safeguard flags a response, it is blocked before delivery.

**What did you put in place to prevent the AI from causing harm — and was it ever tested?**
The independent safeguard model (GPT-OSS Safeguard 20B) runs on every response. A 6,000-token system prompt encodes advisory guardrails, including escalation paths for situations where the AI should direct the farmer to a human officer rather than attempt an answer. Prefix caching caches this system prompt — 37% of notional input compute is skipped — so safeguard evaluation does not add proportional cost per query. The moderation model was evaluated against adversarial test sets of 500 attack patterns covering prompt injection, hallucination triggers, and jailbreak attempts. Whether formal red-team adversarial testing beyond these pattern sets has been conducted is not documented.

### Additional Insights

The 7-layer system architecture — user, interface, moderation, AI decision engine, knowledge and scientific models, live data and institutional sources, DPI foundation — functions as a reusable design template across OAN deployments. Each layer has a defined responsibility boundary; this separation allowed the Amul Sarlaben deployment to reuse the architecture in three weeks by substituting cooperative-specific configuration at the interface and data layers without rebuilding the moderation or decision engine layers. The fine-tuned Qwen3.5-27B achieved 94% accuracy on agricultural advisory benchmarks against 91% for larger commercial models, demonstrating that fine-tuning a smaller open-weight model on domain data can outperform larger general-purpose commercial models while operating at 188× lower per-query LLM cost.

---

## C — Institution

*Who deploys AI.*

**How did you get the deployment approved and funded — and did you position it as a one-time project or a long-term transformation initiative?**
The deployment is positioned as a long-term transformation of the extension delivery system — not a pilot project. The Agri Secretary nomination as institutional sponsor was the first decision taken — preceding any technology choices — establishing that the deployment would be anchored in government authority rather than treated as a time-limited technology experiment. From that decision, the deployment reached a live system in nine months. Gates Foundation, World Bank, and UNDP are named as funders in ecosystem documentation; the specific approval pathway and budget allocation mechanism are not documented.

**Was there internal resistance — and if so, what actually changed minds?**
Not documented.

**Did you need multiple departments or agencies to cooperate — and where did that get difficult?**
The deployment requires cooperation across the state agriculture department, the extension directorate, data-owning departments (weather, mandi, land records), and knowledge institutions. The state agriculture department held data in a system the extension directorate could not access; resolving this required a joint secretary-level meeting that took time to convene before the federated data architecture could be operationalised.

**Did procurement rules create a barrier — and if so how did you get through them?**
Not documented.

**When something went wrong, who was accountable — and was that clear from the start?**
Not documented.

**What happens to this deployment if the key person driving it moves to a different role?**
Not documented.

**Was there a leadership or political change during the deployment, and how did it affect things?**
Not documented.

### Additional Insights

The decision to name an Agri Secretary as institutional sponsor before any technology choices were made is recorded as the first decision in the deployment — not a technical or data decision, but an institutional anchoring decision. This sequencing — institution first, technology second — is cited in cross-deployment analysis as a factor that enabled the nine-month delivery timeline by preventing the deployment from stalling at data-access or procurement barriers that require senior political cover to unblock. For a next adopter, identifying and securing a named government sponsor before scoping any technology is the inference this deployment supports.

---

## D — Ecosystem

*Who executes.*

**How many organisations had to work together for this to function?**
The OAN source document maps 54 named enablers across four layers: institutional (government departments, Commissioner of Agriculture), technology (EkStep Foundation, AI4Bharat/Bhashini, Karya, compute infrastructure), data (state agricultural databases, ICAR, weather services, mandi price systems), and knowledge (domain experts, agricultural scientists). A minimum of 25+ organisations need to be operationally active for the system to function at full capability. Named funders include Gates Foundation, World Bank, and UNDP.

**Who was ultimately responsible for keeping all of them aligned — and what did that role actually involve?**
EkStep Foundation holds the network orchestrator role. In practice this involves maintaining the OAN DPG layer so all deployments can reuse it, coordinating the technology partner ecosystem (Bhashini, Karya, compute providers), and supporting the government deployer in the institutional coordination required to access federated data sources.

**Did any partner relationship not work out as expected — what happened and how did you handle it?**
Not documented.

**How was trust maintained across partners — especially when something went wrong?**
Not documented.

---

## E — Workforce

*Who absorbs AI.*

**Were there people — field workers, extension officers, call centre staff — whose job changed because of this deployment?**
The deployment interacts with the existing extension officer hierarchy: Krishi Sahayaks (village-level), Block Officers (BOs), Sub-Divisional Officers (SDOs), District Officers (DOs), Subject Matter Specialists (SMS), and ATMA (Agricultural Technology Management Agency) staff. The AI system handles routine queries that would previously have required a farmer to reach an extension officer by phone or in person. The role of extension officers shifts toward cases the AI escalates and toward verification and follow-up, rather than first-line advisory delivery.

**How and when were they brought in, and what did they need to learn?**
Farmers were not trained in the conventional sense — the training model was use itself. The voice interface requires no digital literacy; any farmer who can make a phone call can use the system. Farmers begin naturally with simple queries (mandi prices, weather forecasts) and progress to more complex advisory interactions (crop-specific pest management, scheme eligibility) as familiarity grows. Whether extension officers received formal training on the system, and when in the deployment timeline that occurred, is not documented.

**Was there resistance from staff — and if so what worked to address it?**
Not documented.

**After the deployment, could staff still do their job if the system was unavailable — or had they become dependent on it?**
Not documented.

### Additional Insights

The "training = use" design principle — building a system where the interface itself is the onboarding — eliminates the training bottleneck that stalls deployments requiring formal instruction before first use. The voice channel operationalises this: a farmer does not need to learn a new interface, attend a training session, or achieve digital literacy before the system is useful to them. The implication for adoption velocity is direct: the deployment can scale as fast as awareness, without a training capacity constraint.

---

## F — Operating Model

*What makes it last.*

**What did this cost to build, and what does it cost to run annually?**
Pathway-level cost: approximately $250,000 to set up and approximately $250,000 per year to maintain. Serving infrastructure detail: before migration to self-hosted, ₹9.4 per question on Azure GPT-4.1, running at ₹2 lakh per day. After migration: ₹0.05 per question on self-hosted fine-tuned Qwen3.5-27B (4×H100 GPUs, vLLM, TP=4). The six-month actual cost for the 4-GPU cluster was ₹25 lakh. A planned 16-GPU cluster would run at approximately ₹2 crore per year versus an Azure run-rate of approximately ₹18 crore per year. Per-query total system costs by use case: Advisory ₹11.06, Scheme information ₹7.28, Mandi price ₹7.56, Weather ₹4.79 (these figures reflect total system cost per query, not LLM cost alone).

**How did your costs change over time as the deployment matured — and what drove those changes?**
LLM serving costs rose from ₹2 lakh per day in November 2025 to a projected ₹6 lakh per day as query volume grew on Azure. This trajectory triggered the migration to self-hosted Qwen3.5-27B, which reduced per-query LLM cost 188× — from ₹9.4 to ₹0.05. The driver was query volume growth, not a change in model or functionality. The migration was viable because input tokens constituted 80% of the Azure bill, and the fine-tuned smaller model achieved 94% accuracy against 91% for larger commercial models — meaning cost reduction did not require accepting lower output quality. Prefix caching, which skips 37% of notional input compute by caching the 6,000-token system prompt, provides an additional structural cost reduction that compounds as query volume grows.

**What did you measure to know it was working — and what did the numbers actually show?**
Query volume, per-query cost by use case, and user feedback are tracked. By the end of the structured pilot period: 440,000+ queries per month; 342,000+ unique users; 1.67 million+ questions answered; 791,000+ sessions; 17 lakh daily proactive alerts. Use case coverage: 205,000+ crop and pest advisory queries; 40+ government schemes; 307 APMCs; 203 warehouses; 4 agricultural universities integrated. Farmer feedback: 97%+ positive on crop advisory, 98.5% positive on scheme information. Average conversational turns per session: Advisory 3.15, Weather Forecast 2.78, Scheme 2.65, Mandi Price 2.60 — indicating multi-turn engagement for complex advisory and single-turn completion for price lookups. Outcome measures — whether advisory translated into improved yields, farm income, or scheme uptake — are not documented.

**Who owned operations after the pilot ended, and how was that handover structured?**
Not documented.

**Was there an outcome or a problem that showed up later that you wished you had been measuring from the start?**
Not documented.

**Was there a point where the whole thing nearly stalled — and what got it through?**
Not documented.

**Were there compliance, audit, or regulatory requirements that shaped how you ran operations?**
NIC (National Informatics Centre) hosting is a potential compliance pathway for government deployers who cannot use commercial cloud providers for sensitive data; whether the deployment has formally engaged this pathway is not documented.

### Additional Insights

The conversational turns data (Advisory 3.15 vs. Mandi Price 2.60) functions as a demand signal that validates resource allocation decisions. Advisory queries take more turns and carry higher per-query cost (₹11.06) because they require iterative clarification — farmers often describe symptoms in colloquial terms that require follow-up questions before a recommendation can be generated. The mandi use case completes in fewer turns (2.60) at lower cost (₹7.56) because it is a structured lookup. Tracking turns per use case alongside cost per query allows the operating team to distinguish between queries that are expensive because of computation and queries that are expensive because of inefficient data integration.

---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| OAN DPG layer | Open-source codebase | Foundational architecture for agricultural AI advisory; reusable across new state or country deployments | Via EkStep Foundation / OpenAgriNet |
| 7-layer system architecture | Architecture blueprint | Designing the full stack from user interface to DPI foundation for AI advisory systems | Documented in OAN source materials |
| Fine-tuned Qwen3.5-27B model | LLM weights | Agricultural advisory in Indian languages; starting point for fine-tuning in new geographies | Not publicly released in available sources |
| vLLM serving configuration | Infrastructure blueprint | Self-hosted LLM serving at scale; cost optimisation versus commercial API; TP=4 concurrency design for 27B-class models | Documented in MahaVistaar Production Serving Architecture note |
| Adversarial test set | Evaluation dataset | 500 attack patterns (prompt injection, hallucination triggers, jailbreak attempts) for evaluating agricultural advisory moderation models | Via EkStep Foundation |
| 54-enabler ecosystem map | Ecosystem design template | Identifying the minimum viable ecosystem for a comparable state-level deployment | Via EkStep Foundation |
| Beckn protocol integration | Interoperability standard | Connecting ecosystem partners without proprietary lock-in | Beckn community / EkStep Foundation |

---

## Related Pathways

- [Bharat-VISTAAR](bharat-vistaar.md) — National-level deployment built on MahaVistaar architecture
- [Amul Sarlaben](amul-sarlaben.md) — Cooperative deployment reusing OAN DPG layer; 3-week deployment demonstrates portability
- [Bihar Krishi](bihar-krishi.md) — Independent state deployment; comparison case for DPG reuse value
- [Ethiopia ATI](ethiopia-ati.md) — First international OAN deployment; demonstrates cross-border portability

## Related Entities

- [EkStep Foundation](../entities/ekstep-foundation.md)
- [OpenAgriNet](../entities/openagri-net.md)

## Lineage

This is the anchor OAN deployment. Subsequent deployments ([Bharat-VISTAAR](bharat-vistaar.md), [Amul Sarlaben](amul-sarlaben.md), [Ethiopia ATI](ethiopia-ati.md)) drew on MahaVistaar's architecture, code, and learnings.
