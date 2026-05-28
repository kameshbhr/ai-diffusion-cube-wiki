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

MahaVistaar is an AI-powered agricultural advisory system deployed by the Commissioner of Agriculture, Government of Maharashtra, serving Maharashtra's 1.5 crore farmers through a toll-free voice channel (short code 155313) in Marathi. The system handles crop advisory, scheme guidance, mandi price queries, and weather-based alerts, and is the anchor deployment of the OpenAgriNet (OAN) digital public goods architecture. For a next adopter, this pathway documents how a state government can take an AI advisory system from pilot to scale, the cost structure of self-hosted versus commercial LLM serving, and the ecosystem design required to sustain a system answering queries from over a million farmers.

---

## A — Problem Orientation

*What you build on.*

**Who were you trying to serve, and what specific problem were you solving for them?**
The deployment targets Maharashtra's 1.5 crore farmers, the majority of whom are smallholders with limited access to timely, personalised agricultural advice. Farmers face decisions — pest management, optimal sowing windows, scheme eligibility, mandi price movements — that change week to week, but the extension officer network cannot deliver timely, individualised advice at that cadence or scale.

**What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?**
Farmers communicate in Marathi; many have low digital literacy and limited smartphone access. The system was built voice-first, delivered over standard telephony via short code 155313 rather than a smartphone app. This allows reach into populations without data plans or literacy sufficient for text-based interfaces. Bhashini ASR/TTS components handle spoken Marathi input and output.

**Was there data already available to start with, or did you have to build or collect it first?**
The deployment drew on existing institutional data — state agricultural databases, ICAR knowledge repositories, weather service feeds, and mandi price data. A federated architecture was adopted: the AI connects to data where it lives at query time rather than copying it into a central store. This avoided the institutional and compliance cost of data migration while enabling real-time answers.

**Why did this problem need AI — what would a non-AI solution have missed?**
The extension officer network in Maharashtra cannot deliver personalised advice to 1.5 crore farmers at the cadence required. A non-AI solution faces a hard ceiling at the number of human officers available. AI enables the system to handle thousands of concurrent voice calls, generate personalised answers from multiple real-time data sources, and shift from reactive query-answering to proactive advisory — sending outbound pest alerts or weather warnings to farmers in affected geographies before they call in.

**Did your understanding of the problem change after you started — and if so, how?**
The deployment evolved from a reactive query system (farmers call in with questions) toward a proactive advisory model (system pushes relevant alerts to farmers based on their location and crops). This shift was enabled by integrating crop registry and location data that was not part of the original design.

**Is there anything about your users you assumed early on that turned out to be wrong?**
Not documented.

---

## B — Architecture

*What you build with.*

**Did users interact through voice, an app, or something else — and what drove that choice?**
Users interact exclusively through voice telephony, calling short code 155313. The choice was driven by the access constraints of the target population — voice over basic telephony reaches farmers regardless of smartphone ownership, data plan availability, or digital literacy. The interface layer transcribes Marathi speech (Bhashini ASR), processes the query through the AI decision engine, and returns a spoken Marathi response (Bhashini TTS).

**Did you bring data together into one place or connect to it where it lived — and why?**
Data remains federated — the AI connects to data sources (agricultural databases, weather feeds, mandi prices, pest alerts) at query time rather than copying them into a central repository. This approach preserves data sovereignty for institutional data owners and avoids the institutional cost and compliance risk of centralised data migration. The trade-off is query latency, which is managed through caching of high-frequency data.

**What did you build yourself versus use something that already existed?**
Built: the OAN DPG layer (reusable across future deployments), the fine-tuned Qwen3.5-27B agricultural advisory model, the 7-layer system architecture, and the deployment-specific configuration for Maharashtra (crops, schemes, language). Used existing: Bhashini ASR/TTS (AI4Bharat), Karya voice data, ICAR knowledge repositories, Beckn protocol for ecosystem interoperability, and the state agriculture department's data infrastructure.

**How did you avoid being locked into a single vendor?**
The architecture explicitly separates the DPG layer (reusable, open-source code) from the deployment instance (Maharashtra-specific configuration). The LLM serving stack migrated off Azure GPT-4.1 (commercial API) to self-hosted fine-tuned Qwen3.5-27B on 4×H100 GPUs running vLLM with tensor parallelism (TP=4), reducing per-query cost from ₹9.4 to ₹0.05. This migration demonstrates that the architecture does not require a commercial LLM API. The Beckn protocol ensures ecosystem interoperability without locking into any single partner's standards.

**Did any data source or system integration turn out to be harder than expected?**
Not documented.

**Did the AI ever give a wrong or harmful answer to a user — and how did you catch and handle it?**
The deployment uses a dual-model architecture: the primary Qwen3.5-27B advisory model and an independent GPT-OSS Safeguard 20B moderation model that evaluates every output before it reaches the user. The safeguard model operates independently — it cannot be influenced by the same prompt injection that might affect the primary model. If the safeguard flags a response, it is blocked before delivery.

**What did you put in place to prevent the AI from causing harm — and was it ever tested?**
The independent safeguard model (GPT-OSS Safeguard 20B) runs on every response. A 6,000-token system prompt encodes advisory guardrails, including escalation paths for situations where the AI should direct the farmer to a human officer rather than attempt an answer. The prefix caching infrastructure caches this system prompt — 37% of notional input compute is skipped — so guardrail evaluation does not add proportional cost per query. Whether the safeguard has been formally adversarially tested is not documented.

---

## C — Institution

*Who deploys AI.*

**How did you get the deployment approved and funded — and did you position it as a one-time project or a long-term transformation initiative?**
The deployment is positioned as a long-term transformation of the extension delivery system — not a pilot project. The Commissioner of Agriculture, Maharashtra is the named deployer. Funding sources and the specific approval pathway are not documented in available sources.

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

---

## D — Ecosystem

*Who executes.*

**How many organisations had to work together for this to function?**
The OAN source document maps 54 named enablers across four layers: institutional (government departments, Commissioner of Agriculture), technology (EkStep Foundation, AI4Bharat/Bhashini, Karya, vLLM serving infrastructure), data (state agricultural databases, ICAR, weather services, mandi price systems), and knowledge (domain experts, agricultural scientists). EkStep Foundation acts as the network orchestrator across these enablers.

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
Not documented.

**Was there resistance from staff — and if so what worked to address it?**
Not documented.

**After the deployment, could staff still do their job if the system was unavailable — or had they become dependent on it?**
Not documented.

---

## F — Operating Model

*What makes it last.*

**What did this cost to build, and what does it cost to run annually?**
The serving infrastructure migration cost is documented. Before migration to self-hosted: ₹9.4 per question on Azure GPT-4.1, running at ₹2 lakh per day and trending toward ₹6 lakh per day at growing query volume. After migration: ₹0.05 per question on self-hosted fine-tuned Qwen3.5-27B (4×H100 GPUs, vLLM, TP=4). The 6-month actual cost for the 4-GPU cluster was ₹25 lakh. A planned 16-GPU cluster would run at approximately ₹2 crore per year versus an Azure run-rate of approximately ₹18 crore per year. Per-query costs by use case: Advisory ₹11.06, Scheme information ₹7.28, Mandi price ₹7.56, Weather ₹4.79 (these figures reflect total system cost per query, not LLM cost alone).

**What did you measure to know it was working — and what did the numbers actually show?**
Query volume and per-query cost by use case are tracked. The use case breakdown (Advisory, Scheme, Mandi, Weather) indicates the system tracks what farmers call about, not just aggregate volume. Outcome measures — whether advisory improved farmer decision-making or yields — are not documented.

**Who owned operations after the pilot ended, and how was that handover structured?**
Not documented.

**Was there an outcome or a problem that showed up later that you wished you had been measuring from the start?**
Not documented.

**Was there a point where the whole thing nearly stalled — and what got it through?**
Not documented.

**Were there compliance, audit, or regulatory requirements that shaped how you ran operations?**
Not documented.

---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| OAN DPG layer | Open-source codebase | Foundational architecture for agricultural AI advisory; reusable across new state or country deployments | Via EkStep Foundation / OpenAgriNet |
| 7-layer system architecture | Architecture blueprint | Designing the full stack from user interface to DPI foundation for AI advisory systems | Documented in OAN source materials |
| Fine-tuned Qwen3.5-27B model | LLM weights | Agricultural advisory in Indian languages; starting point for fine-tuning in new geographies | Not publicly released in available sources |
| vLLM serving configuration | Infrastructure blueprint | Self-hosted LLM serving at scale; cost optimisation versus commercial API | Documented in MahaVistaar Production Serving Architecture note |
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
