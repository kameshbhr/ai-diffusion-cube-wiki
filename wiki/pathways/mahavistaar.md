# MahaVistaar — Pathway

**Deployment:** MahaVistaar — Maharashtra Agricultural AI Advisory System
**Contributor:** Department of Agriculture, Government of Maharashtra; EkStep Foundation; OpenAgriNet
**Sector:** Agriculture
**Geography:** India — Maharashtra (statewide; initially selected Kharif districts)
**Actor type:** Government
**Journey stage:** Scaling
**Dimensions covered:** A, B, C, D, E, F
**Horizontal or vertical:** Vertical (sector-specific — agriculture)
**Deployment status:** Active
**Last updated:** 2026-06-02
**Contact for peer connection:** EkStep Foundation — ekstep.org

## Summary

MahaVistaar is Maharashtra's state-level voice AI advisory system for farmers, connecting crop advisories, weather, market prices, government schemes, and grievance tracking through a single voice call on any phone. Built in nine months by the Department of Agriculture, Maharashtra, it generated 342,000+ unique users, answered 1.67 million+ farmer questions, and now reaches 17 lakh farmers daily through proactive voice alerts. It is the pioneer deployment on the OpenAgriNet pathway and carries every transferable asset subsequent deployments have reused.

---

## A — Problem Orientation

*What you build on.*

**Who were you trying to serve, and what specific problem were you solving for them?**
Maharashtra serves 152 lakh hectares of Kharif cropland and millions of smallholder farmers who had no single point of access to integrated agricultural guidance. The specific problem was fragmentation: the state agricultural university held crop knowledge, IMD held weather, APMCs held market prices, MahaDBT held scheme status — none of these talked to each other, and none was accessible to a farmer through a single voice call. A Marathi-speaking farmer in Raigad asking "my paddy is still standing — should I harvest now?" needed current weather, local market prices, and crop-stage advisory from a university simultaneously. No single institution could answer it. Together they could — but they were never designed to work together.

**Who defined the problem — the deployer, the institution, or the user — and how do you know the user agrees?**
The Department of Agriculture, Maharashtra, defined the institutional problem — fragmented advisory channels and inaccessibility for the majority of farmers. The evidence that users agreed came rapidly after deployment: 205,000 crop/pest advisory queries per month, with farmers asking hyper-specific questions such as "leaf curling in chilli — what to do?" and "can guava be grown on my land?" The query volume itself confirmed the problem framing was accurate.

**How did you define your success metrics — are they usage based or outcome based?**
The deployment team tracked unique users, total questions answered, sessions (as an indicator of repeat engagement), and farmer feedback rate. As of early 2026: 342,000+ unique users, 1.67 million+ questions answered, 791,000+ sessions, 97–98.5% positive feedback rate. The shift toward proactive outbound alerts (17 lakh farmers reached daily) marked a move toward outcome-adjacent metrics. Full agronomic outcome metrics — yield change, input cost reduction — were not yet systematically measured at this stage.

**Did you discover something in the field that you hadn't anticipated when defining the problem or designing the solution?**
The OAN Diffusion Pathway documents that dialect variation and API instability were not anticipated and required nine months of operational learning. The deployment team also discovered that the system's categories needed to match farmers' mental models, not the department's organisational chart. Grouping use cases by what farmers are trying to do (asking about a sick crop, checking scheme eligibility, tracking an application) produced a different and more adoptable architecture than grouping by technical taxonomy. The inbound/outbound distinction also became clearer in practice: the shift from a platform that waited for questions to one that proactively pushed crop calendar advisories was identified as the move from useful to indispensable.

**Was there data already available to start with, or did you have to build or collect it first?**
Maharashtra had fragmented advisory platforms, university databases, weather services, and market data — all working in isolation. The deployment team reports that the feasibility question was not "what do we need?" but "what can be joined?" Every department had APIs that had never been called. The moment AI wired them together, officials were confronted with what their own data could show. No new data infrastructure was built before deployment began; the connection itself was the intervention.

**Why did this problem need AI — what would a non-AI solution have missed?**
The state had historically barely one agriculture field officer for every 2,000 farmers in comparable states. A non-AI advisory model scales with staff; an AI advisory model scales with usage. Beyond scale, AI was needed to perform real-time cross-institutional synthesis: a farmer's question routinely requires weather data, soil data, crop advisory, and scheme eligibility to be assembled and answered in one response in the farmer's language within seconds. No human extension system could do this at the moment of query. AI also revealed institutional data gaps — 205,000 monthly queries created a visible, quantified demand signal for knowledge that had previously been tacit.

**What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?**
The majority of Maharashtra's smallholder farmers are Marathi-speaking, many with limited literacy and basic feature phones rather than smartphones. The OAN Diffusion Pathway documents this as a structural inclusion problem, not a marginal one: a determined person would need a smartphone, reliable internet, sufficient literacy, and the right language to access what government portals already held. MahaVistaar was designed voice-first for this reason. The short code is 155313. The system supports Marathi, Hindi, Bhili, and English, with a bilingual Marathi↔English agricultural glossary built as a core component.

**Did you design the system to wait for users to come to it, or did it reach out to them too?**
Both modes operate. Inbound: farmers call 155313 with questions. In December 2025, the system was receiving over 440,000 categorised queries per month. Outbound: the system proactively pushes crop calendar advisories, pest alerts (e.g., "pink bollworm detected in your region"), and weather warnings to registered farmers before they ask. Roughly 15 stage-based advisories are delivered proactively across the crop calendar. The second phase of MahaVistaar was explicitly designed to complete the shift from a platform that waits for questions to one that anticipates needs.

---

## B — Architecture

*What you build with.*

**Did you need data sources that were controlled by other departments or organisations — if so, what did it actually take to get access?**
Yes. The deployment required data-sharing across the Department of Agriculture, state agricultural universities (MPKV, VNMAU, PDKV, PDKV), IMD, Skymet, APMCs (307 market committees), MahaDBT (40+ government schemes), AgriStack (farmer and farm registry), soil labs, and KVKs. The OAN Pathway documents that the Department of Agriculture authorised data-sharing across its own systems and from its agricultural universities — this institutional authorisation was the system leadership work that made everything else possible. Specific negotiation timelines for each data source are not documented in available sources.

**Did you bring data together into one place or connect to it where it lived — and why?**
Data was connected to where it lived rather than centralised. The orchestrating AI agent connects to institutional data sources as tools at the moment of query. Raw institutional data never moves to a central repository. The OAN architecture principle is explicit: data stays with its legitimate owner; the AI reaches it through APIs with farmer consent at the moment of query. This choice was made for both sovereignty reasons (government data remaining with government institutions) and compliance reasons (alignment with India's Digital Personal Data Protection Act).

**For each major component of your system — did you build it, buy it, or reuse something that existed? Would you make the same choices again?**
The MahaVistaar system was built on OpenAgriNet's open-source building blocks — the same 7-layer architecture (user, interface, moderation, AI decision engine, knowledge/scientific models, live data sources, DPI foundation) reused across subsequent deployments. The production serving stack (documented in the MahaVistaar Architecture Note, May 2026) runs a fine-tuned Qwen3.5-27B model as the primary advisory LLM on 4 × H100 GPUs via vLLM, with GPT-OSS Safeguard 20B as an independent moderation model on 2 × H100s, and Azure OpenAI as fallback. The moderation model and advisory model are fully decoupled — a design choice the team explicitly maintained. For several months before the migration to self-hosted, the platform ran entirely on GPT-4.1 via Azure OpenAI at ~₹9 per question; the self-hosted path achieves ~₹0.05 per question at full utilisation, a ~180× reduction.

**Did any data source or system integration turn out to be harder than expected?**
The OAN Pathway documents dialect variation and API instability as the two most operationally demanding challenges, both requiring the full nine-month build period to resolve. Weather station geographic gaps required expanding search radii and building graceful fallbacks. Some government data APIs had never been called before MahaVistaar wired into them, meaning the system exposed data quality problems that had previously been invisible — officials asking "whose data is right?" for the first time.

**Did vendor lock-in become a real constraint — what were your options and how did you resolve it?**
The initial deployment on GPT-4.1 via Azure OpenAI created both cost exposure and potential lock-in. The Architecture Note documents the decision to migrate to a self-hosted fine-tuned open-source model (Qwen3.5-27B) as the primary path, with Azure retained as a reliability fallback rather than the primary inference provider. The design principle is explicit: no AI model is permanent; the infrastructure beneath — institutional data sources, open network protocols, farmer registries — remains stable as models evolve. The modular architecture means the AI model can be swapped without changing data sources, and the voice pipeline can be upgraded without changing orchestration logic.

**What was your design policy for handling peak load?**
The Architecture Note documents the policy as "latency over queue depth." The vLLM primary is capped at 100 concurrent calls per endpoint. When a request arrives and the cap is saturated, the system does not queue it — the request is routed instantly to Azure OpenAI as fallback. The operating principle is that users never experience elevated latency from queuing, even at burst load. The cost of that guarantee is paid by Azure, not by the user. The 100-call cap is tunable via environment variable, not hard-coded. Load tests at 10, 25, and 60 users/minute produced no fallback events.

**Did the AI produce wrong or harmful outputs that reached users — how did you detect it and what did you put in place to prevent recurrence?**
The architecture includes an independent moderation layer — GPT-OSS Safeguard 20B — fully decoupled from the advisory engine. This model performs domain validation, content safety filtering, prompt injection defence, and input sanitisation on every query. In voice channels, moderation is embedded within the ASR pipeline. Adversarial test sets of up to 500 attack patterns were maintained. The design principle is that unsafe outputs are caught before they reach the farmer, not addressed by policy after the fact. Specific documented incidents of harmful outputs reaching users are not available in current sources.

**Did data residency, sovereignty, or government policy on technology vendors constrain your architecture — did that come up early or late?**
Data sovereignty was a foundational design constraint, addressed from the start. The orchestrating agent talks directly to the deployer's databases, pulls data, frames the prompt, and sends only the prompt to the LLM — raw data never leaves government systems. This is described in the Six Shifts framework as a sovereignty decision, not a technical footnote. The architecture aligns with India's Digital Personal Data Protection Act (DPDP). NIC hosting requirements for sensitive government data (land records, scheme eligibility) also required dedicated secure connectivity.

**If you used voice — did you face any problems such as latency, pronunciation, turn-taking and timing? What did you do to address it?**
Voice was the primary channel. The deployment team built a distinct voice pipeline — ASR (automatic speech recognition), turn detection, and TTS (text-to-speech) — separate from the advisory decision engine. Marathi regional accent variation required a bilingual Marathi↔English agricultural glossary as a core component. Low-latency inference was critical for voice: the model must begin streaming output before the full response is ready, enabling TTS to start speaking immediately. Telephony gateway hardware (SIP servers, PSTN interconnect) with low jitter and stable audio codec support was required. The system plans a future transition to unified speech-to-speech models. The typical advisory exchange completes in 12–15 seconds wall-clock response time.

**How frequently did the underlying data change, and how did you keep the AI current with those changes?**
Different data sources have different update frequencies. IMD and Skymet weather data are real-time feeds accessed at query time. APMC mandi prices are updated regularly and accessed as live tools. Government scheme data (MahaDBT) changes less frequently but was accessed through live APIs rather than cached static copies. The agricultural advisory corpus (crop SOPs, pest guides from ICAR and universities) is more stable but required structured chunking, metadata tagging, and periodic update. The system's connection-at-query-time architecture means that when source data is updated, the AI's responses update without any model retraining.

**Did you hit any infrastructure constraint at scale that you didn't anticipate, and how did you resolve it?**
The Architecture Note documents that the initial 8-GPU node (4 GPUs for MahaVistaar LLM at TP=4, 2 for moderation, 2 idle) was suboptimal: tensor parallelism accepts only power-of-two widths, meaning the node cannot step from TP=4 to TP=6, leaving 2 GPUs stranded. The planned resolution is to spin up a separate dedicated single-H100 moderation node and consolidate all 8 main-node GPUs for the advisory LLM at TP=8 — roughly doubling concurrency from ~80 to ~160+ users per node with the addition of one H100. The prior Azure cost trajectory (headed toward ~₹6 lakh/day at Voice AI scale) was the infrastructure constraint that drove the migration to self-hosted inference.

### Additional Insights

The Architecture Note documents a precise cost comparison that any adopter planning scale should study. The volume-weighted average cost on Azure OpenAI was ₹9.4 per question (November 2025 production data, 216,000 queries). The self-hosted path achieves ₹0.05 per question at full utilisation — a ~180× reduction. Advisory queries dominated both cost and volume (67% of LLM spend on 57% of queries) because they chain multiple tool calls. The input token cost dominated composition (79.7% of total), making prefix caching — not output token efficiency — the primary cost lever. A 16-GPU build-out pencils at ~₹2 crore annually versus a projected Azure run-rate of ~₹18 crore/year at scale.

---

## C — Institution

*Who owns solving of the problem.*

**Was this deployment treated as a one-time project or as a long-term transformation initiative — did that framing create problems?**
The OAN Pathway documents that the Department of Agriculture, Maharashtra did not commission a platform — it created a state-level advisory capability embedded in the workflows of farmers, extension workers, and departments. The framing was explicitly a long-term institutional transformation: moving from fragmented advisory channels to a common rail for trusted intelligence, creating a feedback loop so field usage improved policy over time, and scaling without adding staff proportionally. Whether this framing encountered resistance from those who preferred a project framing is not documented in available sources.

**How did you get the deployment approved and funded?**
Not documented in detail. The OAN Pathway records that the Department of Agriculture authorised data-sharing across its own systems and from its agricultural universities, and that a named Agri Secretary sponsor and nodal officers across agriculture, IT, and field operations were the first concrete institutional decisions. The Six Shifts framework notes that state government sponsorship — specifically the alignment of an Agri Secretary — was the enabling condition for MahaVistaar as the pioneer deployment.

**If the one or two people driving this deployment had moved to different roles mid-way, what would have happened?**
The Six Shifts framework flags this risk explicitly under institutional knowledge (C3): AI forces institutions to articulate what they know, what they decide, and why. When the Department of Agriculture authorised its advisory corpus to flow through MahaVistaar, it made an institutional knowledge claim that became publicly queryable — no longer living only in individual experts. However, whether the institutional arrangements around MahaVistaar itself were sufficiently documented to survive key personnel transitions is not confirmed in available sources.

**Which departments had to cooperate for this to work — where did that cooperation break down or get difficult, and how was it resolved?**
The OAN enabler map documents 54 organisations across institutional/governance, technology/AI, structured data, and knowledge/document layers — including the Department of Agriculture, Department of Livestock (MH), Department of Fisheries (MH), GoI Agriculture Ministry, Maharashtra DBT, and others. The specific friction points in interdepartmental cooperation are not documented in available sources. The framework document notes that in one unnamed project, the same institution accused its operational partner of rubber-stamping vendor decisions while also refusing to participate in the steering committee — a pattern to watch for.

**Did procurement rules become a barrier — and if so how did you navigate through?**
The Six Shifts framework documents procurement as a systemic barrier across deployments generally: government procurement was built for hardware and hiring body shops, not for buying AI capabilities that evolve monthly. RFP specifications become obsolete before contracts are signed. MahaVistaar-specific procurement navigation is not documented in available sources.

**Were there decisions that needed political support from above — did you have it when you needed it?**
Bharat-VISTAAR (the national layer built on MahaVistaar's architecture) was announced in the Union Budget 2026-27 and championed by the Prime Minister at the India AI Impact Summit — indicating strong political support at the national level for the pathway MahaVistaar pioneered. State-level political support during MahaVistaar's nine-month build is not detailed in available sources.

**When something went wrong, who was accountable — and was that clear from the start?**
Not documented.

**Which institution did the AI speak on behalf of — and did that institution have credibility with your end users?**
MahaVistaar speaks as the Department of Agriculture, Maharashtra, and cites state agricultural universities (MPKV, VNMAU, PDKV). The Six Shifts framework documents this explicitly: the AI must not speak as itself — it must speak as the institution. Every response carries institutional attribution. The trust source analysis in the framework confirms that farmers distinguish between information and trusted information: the same advice from a commercial seller sounds like a sales pitch; from a university or government extension service, it sits as certain.

---

## D — Ecosystem

*Who executes.*

**How many organisations had to work together for this to function?**
54 enablers are documented across four layers: 14 institutional/governance (funders including Gates Foundation, World Bank, UNDP, EkStep Foundation; orchestration partners EkStep, COSS, Samagra, Artha Global; government bodies), 8 technology/AI (research institutions IIT Mumbai, IISc, Vassar Labs, India AI Mission; language models Bhashini, AI4Bharat, Karya; knowledge contributors ICAR), 8 structured data sources (APMC, WDRA, CHC, KVK, IMD, Skymet, Officer Data, Scheme Data), and 24 knowledge/document sources (state and national programme guidelines, crop knowledge manuals, livestock and animal husbandry materials, fisheries and aquaculture guidelines, research and reports). The OAN Pathway notes that 25+ organisations were directly required for MahaVistaar's core operation.

**Who was specifically responsible for keeping all partners aligned — was that role clearly assigned and resourced?**
EkStep Foundation served as the primary orchestration and implementation partner. The OAN Pathway documents that the role of the entity that creates the "network roots" and says "this runs in my name" was critical — and that the Department of Agriculture, Maharashtra, held that institutional authority. Whether the coordination role had a single named individual with explicit resourcing is not documented.

**Were there partners whose commitment weakened over time — what drove that and how did you handle it?**
Not documented in available sources.

**Where did partners have conflicting priorities or mandates — how were those conflicts resolved?**
Not documented in available sources. The Six Shifts framework documents a named failure pattern from a different deployment (not MahaVistaar): an institution that accused its operational partner of rubber-stamping vendor decisions while also refusing to participate in the steering committee governing those decisions. That pattern is flagged as a risk rather than a MahaVistaar-specific event.

---

## E — Workforce

*Who absorbs AI.*

**Were there people — field workers, extension officers, call centre staff — whose job changed because of this deployment?**
Yes. Agricultural extension officers in Maharashtra had previously operated by travelling long distances to answer questions across crops, livestock, schemes, and markets, carrying scattered PDFs, circulars, and personal notes. MahaVistaar does not replace extension officers — it changes what they do. The system enables farmers to get answers to routine questions directly, freeing extension capacity for higher-value interactions. The system also serves government and policy actors as a layer: state planning officials can see live usage patterns across the crop calendar.

**When the AI gave an answer or recommendation to a user, what was the last-mile human expected to do with it — and were they actually capable of doing that?**
For farmers using the inbound voice channel, the last-mile is the farmer themselves — the expectation is that they act on the advisory (spray this, harvest now, apply for this scheme). The system was designed so that use itself is training: farmers move naturally from simple queries (weather, pest) to complex actions (scheme applications, credit products, grievance tracking). For extension officers using the system as a reference, the expectation is professional judgement applied to AI-supplied information — not blind compliance.

**How and when were they brought in, and what did they need to learn?**
Not documented for Maharashtra-specific extension officer training. The OAN Pathway notes that farmers were not trained on MahaVistaar and then given access — they called a number, asked a question, and got an answer. The system was designed so that use is training.

**Did you face resistance from staff — what were the reasons and what worked?**
Not documented in available sources.

**Did frontline staff become dependent on the system in a way that reduced their own capability — how did you know?**
Not documented. The Six Shifts framework flags this as a genuine risk (the agency test, E3): the question is whether AI leaves people more capable or more dependent. MahaVistaar-specific evidence on this question is not available.

**How did problems or insights from the field reach the people improving the system — was there a structured feedback loop?**
The system creates a data feedback loop: 205,000+ monthly queries create a visible, quantified demand signal for knowledge that was previously tacit. Where farmers' questions went unanswered, the institution could now see its own gaps. The OAN Pathway documents this as one of the structural benefits of AI at population scale — institutions listening to field signals continuously, not just through periodic surveys. Specific governance mechanisms for translating this signal into system improvements are not documented.

---

## F — Operating Model

*What makes it last.*

**Who took ownership of steady state operations after the pilot — how was that transition structured and when did it happen?**
The Department of Agriculture, Maharashtra holds institutional ownership. EkStep Foundation and the broader OAN partner network hold the technical operating model. The specific transition structure from pilot to steady state is not documented in available sources. The Architecture Note (May 2026) describes an ongoing production deployment, suggesting the transition has occurred, but its structure is not detailed.

**What did it cost to build, and what does it cost to run annually — how did those compare to your original estimates?**
The Six Shifts framework notes a general pathway cost of approximately $250,000 to set up and $250,000 per year to maintain — MahaVistaar is the pioneer against which these estimates were derived, so it likely incurred higher build costs than subsequent deployments. The Architecture Note documents current GPU infrastructure costs precisely: six months of the 4-GPU H100 cluster cost ₹25 lakh (~₹50 lakh annually); a planned 16-GPU build-out would cost ~₹2 crore annually. Against a projected Azure run-rate of ₹18 crore/year, the self-hosted economics are strongly favourable. Original estimates versus actuals are not documented.

**Were there compliance, audit, or regulatory requirements that shaped how you ran operations?**
India's Digital Personal Data Protection Act (DPDP), 2023 shaped the consent architecture. NIC hosting requirements applied to government data. The modular data architecture — connecting to data where it lives, not copying it — was designed to be DPDP-compliant by construction rather than as a post-facto audit exercise.

**How long did the deployment actually take versus what you planned — where did time get lost?**
MahaVistaar was built from commitment to deployment in nine months. This was the pioneer build — without a playbook, governance frameworks, or failure mode library to draw on. The nine months absorbed learning about dialect variation, API instability, inter-institutional data access, and trust-building with farmers. Subsequent deployments compressed this dramatically: Ethiopia took three months, Amul took three weeks. The nine months was not waste — it produced every transferable asset the pathway now carries.

**Was there a point where the whole thing nearly stalled — and what got it through?**
Not documented in available sources.

**What did you measure to know the solution was working — and what did the numbers actually show?**
As of early 2026: 342,000+ unique users; 1.67 million+ farmer questions answered; 791,000+ sessions (indicating repeat and sustained engagement, not one-off usage); 17 lakh farmers reached daily through proactive personalised voice alerts; 97–98.5% positive feedback rate. The system spans weather, pest advisory, mandi prices, 40+ government schemes, 307 APMCs, 4 state agricultural universities, and 203 warehouses — all accessible through a voice call or message in Marathi. Agronomic outcome metrics (yield change, input cost reduction) were not yet systematically reported at this stage.

**Did you do a big launch or sequence through small pilots — and looking back was that the right call?**
The Six Shifts framework documents "bounded ambition" as MahaVistaar's launch strategy: starting with one or two crops, a few districts, one or two languages. The national platform Bharat-VISTAAR was built on the architecture Maharashtra established. The pathway evidence from MahaVistaar supports the "sequence through small pilots" approach explicitly — and the framework states that those who treat the pilot as a vanity launch find the compounding stops there.

---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| OpenAgriNet open-source building blocks (7-layer architecture) | Code / DPG | Foundational voice AI system for agriculture — Knowledge Engine, Memory Layer, Trust Layer, Agent Core, Action Gateway, Reach Layer, Learning Layer | openagri.net |
| Dual-provider inference stack design (vLLM + Azure fallback) | Architecture pattern | Handling peak load at low cost with reliability guarantee — documented in MahaVistaar Architecture Note May 2026 | Internal note; contact EkStep Foundation |
| Adversarial test set (500 attack patterns) | Evaluation benchmark | Safety testing for agricultural AI moderation layers | Via OpenAgriNet ecosystem |
| Bilingual Marathi↔English agricultural glossary | Language asset | ASR/TTS accuracy for regional agricultural terminology | Via OpenAgriNet ecosystem |
| Advisory corpus (ICAR, state university crop/pest knowledge, chunked and metadata-tagged) | Knowledge base | Agriculture advisory RAG layer | Via OpenAgriNet ecosystem |
| 54-enabler ecosystem map | Governance template | Inventorying the four-layer ecosystem (institutional/governance, technology/AI, structured data, knowledge/documents) for a new deployment | OAN Diffusion Pathway document |
| Governance frameworks, data connector approach, model evaluation benchmarks, failure mode library | DPG — organisational knowledge | Transferable deployment know-how for next instances | Via EkStep Foundation / OpenAgriNet |

---

## Solution Patterns

### Architecture

**Problem:** LLM costs become unsustainable as usage scales.

**Solution:** Migrate high-volume flows to self-hosted open-source models; retain managed API as fallback only. Profile cost by use case before migrating — identify the dominant flow and optimise for its worst case.

---

**Problem:** Self-hosted infrastructure and managed APIs create opposing pressures on cost and reliability.

**Solution:** Dual-provider architecture: self-hosted as primary, managed API as automatic fallback triggered only by infrastructure faults — not answer quality. Define a tunable concurrency cap that spills to managed API on overflow rather than queuing users.

---

**Problem:** The system gets locked with a vendor with no exit path.

**Solution:** Build a provider abstraction layer at the start — resolve provider at configuration time, not in application code. Migration between providers becomes transparent to the application.

---

### Population & Access

**Problem:** Target population cannot reach the system through available channels.

**Solution:** Voice-first as an architectural requirement — IVR short codes on basic feature phones, not a smartphone add-on. Support multiple channels — voice, WhatsApp, app, web — converging into the same processing pipeline.

---

**Problem:** The system works in one language but the population speaks many.

**Solution:** Build multilingual ASR and TTS pipeline as core infrastructure, not a post-launch addition. Develop domain-specific bilingual glossary to bridge regional language and institutional terminology — general translation models fail on specialised terms.

---

### Data

**Problem:** Data needed to serve users is fragmented across institutions.

**Solution:** Federated tool architecture — AI connects to each institutional source at query time via API; data does not move into a central repository. Each institution retains ownership and governance of its own data; open network protocols provide the interoperability layer.

---

**Problem:** AI responses have no traceable source — no institution is accountable for what the system says.

**Solution:** Every claim the system makes must be retrieved from a named institutional source at the time of the query — the system does not answer from its own model memory. Surface institutional source attribution visibly to the user on every response.

---

### Institution

**Problem:** The deployment is treated as a technology project — commissioned by the institution but not owned by it — leaving no one with authority over the governance, data sharing, and outcomes that the technology alone cannot deliver.

**Solution:** Nominate a named senior sponsor and nodal officers across relevant departments before build begins. Frame the deployment as an institutional capability.

---

**Problem:** Data sharing agreements between institutions take longer to negotiate than the project expects.

**Solution:** Begin data sharing negotiations before technical build starts — treat agreement timelines as the critical path, not a parallel workstream. Align data sharing across all required institutions as system leadership work before any build begins.

---

### Trust & Adoption

**Problem:** End users distrust AI-generated answers for decisions.

**Solution:** Position AI as delivery layer not authority — every answer cites the institution whose knowledge it draws from. The institution stands behind every answer; AI makes institutional knowledge reachable, it does not replace institutional accountability.

---

**Problem:** The AI system makes claims the institution has not authorised it to make.

**Solution:** Define explicitly what the AI can and cannot do — domain validation, content safety, and policy-sensitive query classification enforced by an independent moderation layer. Every claim flows through a verified tool call to an authoritative source; the AI does not answer from memory.

---

### Ecosystem

**Problem:** The deployment requires capabilities and data that no single institution possesses — but the institutions that collectively possess them were never designed to work together.

**Solution:** Map the full enabler ecosystem before build — identify which layer each actor belongs to, what they contribute, and what governance arrangement allows their contribution to flow. Design participation so each actor's own interest is served — shared mission alone will not sustain coordination across actors with different mandates and incentives.

---
## Gaps — Information Not in the Source Documents

1. At twelve months, what would you expect to observe in a farmer's life — not in the system's logs — that would tell you this worked? And for any of the live deployments, has anything like that been observed yet?
2. Which body has the authority to determine what MahaVistaar can and cannot claim on behalf of the state — and what happens when that boundary is crossed?
3. How was the initial deployment funded — which institution's budget, under what mechanism? And who bears the ongoing cost of the GPU cluster and the operational team — state government budget, central scheme, development partner, or something else?
4. For the core actors — ICAR, IMD, AgriStack, the state agricultural universities — was their data contribution under a formal agreement, an informal arrangement, or a public mandate? And if any of them had withdrawn, what would have broken?
5. Were extension officers or agriculture department staff resistant to the system — and what form did that resistance take?
6. Today, in normal operations, who decides when the model needs retraining, when the advisory corpus needs updating, and when a guardrail needs changing? Is that a named role, a team, or is it still the pilot team?
7. When a farmer receives a wrong or harmful answer — wrong pest treatment advice, wrong scheme eligibility, wrong mandi price — what is the path from that error to a fix? Who finds out, who decides what to do, and how are the guardrails updated so it doesn't happen again?
8. Which specific regulatory or policy constraints — DPDP obligations, government procurement rules, NIC hosting requirements — shaped how the deployments were structured? And were any of them obstacles that required a workaround?
