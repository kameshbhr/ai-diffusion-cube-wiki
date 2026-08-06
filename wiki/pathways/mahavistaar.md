# MahaVISTAAR Pathway

## 0. Reading guide

This is a pathway of MahaVISTAAR (Maharashtra's state agricultural voice advisory system). It draws primarily on the published diffusion pathway document and its executive summary, cross-checked against an earlier OpenAgriNet package document and a production-serving architecture note. Written for a government department, technologist, or social-sector/enterprise team deciding whether to build a similar voice-first, DPI-backed advisory system, or already building one.

**Why this pathway exists.** MahaVISTAAR doesn't speak as an AI — it speaks as the Department of Agriculture, Maharashtra, through a bot named Vasudha. A farmer who gets bad advice doesn't experience "the model got it wrong"; she experiences "the department failed me." Every unit here — architecture, data governance, safety design, testing sequence — traces back to that fact. The second throughline: the problem was fragmentation, not absence. The knowledge farmers needed already existed across universities, IMD, APMCs, and scheme databases; the work was connecting it.

**How to navigate:**
- Deciding whether AI advisory fits your context → Units 1–3, 7.
- Negotiating institutional sign-off and data access → Units 26–31, 38.
- Mid-build, choosing architecture and vendor posture → Units 9–16.
- About to test with real users → Units 20, 33.
- Already live, dealing with call-quality issues → Units 17–19.
- Staring at your inference bill → Units 21–25.
- Wondering what would transfer elsewhere → Downstream Adoptions (Section 1), Units 41–42.

---

## 1. Pathway identity

| Field | Detail |
|---|---|
| Deployment/Pathway name | MahaVISTAAR — Maharashtra State Agricultural Advisory |
| Sector | Agriculture — crop advisory, pest management, market pricing, government scheme access, grievance tracking |
| Actor type | Government, Technologist, Social Sector/Enterprise |
| Geography | Maharashtra, India (152 lakh hectares of Kharif cropland) |
| Population served | Smallholder farmers in Maharashtra — primarily Marathi-speaking, feature-phone users, limited literacy, no reliable internet. The median user, not the edge case. |
| Stage reached | Scale |
| Contributing organisation | Department of Agriculture, Government of Maharashtra; EkStep Foundation; OpenAgriNet (OAN) |
| Key dates | Build: commitment to deployment, 9 months. Architecture Note: as of May 2026. Pathway document: as of July 2026. |
| Summary | MahaVISTAAR is a live, government-run voice advisory system connecting seven fragmented institutional data sources behind a single call, with the Department of Agriculture's own name and authority standing behind every answer. |
| Scale/impact achieved (as of mid-2026) | 342,000+ unique users · 1.67 million+ questions answered · 791,000+ sessions (repeat/sustained engagement, not one-off usage) · 17 lakh farmers/day via proactive alerts · 97–98.5% positive feedback |
| Cost anchor (as of mid-2026, order of magnitude) | ~$250K setup, ~$250K/year run-rate. GPU infrastructure detail: 6 months of a 4-GPU H100 cluster cost ₹25 lakh; a planned 16-GPU build-out pencils at ~₹2 crore/year against a projected Azure run-rate of ~₹18 crore/year at scale. AI inference cost fell 180× after migrating to self-hosted (₹9.4 → ₹0.05/question, as of November 2025). |
| Build effort | 9 months from commitment to deployment, with 30 partner organisations, targeting a population of 3 million farmers. No prior pathway existed to draw on — this was the pioneer build. |
| Known downstream adopters | OpenAgriNet Ethiopia (ATI) — reused the architecture, 3 months to deploy vs. MahaVISTAAR's 9, though farmer-trust mechanics needed local adaptation and did not transfer directly. Amul/Sarlaben (Gujarat dairy cooperative) — reused two full cycles of shared learning, 3 weeks to deploy, serving 3.6 million farmers and 40 million cattle from day one. Bharat-VISTAAR (national) — federated the proven state-level architecture nationally, announced in the Union Budget 2026-27, only after the state architecture was proven at scale. |
| Scope — where this does not transfer cleanly | Strongest where the population is feature-phone-dependent, Indic-language-speaking, institutional credibility is a trust asset, and the needed data already exists in fragmented institutional form that can be federated. Transfers less cleanly where the population has reliable smartphone access and text literacy, government credibility is contested or low, no existing agricultural data infrastructure exists to connect to, or the primary goal is internal efficiency rather than last-mile inclusion. |

---

## 2. Coverage grid and gaps

| Dimension | Explore | Define | Pilot | Scale |
|---|---|---|---|---|
| Persona | ●●● | ●● | ○ | ● |
| Solution | ●● | ●●● | ●●● | ●●● |
| Institution | ● | ●●● | ● | ●● |
| Ecosystem | ● | ●●● | ○ | ●●● |

**Known gaps in the pathway**

- *(Persona, Pilot — C. Outcome and Success; D. Scope, Inclusion, and Trust)* What did MahaVISTAAR's own pilot reveal about which user interactions succeeded or failed — as distinct from the general UX fixes documented later in production (Units 17–19)?
- *(Persona, Scale — C. Outcome and Success)* Beyond the raw session count (Section 1), what decision was made about how to interpret engagement as a signal of success at Scale, and what would have changed that interpretation?
- *(Solution, Pilot — C. Model, Architecture, and Infrastructure)* Which architecture or model choice actually broke or needed adjustment during the pilot itself, as distinct from the production-scale changes documented later (Units 21–25)?
- *(Solution, Pilot — D. Data and Knowledge Readiness)* Which live data source was found stale, wrong, or low-quality during the pilot, and how was it resolved?
- *(Solution, Scale — D. Data and Knowledge Readiness)* Are there formal data SLAs or a data-currency governance process at Scale, beyond the four data relationships formalised before launch (Unit 38)?
- *(Institution, Define — F. Operating Model and Sustainability)* What decision, with a real alternative behind it, was made about the operating model before launch — as distinct from the cost anchor figures on their own (Section 1)?
- *(Institution, Pilot — B. Workforce and Change)* What did MahaVISTAAR observe about its own workforce and extension officers specifically during the pilot — as distinct from the general design principle set at Define (Unit 30) or the farmer-facing onboarding finding (Unit 20)?
- *(Institution, Scale — B. Workforce and Change)* Does frontline or extension-officer capability show signs of dependency rather than enhanced capacity at scale?
- *(Institution, Scale — D. Accountability, Liability, and Compliance)* When a farmer receives a wrong answer, what is the actual path from that error to a fix, and who holds liability? (Named as an open question in the source's own "Info gaps" section.)
- *(Institution, Scale — E. Data Stewardship)* Who reviews and refreshes data currency and stewardship on an ongoing cadence at Scale, distinct from who is accountable for accuracy at launch (Unit 29)?
- *(Ecosystem, Pilot — E. Resilience, Portability, and Contingencies)* Which ecosystem partner underperformed during the pilot, and was a contingency already identified?
- *(Ecosystem, Scale — B. External Data and Infrastructure Dependencies)* Have the four Define-stage data relationships (Unit 38) been formalised into SLAs or renegotiated as usage scaled?

---

## 3. Micro-innovations

### Persona

**1. Define the excluded user precisely, not as a demographic**
- Dimension: Persona · Stage: Explore · Type: Strategic Decision
- Decision: Target women farmers in Marathwada specifically — small trust circles, don't visit agriculture offices, receive contradictory advice from fertiliser sellers — rather than "farmers" or "rural citizens."
- Alternative considered: Broader demographic targeting ("farmers," "rural citizens," "agricultural users").
- Why: A precise user determines channel, model, data, language, and testing process; a vague demographic gives no fixed point to design against.
- Condition — applies when: exclusion is driven by language, literacy, device access, or institutional reach.

**2. Recognise that the registered farmer isn't always the decision-maker**
- Dimension: Persona · Stage: Explore · Type: Strategic Decision
- Relevant to: Government
- Decision: Design around who actually makes crop decisions, not who's listed in land records.
- Why: Many women farm the land while it stays registered in a husband's name — designing to the registry would target the wrong person.
- What this looked like here: Land-title records in Maharashtra frequently name the husband while the wife makes the sowing, spraying, and selling decisions.
- Condition — applies when: government registry data is being used as a proxy for "the user."

**3. Size the incremental value gap, not the technology, before committing**
- Dimension: Persona · Stage: Explore · Type: Strategic Decision
- Decision: Size the gap between the proposed AI use case and the current state — including doing nothing — before committing. That gap is the value being created.
- Alternative considered: Committing to AI on the basis of what the technology can do, without a sized comparison against the current state.
- Why: A human-only advisory model scales with staff; an AI model scales with usage. Where the staffing constraint is fixed, that difference is the case for AI.
- What this looked like here: Maharashtra's ~1 field officer per 2,000 farmers was the concrete constraint that made the case.
- Condition — applies when: a genuine current-state baseline exists and a limiting constraint can be named concretely.

**4. Design for inbound and outbound reach together, not in sequence**
- Dimension: Persona · Stage: Define · Also relevant at: Scale · Type: Strategic Decision
- Relevant to: Technologist
- Decision: Build inbound query-answering and proactive outbound advisory (crop-calendar alerts, weather-triggered pest alerts, pre-harvest timing) into the initial design together, not outbound as a later addition.
- Alternative considered: Launch inbound-only, add proactive push later.
- Why: A system that only waits for questions is less valuable than one that anticipates them, and an inbound-only build needs significant rearchitecting to add outbound once it's live.
- Condition — applies when: the use case has structured trigger data (weather, crop calendar, scheme deadlines).
- Before → After: Before: inbound-only, farmers call 155313 with questions. After: 17 lakh farmers/day reached proactively without making a call.

**5. Narrow scope to a single answerable question, not a domain**
- Dimension: Persona · Stage: Define · Type: Strategic Decision
- Decision: Scope the system to answer a single, concrete question type in one response — e.g., "should I harvest my paddy now?" requiring weather, market price, and crop-stage advisory assembled together — rather than "agricultural advisory" broadly.
- Why: A precise use case defines exactly which data sources, languages, and safety boundaries the build actually needs; a broad domain doesn't.
- Condition — applies when: the answer genuinely requires synthesis across multiple live sources within one response.

**6. Anticipate multilingual demand rather than retrofitting it**
- Dimension: Persona · Stage: Scale · Type: Tactical Decision
- Decision: Plan for languages beyond the launch language before going live.
- Why: Demand for additional languages surfaces after launch regardless; planning for it is materially cheaper than retrofitting it.
- What this looked like here: MahaVISTAAR launched Marathi-only; demand for Hindi, Bhili, and English emerged only after launch.
- Condition — applies when: the target region has meaningful linguistic diversity even if the pilot targets one language.

### Solution

**7. Justify AI specifically for real-time cross-institutional synthesis**
- Dimension: Solution · Stage: Explore · Type: Strategic Decision
- Decision: Use AI because a single farmer question routinely requires weather, soil, crop, and scheme data assembled and answered in seconds.
- Why: No human extension system can perform that synthesis at the moment of query; this is the specific failure mode AI addresses, not a general efficiency argument.
- Condition — applies when: the value is real-time synthesis across live institutional sources, not general efficiency.

**8. Don't over-commit to voice as the only channel**
- Dimension: Solution · Stage: Explore · Type: Failure and Fix
- Failure: Multiple deployments (cross-deployment observation) assumed voice alone would carry the full user journey.
- Fix: Recognise voice opens the door, but some users need to send images, some prefer text in noisy environments, some need human escalation the bot can't provide.
- Insight: Channel choice should be tested against the full task, not only against the population's literacy profile.
- Condition — applies when: a channel decision is made primarily from a literacy/device profile without testing the full task.

**9. Start bundled to learn fast; design so you can unbundle later**
- Dimension: Solution · Stage: Define · Type: Strategic Decision
- Relevant to: Government
- Decision: Launch on a bundled commercial provider (GPT-4.1/Azure OpenAI) for speed, while designing so it can later be unbundled to a self-hosted model.
- Alternative considered: Build self-hosted and unbundled from day one.
- Why: Speed of early deployment and learning outweighed day-one cost and control; the risk isn't starting bundled, it's staying bundled by accident once real users and stakes exist.
- Condition — applies when: speed of early deployment matters more than day-one cost or control.
- Condition — fails when: no deliberate unbundling decision is ever made once real users and stakes exist.
- Before → After: ~₹9.4/question (Nov 2025) → ~₹0.05/question self-hosted, a 180× reduction — achievable because modularity was designed in on day one.

**10. Dual-provider inference stack: abstraction layer + latency-over-queue-depth**
- Dimension: Solution · Stage: Define · Type: Toolkit Asset
- Toolkit asset: A provider-abstraction layer resolved at configuration time (not application code), paired with a policy that routes instantly to a fallback provider on capacity saturation rather than queuing.
- Purpose: Lets the deployment guarantee latency to the user while still being able to migrate or fall back between inference providers without touching application code.
- Reusable as-is: Documented in the MahaVistaar Architecture Note (contact: EkStep Foundation).
- Condition — applies when: voice interactions where seconds of silence read as failure, and a fallback provider is financially viable.

**11. Two-endpoint moderation, fully decoupled from the advisory engine**
- Dimension: Solution · Stage: Define · Type: Strategic Decision
- Relevant to: Technologist
- Decision: Run the moderation model (GPT-OSS Safeguard 20B) on entirely separate infrastructure from the advisory engine (Qwen3.5-27B).
- Alternative considered: A single integrated model handling both safety and advisory.
- Why: A safety layer that depends on the model it moderates is a single point of failure in the worst possible place; decoupling lets each fail independently.
- Condition — applies when: a safety layer must not go down together with the primary model.

**12. OpenAgriNet 7-layer architecture**
- Dimension: Solution · Stage: Define · Type: Toolkit Asset
- Toolkit asset: The foundational open-source architecture — Knowledge Engine, Memory Layer, Trust Layer, Agent Core, Action Gateway, Reach Layer, Learning Layer.
- Purpose: Gives a new deployment a DPG-licensed architectural starting point instead of designing the full layer stack from scratch.
- Reusable as-is: Freely available under DPG licence at openagri.net.

**13. Voiceera open-source orchestration platform**
- Dimension: Solution · Stage: Define · Type: Toolkit Asset
- Toolkit asset: A model-agnostic, language-agnostic, telephony-provider-agnostic orchestration platform.
- Purpose: Connects models into a deployable, maintainable system — the orchestration layer, not another model, is what most deployments actually lack.
- Reusable as-is: Via the OpenAgriNet ecosystem; applies specifically to Indian telephony infrastructure.

**14. Match telephony protocol to local network realities**
- Dimension: Solution · Stage: Define · Type: Tactical Decision
- Decision: Choose the telephony interface protocol based on actual local network conditions, not global best-practice defaults.
- Alternative considered: WebRTC, recommended in some global contexts.
- Why: Global recommendations don't account for local conditions like 8kHz audio, PSTN requirements, and regional accent variation.
- What this looked like here: WebSocket APIs were used instead of WebRTC for Indian telephony conditions.
- Condition — applies when: local telephony/network conditions diverge materially from where "best practice" recommendations were formed.

**15. Advisory corpus — chunked and metadata-tagged for tool-call retrieval**
- Dimension: Solution · Stage: Define · Type: Toolkit Asset
- Toolkit asset: ICAR and state-university crop/pest/scheme knowledge, structured for tool-call retrieval rather than free-text search.
- Purpose: Lets the advisory engine call structured knowledge as a tool at query time instead of relying on unstructured retrieval.
- Reusable as-is: Via OpenAgriNet; explicitly requires adaptation for different states' scheme structures.

**16. Bilingual Marathi↔English agricultural glossary**
- Dimension: Solution · Stage: Define · Type: Toolkit Asset
- Toolkit asset: A terminology bridge supporting ASR/TTS accuracy for crop, pest, scheme, and mandi terms.
- Purpose: Keeps domain-specific terms accurate across ASR/TTS without needing to translate the entire advisory corpus.
- Reusable as-is: Via OpenAgriNet; applies for Marathi-language deployments.

**17. Fix dead silence with a hold message plus a latency investment**
- Dimension: Solution · Stage: Pilot · Type: Failure and Fix
- Failure: 3–4 seconds of silence during a multi-source backend fetch read to callers as a dropped call.
- Fix: A hold message plus a latency-reduction investment brought fetch time to roughly one second.
- Insight: In voice, perceived failure is about silence, not absolute latency — the first fix can be UX, not only engineering.
- Condition — applies when: the system must call multiple live sources before answering, on voice.

**18. Keep the opening introduction under 30 seconds**
- Dimension: Solution · Stage: Pilot · Type: Tactical Decision
- Decision: Cap the opening message length rather than explaining full capability upfront.
- Why: Long introductions disengage users who called with a specific need.
- Condition — applies when: users call with a specific need and long preambles cause disengagement.

**19. Drop commercial-style follow-up nudging on a public-service line**
- Dimension: Solution · Stage: Pilot · Type: Tactical Decision
- Decision: Replace "Would you like to know more?" with a lighter close, or nothing at all.
- Why: A commercial engagement pattern reads oddly on a public service line — answering the question and stopping is often better.
- Condition — applies when: the service is a public institutional advisory line, not a commercial engagement product.

**20. "Use is training" — no separate onboarding step**
- Dimension: Solution · Stage: Pilot · Type: Tactical Decision
- Decision: Design the interface so that using it is the only training a farmer needs — no separate training programme.
- Why: The interface (a phone call) is simple enough that a farmer learns it in the act of calling and asking, rather than needing prior instruction.
- What this looked like here: Farmers called a number, asked a question, and got an answer — with no separate onboarding step before that.
- Condition — applies when: the interface is simple enough (a phone call) that no separate onboarding step is needed.

**21. Isolate moderation onto its own GPU to unlock TP=8**
- Dimension: Solution · Stage: Scale · Type: Tactical Decision
- Decision: Move the moderation model off the shared 8-GPU node onto a dedicated single H100, freeing all 8 main-node GPUs for the advisory LLM at TP=8.
- Alternative considered: Leaving the naive 4/2/2 GPU split in place.
- Why: Tensor parallelism only accepts power-of-two widths; a small auxiliary model sharing the node was blocking the step from TP=4 to TP=8.
- Condition — applies when: a small auxiliary model shares a node with a much larger primary model and blocks a step up in tensor-parallel width.
- Before → After: ~80 concurrent users/node, 2 of 8 GPUs stranded → ~160+ concurrent users/node for one additional H100.

**22. Prefix caching to avoid re-paying for conversation history**
- Dimension: Solution · Stage: Scale · Type: Toolkit Asset
- Toolkit asset: Prefix caching on the self-hosted stack so a multi-turn conversation's repeated system prompt and prior-turn context isn't recomputed each turn.
- Purpose: Cuts redundant compute on the largest share of cost — input tokens — for conversations that share a long, repeated prefix.
- Reusable as-is: A serving-stack configuration; any vLLM-style deployment with multi-turn, tool-heavy conversations can enable the equivalent.
- Condition — applies when: turns share a large repeated prefix — ~37% of notional input compute is skipped on a three-turn conversation.

**23. Little's Law capacity model for concurrency planning**
- Dimension: Solution · Stage: Scale · Type: Toolkit Asset
- Toolkit asset: A capacity formula — occupancy per active user = call rate × time per call — used to derive a node's safe concurrent-user ceiling.
- Purpose: Turns observed call-rate and call-duration data into a defensible concurrency ceiling, instead of guessing at a load test.
- Reusable as-is: Domain-general; a new deployment only needs its own call-rate and duration numbers.

**24. Cross-cutting production infrastructure checklist**
- Dimension: Solution · Stage: Scale · Type: Toolkit Asset
- Toolkit asset: A checklist spanning GPU cluster sizing for peak voice concurrency, HSMs/rate-limiting for security, an observability stack separate from the inference path, and redundant rural telephony connectivity.
- Purpose: Surfaces the infrastructure concerns that sit outside any single software layer, before they become production incidents.
- Reusable as-is: Structured by concern (compute/security/telemetry/resilience).

**25. Cost modelling framework**
- Dimension: Solution · Stage: Scale · Type: Toolkit Asset
- Toolkit asset: Azure-vs-self-hosted cost comparison, prefix-caching strategy, and GPU allocation guidance for a TP=4→TP=8 migration.
- Purpose: Gives a deployment approaching six-figure monthly volume a concrete basis for the bundled-vs-self-hosted decision, rather than a rough guess.
- Reusable as-is: Documented in the MahaVistaar Architecture Note; stated to apply at >100K queries/month.

### Institution

**26. Institutional authorisation is the critical path — nominate named ownership before any code is written**
- Dimension: Institution · Stage: Explore · Type: Strategic Decision
- Decision: Treat institutional authorisation and named ownership as the critical path preceding technical work, not a parallel task — starting with a named sponsor and nodal officers.
- Why: A vendor or technology team can't grant cross-departmental data-sharing authorisation on its own; without it, the technical build has nothing legitimate to connect to.
- What this looked like here: An Agri Secretary-level sponsor and named nodal officers across agriculture, IT, and field operations were the first concrete decisions.
- Condition — applies when: the deployment needs cross-departmental data-sharing authorisation no vendor can grant alone.
- Before → After: Data-sharing sign-off across the Department of Agriculture, four universities, IMD, 307 APMCs, and MahaDBT was secured before a single line of production code was written.

**27. The system speaks as the institution, never as an AI**
- Dimension: Institution · Stage: Define · Type: Strategic Decision
- Decision: The system must speak as the institution itself, not as an AI in its own right.
- Why: Farmer trust and accountability need to sit with a recognisable public institution, not a technology brand — a farmer who gets bad advice experiences it as the institution failing her, not the model.
- What this looked like here: The bot was named Vasudha and speaks explicitly as the Department of Agriculture, Maharashtra.
- Before → After: Framed as the pathway's central, structuring principle — every architecture, data-governance, and safety decision follows from it.

**28. Adversarial test set — 500 attack patterns**
- Dimension: Institution · Stage: Define · Type: Toolkit Asset
- Toolkit asset: A safety-testing bank covering in-scope, out-of-scope, sensitive/distress, abuse, complaint, and jailbreak scenarios, maintained as a living document.
- Purpose: Makes the system refuse well, not just answer well, in a domain where wrong answers carry institutional risk.
- Reusable as-is: Via the OpenAgriNet ecosystem, for agricultural advisory contexts.
- Condition — applies when: the goal is refusing well, not just answering well, in a domain where wrong answers carry institutional risk.

**29. Name the data owner before naming the data source**
- Dimension: Institution · Stage: Define · Type: Strategic Decision
- Decision: Give each data source formalised before launch a named institutional owner accountable for accuracy, update frequency, and correction.
- Why: Discovering an unowned data source at Pilot stage risks costing months; naming the owner upfront makes correction someone's job rather than nobody's.
- What this looked like here: ICAR, IMD, APMC, and NIPHM each had a named institutional owner before launch.
- Condition — applies when: multiple institutions or departments each hold a piece of the data the system depends on.

**30. Five data questions checklist**
- Dimension: Institution · Stage: Define · Type: Toolkit Asset
- Toolkit asset: Availability, Sovereignty, Accountability, Residency, and Update cadence — five questions to run against every candidate data source before any code is written.
- Purpose: Turns "is this data usable" from an intuition into a checklist that can be run against any candidate source consistently.
- Reusable as-is: Domain-general.

**31. Frame AI as extending human capacity, not replacing it**
- Dimension: Institution · Stage: Define · Type: Strategic Decision
- Decision: Position extension officers as owning the relationship, with the system handling the off-hours/on-demand question.
- Why: Workforce trust and adoption depend on staff not perceiving the system as a threat to their role.
- Condition — applies when: workforce trust and adoption depend on staff not perceiving the system as a threat to their role.

**32. Governance questions deferred to after launch produce a system nobody stands behind**
- Dimension: Institution · Stage: Define · Type: Failure and Fix
- Failure: In more than one deployment (cross-deployment observation), governance questions — who owns, who approves, who reviews failures — were left for after launch.
- Fix: Answer these explicitly inside the institution before launch.
- Insight: A technically functional system with no named institutional owner is one of the most common reasons a pilot never earns the credibility to scale.
- Condition — applies when: users will experience the system as the institution itself speaking.

**33. Staged, gated institutional testing before public launch**
- Dimension: Institution · Stage: Pilot · Also relevant at: Define · Type: Playbook
- Playbook: (1) builder/project team tests first, (2) a small institutional group tests next, (3) a wider institutional group tests across geographies, accents, and scenarios, (4) only then does a limited district-level rollout begin, ahead of wider expansion.
- Note: Fully outsourcing testing to a vendor is explicitly flagged as risky — the vendor's public credibility isn't the one on the line.
- Condition — applies when: the system will speak in the name of a public institution.

**34. Treat the operating model as a staffing question, not only a funding one**
- Dimension: Institution · Stage: Scale · Type: Strategic Decision
- Decision: Name, explicitly, who retrains the model, updates the advisory corpus, and manages vendor relationships.
- Why: "The people who built it" isn't a valid answer — the founding team is expected to move on, and the service has to survive that transition.
- Condition — applies when: the founding/build team is expected to move on and the service must survive that transition.

**35. Put a named owner on continuous improvement from day one**
- Dimension: Institution · Stage: Scale · Type: Strategic Decision
- Decision: Assign a named owner to monitor failed calls, misunderstood queries, drop-offs, unsafe responses, latency, cost, and data errors — and feed that back into the system on a regular cadence.
- Why: Without a named owner acting on it, the system degrades — often invisibly, until institutional trust is already damaged.
- Condition — applies when: query volume is large enough to be a genuine, continuous demand and failure signal.
- Before → After: 205,000+ monthly queries created a continuous signal that only improves the system if someone owns acting on it.

### Ecosystem

**36. Inventory what already exists before specifying what to build**
- Dimension: Ecosystem · Stage: Explore · Type: Playbook
- Relevant to: Social Sector/Enterprise
- Playbook: Before writing a specification, map every institution, dataset, and service already operating for the target population. Only then does feasibility become "what can be joined" rather than "what should we build."
- Note: Skipping this step is what produces a system that duplicates institutional data instead of connecting to it.
- Condition — applies when: multiple institutions already hold relevant data or services independently.

**37. A named, four-layer enabler map**
- Dimension: Ecosystem · Stage: Define · Type: Toolkit Asset
- Toolkit asset: A 54-item inventory of every funder, orchestrator, government body, research institution, language/AI model, live data feed, and knowledge document MahaVISTAAR draws on, organised into four layers — Institutional & Governance, Technology & AI, Structured Data, Knowledge & Documents.
- Purpose: Lets an evaluator demonstrate that a deployment connects rather than duplicates existing institutional assets, before any build decision is made.
- Reusable as-is: The four-layer structure (not the specific 54 entries) is what travels.
- Condition — applies when: an evaluator needs to evidence that a deployment connects rather than duplicates existing institutional assets.

**38. Federated data ownership with four named external relationships**
- Dimension: Ecosystem · Stage: Define · Type: Strategic Decision
- Decision: Federate with each legitimate external data owner rather than centralising their data into an AI-owned repository.
- Alternative considered: Centralising data into an AI-owned repository.
- Why: Sovereignty, DPDP Act compliance, and backend resilience all depend on data staying with organisationally distinct owners, connected at query time rather than copied.
- What this looked like here: Four relationships were formalised before launch — ICAR (crop advisories), IMD (weather), APMC (mandi prices), NIPHM (pest alerts).
- Condition — applies when: sovereignty, DPDP Act compliance, and backend resilience all matter.

**39. Data connector governance templates**
- Dimension: Ecosystem · Stage: Define · Type: Toolkit Asset
- Toolkit asset: Data-sharing MOU templates, consent architecture, and an institutional ownership model, validated under India's DPDP Act.
- Purpose: Gives a new deployment a starting legal/governance template for negotiating external data-sharing agreements, instead of drafting from zero.
- Reusable as-is: Via EkStep Foundation; explicitly requires customisation for specific departmental structures.

**40. Weather data gaps handled by fallback routing, not by fixing the data**
- Dimension: Ecosystem · Stage: Scale · Type: Failure and Fix
- Failure: Some weather data sources have geographic coverage gaps in rural Maharashtra, risking incomplete responses.
- Fix: Expanded search radii and graceful fallback logic built into the routing layer.
- Insight: When an external dependency has a structural limitation the deployment can't fix, the fix belongs in the system's tolerance for gaps, not in a demand for better data.
- Condition — applies when: a live external data feed has known, uneven geographic or temporal coverage.

**41. Architecture and field learning transfer; local trust mechanics don't**
- Dimension: Ecosystem · Stage: Scale · Also relevant at: Explore · Type: Strategic Decision
- Decision: Architecture, governance frameworks, language-pipeline methodology, and failure-mode library are the transferable unit — not the trust relationship with farmers.
- Condition — applies when: the receiving context can adapt an existing architecture rather than construct one from scratch.
- Condition — fails when: farmer-trust mechanics are assumed to transfer with the architecture.
- What this looked like here: Ethiopia's ATI and Amul/Sarlaben both reused the architecture; Ethiopia's team needed to locally adapt farmer-trust mechanics rather than import them directly.
- Before → After: Maharashtra's build took nine months, from scratch. Ethiopia's, drawing on that architecture, took three months; Amul's took three weeks.

**42. Prove state-level, then federate nationally**
- Dimension: Ecosystem · Stage: Scale · Type: Strategic Decision
- Decision: Sequence national federation (Bharat-VISTAAR) only after the state-level architecture is proven at scale, rather than launching both together.
- Why: An unproven architecture federated too early risks propagating failure modes nationally before they're understood locally.
- What this looked like here: Bharat-VISTAAR was announced in the Union Budget 2026-27, after MahaVISTAAR's state-level system was already proven.
- Condition — applies when: an institution wants both an early credible proof point and later national scaling.

---

## 4. Toolkits and playbooks

| Unit | Type | Purpose | Reuse condition |
|---|---|---|---|
| Toolkit (Unit 10) | Dual-provider inference stack | Guarantee latency while keeping providers swappable | Voice interactions where latency reads as failure, with a viable fallback provider |
| Toolkit (Unit 12) | OpenAgriNet 7-layer architecture | DPG-licensed architectural starting point | Want a foundation instead of designing from scratch |
| Toolkit (Unit 13) | Voiceera orchestration | Connects models into a deployable, maintainable system | Indian (or similar) telephony infrastructure needing agnostic orchestration |
| Toolkit (Unit 15) | Advisory corpus | Structured knowledge callable as a tool at query time | Agricultural advisory content — requires per-state adaptation |
| Toolkit (Unit 16) | Bilingual Marathi↔English glossary | Keeps domain terms accurate across ASR/TTS | Marathi-language deployments specifically |
| Toolkit (Unit 22) | Prefix caching | Cuts redundant input-token compute | Multi-turn conversations sharing a large repeated prompt/context prefix |
| Toolkit (Unit 23) | Little's Law capacity model | Converts call-rate/duration into a concurrency ceiling | Any multi-turn, tool-calling conversational serving stack |
| Toolkit (Unit 24) | Cross-cutting infra checklist | Surfaces infra concerns before they become incidents | Moving a voice-first, tool-orchestrating system from pilot to production |
| Toolkit (Unit 25) | Cost modelling framework | Basis for the bundled-vs-self-hosted decision | >100K queries/month |
| Toolkit (Unit 28) | Adversarial test set (500 patterns) | Makes the system refuse well, not just answer well | Agricultural advisory safety testing |
| Toolkit (Unit 30) | Five data questions checklist | Turns data usability into a checklist | Against any candidate data source, before writing code |
| Toolkit (Unit 37) | Four-layer enabler map | Evidences "connect, don't duplicate" | New deployment mapping existing institutional assets |
| Toolkit (Unit 39) | Data connector governance templates | Starting template for external data MOUs | Negotiating data-sharing agreements — requires per-department customisation |
| Playbook (Unit 33) | Staged, gated institutional testing | Builds institutional confidence before public exposure | Whenever a system will speak in the name of a public institution |
| Playbook (Unit 36) | Inventory-before-specification | Turns "what should we build" into "what can be joined" | Multiple institutions already hold relevant data/services |

---

## 5. Problem→solution patterns

| Problem | Root cause | Solution | Result | Condition |
|---|---|---|---|---|
| Calls felt like they'd dropped during a live lookup | 3–4 seconds of silence while fetching from multiple live sources | Hold message + latency-reduction investment (Unit 17) | Fetch time ~1 second; exchange completes in 12–15 seconds | Applies when the system must call multiple live sources before answering, on voice |
| Per-question AI cost was heading toward unsustainable scale | Token-based commercial pricing, with no architecture in place to migrate off it | Self-hosted, fine-tuned model with TP=4/TP=8 and prefix caching (Units 9, 21, 22) | 180× cost reduction, ₹9.4 → ₹0.05/question | Applies when volume is high/predictable enough; fails when volume is too low or spiky |
| A GPU node stranded 2 of 8 GPUs under a power-of-two tensor-parallelism constraint | A naive 4/2/2 split across advisory/moderation/idle | Dedicated single-GPU moderation node, freeing 8 GPUs for TP=8 (Unit 21) | Roughly doubled concurrency for one added GPU | Applies when a small auxiliary model shares a node with a much larger primary model under a TP constraint |
| Weather data had geographic coverage gaps causing incomplete responses | Weather-station network density insufficient in some rural areas | Expanded search radii and graceful fallback routing (Unit 40) | Fewer failed lookups despite unfixed underlying data gaps | Applies when the upstream data source itself can't be fixed |
| A technically working system that no official would stand behind | Governance questions (ownership, approval, escalation) deferred to after launch | Answer ownership, approval, and escalation questions inside the institution before launch (Units 26, 27, 32) | Institutional confidence to stand behind the system publicly | Applies whenever the system will be experienced by users as the institution itself speaking |
| Institutions couldn't see their own knowledge gaps until users started asking | No prior demand signal exposed missing or incomplete institutional data | Route query volume back as a continuous signal to the owning institution, with a named owner acting on it (Unit 35) | 205,000+ monthly queries surfaced gaps that had been invisible | Applies when volume is large enough to be a genuine signal, and a named recipient exists to act on it |
| An inbound-only build becomes a rearchitecting project the moment proactive alerts are needed | Outbound wasn't designed in from the start | Design inbound and outbound together at Define stage (Unit 4) | 17 lakh farmers/day reached proactively without a later rebuild | Applies when the use case has structured trigger data (weather, crop calendar, scheme deadlines) |

---

## 6. Retrieval guide

- *"Who exactly are we building this for?"* → Unit 1, Unit 2
- *"Why does AI make sense here instead of just hiring more field staff?"* → Unit 3, Unit 7
- *"Should we build for voice only?"* → Unit 8
- *"Should we launch inbound-only and add proactive alerts later?"* → Unit 4
- *"What's the minimum viable scope for a first pilot?"* → Unit 5
- *"Should we build everything ourselves or start on a commercial API?"* → Unit 9
- *"How do we stop a single vendor from locking us in?"* → Unit 9, Unit 10
- *"How do we keep our safety layer from going down with the main model?"* → Unit 11
- *"Is there an existing architecture we can start from?"* → Unit 12, Unit 13
- *"What telephony protocol should we use?"* → Unit 14
- *"Calls feel like they're dropping during a live lookup — what do we do?"* → Unit 17
- *"Do farmers need a training programme before they can use this?"* → Unit 20
- *"Who needs to sign off before we go live?"* → Unit 26, Unit 27
- *"How do we test this without breaking public trust on day one?"* → Unit 33
- *"What data questions should we ask before writing any code?"* → Unit 29, Unit 30
- *"How do we handle the MOU/consent side of data sharing?"* → Unit 39
- *"What would actually transfer if we tried this in another state or country?"* → Unit 41
- *"Who owns this system once the people who built it move on?"* → Unit 34, Unit 35
- *"Are frontline staff going to see this as a threat to their jobs?"* → Unit 31
- *"What's actually driving our LLM costs, and can we bring them down?"* → Unit 9, Unit 22, Unit 25

---

Provenance appendix (contributor-only)

| Source file | Covers | Notes |
|---|---|---|
| MahaVISTAAR — A Diffusion Pathway (People+AI, July 2026) | Section 1 (all fields); Units 1–35, 38, 42 (primary content); Sections 5–6 | Primary source |
| Executive Summary — MahaVISTAAR (People+AI) | Reading guide framing; confirms Section 1 cost/scale figures and core lesson | Confirms, doesn't add |
| OANDiffusionPathway.pdf | Units 36–37, 41; confirms Section 1 downstream-adopter record | Primary source for the 54-enabler map |
| MahaVistaar_Production_Serving_Architecture_Internal_Note.pdf | Units 21–24, 40 | Primary source for GPU/cost/resilience detail |
