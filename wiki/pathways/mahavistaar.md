# Agricultural Advisory System for Farmers

## 0. Reading guide

This is a **vertical pathway**: a single state government deployment, documented end to end — from the structural problem it responds to, through its production serving architecture down to the GPU, to the cost economics that shaped its next scaling decision. MahaVistaar is not an adopter of a pre-existing playbook; it is the pioneer deployment that the OpenAgriNet (OAN) pathway itself was built from. Everything documented here was built without a prior template, which is also why the Architecture and Operating Model dimensions are unusually deep — they carry the level of technical and cost detail that later adopters (Bharat-VISTAAR nationally, Amul's Sarlaben in Gujarat, OpenAgriNet Ethiopia) were able to reuse rather than rediscover.

**Why this pathway exists.** A Marathi-speaking farmer's question — "my paddy is standing, should I harvest now?" — needs weather data, market prices, and crop-stage advisory that sit in three different institutions, none of which were built to talk to each other. Separately, the farmer most likely to need that answer is also the farmer least likely to reach it through a portal: low literacy, a basic phone, no reliable internet. MahaVistaar exists because those two problems — institutional fragmentation and structural exclusion — do not resolve on their own, and because voice, not an app, is the access channel that dissolves literacy, device, and language barriers simultaneously. The throughline across this material is that AI here is a delivery and coordination layer sitting above institutions that remain the actual authority — the Department of Agriculture, the state agricultural university, IMD — not a replacement for them.

**How to navigate**
- If you're deciding whether the problem is real before building anything — start with Problem Orientation.
- If you're designing the serving stack itself — start with Architecture; this is where almost all of the load-bearing detail sits.
- If you're scoping what data the system should touch and how — start with Data.
- If you're trying to get institutional buy-in and ownership right — start with Institution.
- If you're mapping who needs to be involved — start with Ecosystem, particularly the 54-enabler map (Unit 26).
- If you're worried about serving cost or GPU capacity — go straight to Operating Model, Units 24–26.

---

## 1. Pathway identity

| Field | Detail |
|---|---|
| Deployment/Pathway name | MahaVistaar — State Agricultural Advisory Platform |
| Sector | Agriculture (crop, livestock, and fisheries advisory), extending to scheme/subsidy discovery and market information |
| Actor type | Government (Department of Agriculture, Government of Maharashtra), Technologist/orchestration (EkStep Foundation, COSS, Samagra, Artha Global), Academic/Research (IIT Mumbai, IISc, Vassar Labs), National infrastructure (Bhashini, AI4Bharat, India AI Mission) |
| Geography | Maharashtra, India — India's second-largest state by GDP, 152 lakh hectares of Kharif cropland |
| Population served | Farmers statewide across crops, livestock, and fisheries; 342,000+ unique users, 1.67 million+ questions answered, 791,000+ sessions, 17 lakh farmers reached daily through proactive voice alerts (as of early 2026) |
| Stage reached | Production, scaling — live and operating for roughly nine months at the point these sources were written; a self-hosted inference migration is complete, and the next scaling step (TP=8, moderation isolated onto its own node) is planned but not yet executed |
| Contributing organisation | Department of Agriculture, Government of Maharashtra (lead); EkStep Foundation, COSS, Samagra, Artha Global (orchestration and implementation); Karya, Bhashini, AI4Bharat (language and AI); IIT Mumbai, IISc, Vassar Labs (research); ICAR-affiliated universities — MPKV, VNMAU, PDKV, GAVASU (knowledge) |
| Source deployments | MahaVistaar is the origin deployment of the OAN pathway, not a downstream adopter. It became the architectural and governance basis that Bharat-VISTAAR (India's national agricultural DPI), Amul's Sarlaben (Gujarat dairy cooperative), and OpenAgriNet Ethiopia each drew on directly, deploying in three weeks and three months respectively rather than MahaVistaar's original nine. |
| Dimensions covered | Architecture is documented exhaustively — serving topology, GPU sizing, and cost economics down to the rupee — reflecting the production internal note as a source. Institution and Ecosystem are covered at the level of principle and enabler-mapping, not day-to-day operational detail. Workforce carries no units of its own: extension officers appear only as a named user class, never as a locus of their own decisions. Outcome-level impact (yield, income, decision quality) is undocumented throughout; what's documented is usage and satisfaction. |
| Last updated | Not stated in the source; the internal note's data is anchored to November 2025 and describes a Langfuse integration planned for "this week," suggesting the underlying material is current to roughly early 2026 |
| Contact for peer connection | Not stated in the source |
| Summary | MahaVistaar is a Maharashtra state government platform that unifies fragmented agricultural advisory — university knowledge, weather, market prices, scheme status — behind a single voice-and-text interface, with institutions remaining the cited authority behind every answer. Built from scratch in nine months with no prior playbook, it has since migrated its serving stack from commercial per-token inference to a self-hosted GPU cluster, cutting cost per question by roughly 180× while becoming the architectural template three other OAN deployments reused directly. |

---

## 2. Coverage grid

Density: ●●● = 3+ units · ●● = 2 units · ● = 1 unit · ○ = 0 units

| Dimension | Explore | Define | Pilot | Scale |
|---|---|---|---|---|
| Problem Orientation | ●●● | ● | ● | ○ |
| Architecture | ○ | ●●● | ●● | ● |
| Data | ○ | ●●● | ● | ○ |
| Institution | ● | ●●● | ○ | ○ |
| Ecosystem | ○ | ●●● | ○ | ○ |
| Workforce | ○ | ○ | ●●● | ○ |
| Operating Model | ● | ○ | ●● | ○ |

### Known gaps in the pathway

- *(Problem Orientation, Scale)* Beyond usage numbers — users, questions answered, satisfaction scores — does MahaVistaar track any outcome, like a change in yield, income, or decision quality, that shows real impact on a farmer's life?
- *(Architecture, Pilot)* What did the dialect-variation and API-instability issues Maharashtra worked through during the nine-month build actually look like day to day, and how were they fixed?
- *(Architecture, Scale)* Now that the TP=8 change and the dedicated moderation node are actually running, does the measured concurrency gain match the roughly 2× projection?
- *(Data, Define)* What does farmer consent for accessing their own registry data — Farmer ID, Farm ID, crop-sown records — actually involve in practice? How is it obtained, and can a farmer withdraw it?
- *(Institution, Define)* Beyond naming an Agri Secretary sponsor and nodal officers, what did building trust with farmers actually require day to day, and how was scepticism handled?
- *(Institution, Scale)* Is there a standing governance body overseeing the live MahaVistaar deployment today, or does it still rest informally with the original project team?
- *(Institution, Define)* Did government procurement rules create any real obstacle when building or running MahaVistaar — and if so, how was it navigated?
- *(Institution, Scale)* Who has the authority to decide what MahaVistaar can and cannot claim on behalf of the state, and what actually happens when that line gets crossed?
- *(Ecosystem, Define)* Are ICAR, IMD, AgriStack, and the state universities contributing their data under a formal agreement, an informal arrangement, or a public mandate — and what would break if any one of them pulled out?
- *(Workforce, Pilot)* Beyond freeing up extension officers' time, what specific new skills or day-to-day changes do they actually need — and is any of that documented, or just assumed?
- *(Operating Model, Scale)* Who bears MahaVistaar's ongoing operating costs beyond the initial build, and what keeps institutional partners contributing their data over time?
- *(Operating Model, Scale)* Today, who actually decides when the model needs retraining, when the advisory corpus needs updating, or when a guardrail needs changing — is that a named role, a team, or still the original pilot team?
- *(Operating Model, Pilot)* When a farmer gets a wrong or harmful answer — wrong pest treatment, wrong scheme eligibility, wrong mandi price — what's the actual path from that error being found to it being fixed?
- *(Operating Model, Pilot)* Now that Langfuse is live, what do the real fallback frequency, blended cost, and per-flow latency numbers actually show, compared with the modelled figures in this note?

---

## 3. Micro-innovations

### Problem Orientation

**1. Frame the problem as institutional fragmentation, not absence of knowledge**
- Dimension: Problem Orientation
- Stage: Explore
- Type: Strategic Decision
- Decision: Treated the core problem as fragmentation across institutions, not a shortage of agricultural knowledge. A farmer's harvest-timing question needs weather data, market prices, and crop-stage advisory — each held by a different institution, none of which was built to talk to the others.
- Why it matters: If you frame the problem as "farmers lack knowledge," you'll try to produce more knowledge. That doesn't help — the knowledge already exists. What's missing is a way to pull it together and hand it to the farmer in one place.
- Alternative considered: Not documented in the source.
- Condition — applies when: The knowledge already exists across multiple institutions, but no single one of them can answer the farmer's actual question alone.
- Before → After: Before — a university, a weather service, a market system, and a scheme department each held one piece of the answer, with no shared route between them. After — one voice or text query reaches all of them at once.
- Source: OAN Diffusion Pathway.

**2. Frame inclusion as a structural failure of reach, not a failure of the farmer**
- Dimension: Problem Orientation
- Stage: Explore
- Type: Strategic Decision
- Decision: Treated exclusion as a property of the system, not the farmer. The knowledge is technically available on portals and PDFs, but reaching it needs literacy, a smartphone, reliable internet, and fluency in the portal's language — things most of the intended population doesn't have.
- Why it matters: If you assume the farmer just needs to try harder or be taught to use the portal, you build the wrong fix. The actual fix is to remove the barriers, not train around them.
- Alternative considered: Not documented in the source.
- Condition — applies when: The population that needs a service most is also the population least equipped to use the channel that currently delivers it.
- Before → After: Not documented in quantified terms.
- Source: OAN Diffusion Pathway.

**3. Voice as the architectural response to inclusion, not a channel choice**
- Dimension: Problem Orientation
- Stage: Explore
- Type: Strategic Decision
- Decision: Treated voice as the actual fix for exclusion, not one option among several. A farmer who can't read doesn't need to read. A farmer without a smartphone can call a number. Literacy, device type, and language all stop mattering at once.
- Why it matters: An app or a better website only fixes one barrier at a time — you'd still need separate fixes for literacy, language, and connectivity. Voice removes all of them in a single move.
- Alternative considered: A text-first or app-first interface with voice added later.
- Condition — applies when: Literacy, device, and language barriers are all present at once, so no single non-voice fix would cover more than one of them.
- Before → After: Not documented in quantified terms; illustrated by a Marathi-speaking farmer on a basic feature phone reaching an advisory that was previously unreachable.
- Source: OAN Diffusion Pathway.

**4. Institutional credibility, not algorithmic credibility, as an explicit design requirement**
- Dimension: Problem Orientation
- Stage: Explore
- Type: Strategic Decision
- Decision: Built the system on the premise that people trust institutions, not algorithms. For AI to be adopted at population scale, it has to carry the traceable authority of a trusted institution — not present itself as the authority.
- Why it matters: An answer with no institutional backing looks, to a farmer, like a guess from an unfamiliar chatbot. Trust in an algorithm has to be earned one interaction at a time; trust in a known institution is already there. Skipping this means adoption has to be won the hard way, answer by answer.
- Alternative considered: Not documented in the source.
- Condition — applies when: The target population already trusts specific public institutions, and a new AI interface can either borrow that trust or undermine it.
- Before → After: Not documented in the source.
- Source: OAN Diffusion Pathway.

**5. Inbound and outbound as two designed modes of interaction**
- Dimension: Problem Orientation
- Stage: Define
- Type: Strategic Decision
- Decision: Built the system to work two ways at once. Inbound: farmers call a short code (155313) with questions. Outbound: the system proactively pushes advisories — pest alerts like pink bollworm detection, pre-monsoon weather warnings, roughly 15 stage-based advisories across the crop calendar — to registered farmers before they ask.
- Why it matters: An inbound-only system only helps a farmer who already knows to ask. For time-sensitive risks — a pest outbreak, a coming storm — waiting for the farmer to think of the question can be too late.
- Alternative considered: An inbound-only system that responds to questions but never initiates contact.
- Condition — applies when: The advisory is time-sensitive enough that waiting for the farmer to ask would be too late to act on.
- Before → After: Before — a platform that only answered when asked. After — a platform that also reaches out first. Completing this shift was treated as the difference between the system being useful and being indispensable.
- Source: OAN Diffusion Pathway; mahavistaar.md reference.

**6. Organise use cases by what farmers are trying to do, not by department**
- Dimension: Problem Orientation
- Stage: Pilot
- Type: Failure and Fix
- Failure: An early version organised use cases by the department's own structure — which system or team held which answer. That didn't match how farmers actually thought about their problem.
- Fix: Regrouped use cases by what farmers are actually trying to do — asking about a sick crop, checking scheme eligibility, tracking an application — instead of by which department holds the answer.
- Insight: A system is easier to adopt when it's organised around the user's own way of thinking about their problem, not the institution's internal filing system.
- Condition — applies when: The system pulls answers from multiple departments, each of which categorises its knowledge differently from how an end user would ask the question.
- Source: mahavistaar.md reference.

### Architecture

**7. Seven-layer reference architecture separating interface, moderation, reasoning, knowledge, live data, and DPI foundation**
- Dimension: Architecture
- Stage: Define
- Type: Toolkit Asset
- Toolkit asset: A layered reference architecture — User Layer, Interface Layer, Moderation Layer, AI Decision Engine (reasoning, orchestration, response), Knowledge & Scientific Models, Live Data & Institutional Sources, and the DPI Foundation — with each layer's job kept strictly separate from the others.
- Why it matters: Without this separation, replacing one piece — say, the moderation model, or adding a new channel like WhatsApp — would mean touching the advisory logic itself. Keeping the layers separate means each one can be swapped, scaled, or upgraded on its own.
- Reusable as-is: A structural template for any similar multi-institutional advisory system, regardless of which specific models or data sources fill each layer.
- Condition — applies when: Multiple institutional data sources and multiple channels (voice, chat, push) need to converge into one response pipeline.
- Source: MahaVistaar Production Serving Architecture (Internal Note); OAN Diffusion Pathway.

**8. Independent moderation layer, fully decoupled from the advisory engine**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Decision: Ran query moderation as a separate model (GPT-OSS Safeguard 20B) — checking for off-topic content, safety issues, and prompt injection — completely apart from the main advisory model. In voice, this check happens inside the speech-recognition step rather than as a separate call.
- Why it matters: If moderation and advisory logic were the same model, a successful prompt injection or off-topic query could reach the part of the system that speaks with institutional authority. Keeping them apart means a compromised or confused query gets stopped before it can produce an answer that looks official.
- Alternative considered: A single model handling both moderation and advisory generation.
- Condition — applies when: The advisory model's answers carry institutional authority and can't risk being compromised by unsafe or off-topic content reaching it.
- Before → After: Not documented in the source.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**9. Agentic tool-orchestration with hard grounding guardrails**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Decision: Required that no query is ever answered from the model's own memory — every claim has to come from a verified tool call. Enforced fixed query flows (for example: Pest → Glossary → Advisory) instead of letting the model decide its own retrieval steps.
- Why it matters: A model answering from memory can sound confident and still be wrong, with no way to trace where the claim came from. Forcing every answer through a real tool call means every claim has a traceable, checkable source behind it.
- Alternative considered: Allowing the model to answer simple queries directly from its own training.
- Condition — applies when: The system's credibility depends on every factual claim being traceable to a specific institutional source.
- Before → After: Not documented in the source.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**10. Federated data architecture: institutions keep their data, the AI connects to it at query time**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Decision: Farmer, weather, market, and scheme data are never copied into a central store. The orchestrating agent connects directly to each institution's database at query time, pulls what it needs, and assembles the prompt locally — only the finished prompt, never the raw data, is sent to the LLM, and the result is attributed back to its institutional source. This was treated explicitly as a sovereignty decision, not a technical footnote: the design was built to align with India's DPDP Act by construction, not bolted on through a later compliance audit. Handling sensitive government data (land records, scheme eligibility) also required dedicated secure connectivity to meet NIC hosting requirements.
- Why it matters: Asking an institution to hand its data into a central repository it doesn't control is often a non-starter — many departments simply won't agree to it. If raw records were sent to the LLM provider itself, that would also risk breaching both institutional sovereignty expectations and DPDP obligations. Keeping raw data inside government systems, and sending only the assembled prompt out, is what satisfies data control and regulatory compliance at the same time, instead of solving them separately.
- Alternative considered: Centralising all institutional data into one MahaVistaar-owned store.
- Condition — applies when: Institutions need to keep ownership and control of their own data as a condition of taking part, and the data involved is sensitive enough that compliance can't be an afterthought.
- Before → After: Not documented in the source.
- Source: OAN Diffusion Pathway; mahavistaar.md reference.

**11. Dual-provider serving topology: self-hosted primary, commercial fallback strictly on infrastructure faults**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Decision: Every generative call goes through a wrapper pointed at one of two providers — a self-hosted vLLM primary, and a shared Azure OpenAI fallback — with failover triggered only by genuine infrastructure faults (timeouts, server errors, malformed payloads, concurrency overflow). It is never triggered by a low-quality answer or a client-side error.
- Why it matters: Self-hosted infrastructure alone risks slow responses or downtime during traffic spikes. A commercial API alone is too expensive to run at full production volume. Running both together gets the low cost of self-hosting in the common case and the reliability of a managed provider in the rare case — without paying full commercial price all the time.
- Alternative considered: A single-provider serving stack.
- Condition — applies when: Cost-sensitive, everyday serving needs to coexist with a hard reliability guarantee during traffic spikes.
- Before → After: Not documented in the source.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**12. Latency over queue depth: overflow spills to fallback instantly rather than making users wait**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Decision: When the self-hosted endpoint's concurrency limit is full, the system doesn't make the request wait in line — it routes instantly to the Azure fallback, at the same API surface.
- Why it matters: A farmer on a voice call won't tolerate a long pause any more than a person would on a normal phone call. This choice means a busy moment costs money (the fallback is pricier), not the farmer's patience.
- Alternative considered: Queuing overflow requests for the cheaper self-hosted path instead of paying for the more expensive fallback right away.
- Condition — applies when: How fast the user gets an answer matters more than minimising the cost of occasional overflow traffic.
- Before → After: Not documented in the source.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**13. Tensor parallelism (TP=4) to convert weight-replication overhead into pooled concurrency**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Decision: Split the 27-billion-parameter model's weights across four H100 GPUs (TP=4) instead of running it on one. A single 80GB GPU has only about 26GB left for active requests once the model's weights are loaded — enough for roughly a dozen at once. Splitting the model across four GPUs frees up roughly 260GB for active requests instead — about eight times the concurrency, on the same total hardware.
- Alternative considered: Running the model on a single GPU, or copying the full model across GPUs without splitting it.
- Condition — applies when: A model's weights alone take up most of a single GPU's memory, so the number of requests it can serve at once — not raw processing power — is what limits it.
- Before → After: Not documented as a before/after on MahaVistaar itself, but stated as a general rule: the same tensor-parallelism decision will matter again if a bigger model (40B, 70B) gets fine-tuned in future.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**14. Prefix caching as the dominant cost lever, discovered from the prior commercial-API spend**
- Dimension: Architecture
- Stage: Pilot
- Type: Failure and Fix
- Failure: On the earlier commercial deployment (Azure OpenAI/GPT-4.1), input tokens made up roughly 80% of total spend, and caching wasn't applied aggressively. Roughly 37% of the compute on a three-turn conversation was simply the previous turn's prompt being paid for again.
- Fix: Moved to a self-hosted setup with prefix caching turned on, so that repeated computation is skipped instead of re-paid.
- Insight: In a multi-turn conversation where the prompt and its accumulated context dominate the token count, caching that shared prefix is not a minor tweak — it's the single biggest lever on cost, after the choice of model itself.
- Condition — applies when: A conversation re-sends a large shared prompt across multiple turns, and the provider doesn't cache it aggressively.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**15. A fine-tuned smaller open-source model outperforming a larger commercial API on internal evaluation**
- Dimension: Architecture
- Stage: Pilot
- Type: Strategic Decision
- Decision: Fine-tuned a 27B-parameter open-source model specifically for this advisory task. It scored higher on the team's own evaluation (94%) than the larger commercial API it replaced (91%) — while costing a fraction as much to run.
- Why it matters: A bigger general-purpose model isn't automatically better at a narrow, specific job. Once the task is well-defined, a smaller model trained specifically for it can beat a larger one at a much lower running cost.
- Alternative considered: Continuing to rely on a larger general-purpose commercial API.
- Condition — applies when: The task is narrow and well-defined enough that a smaller, purpose-built model can match or beat a larger general model on it.
- Before → After: Before — GPT-4.1 via Azure OpenAI, general-purpose. After — a fine-tuned 27B open-source model, scoring higher on the internal evaluation at a fraction of the cost.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**16. GPU allocation stranded by power-of-two tensor-parallel widths; moderation isolated to unlock full width on the main model**
- Dimension: Architecture
- Stage: Scale
- Type: Failure and Fix
- Failure: The current 8-GPU node runs the main model on 4 GPUs and moderation on 2, leaving 2 idle — because splitting a model across GPUs only works in powers of two (2, 4, or 8), so the main model can't use the freed-up GPUs without moderation giving up its own first.
- Fix (planned, not yet executed): Move moderation onto its own single-GPU node — it only ever needed a fraction of that headroom — freeing all 8 GPUs on the main node for the advisory model.
- Insight: Because a wider split frees up more than a proportional amount of memory for active requests, the resulting gain is expected to be more than a clean doubling.
- Condition — applies when: A lightweight secondary model shares a node with a primary model whose ideal GPU split is blocked by the secondary model's allocation.
- Before → After: Before — 8-GPU node, ~80 concurrent users, 2 GPUs idle. After (projected) — moderation moved off, ~160+ concurrent users on the main node.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

### Data

**17. Live institutional data accessed as tools at query time, never pre-loaded into the model**
- Dimension: Data
- Stage: Define
- Type: Strategic Decision
- Decision: Connected the system to weather, farm records, scheme status, soil data, and local extension contacts as live calls made at the moment of the query, rather than loading any of this into the model itself.
- Why it matters: If this data were baked into the model instead, the model would keep confidently repeating an old price or an outdated application status long after it changed — with no way to know it was wrong. Fetching live data at query time means the answer is only ever as old as the last real update.
- Alternative considered: Pre-loading a static snapshot of institutional data into the model's context or training data.
- Condition — applies when: The underlying data changes over time and the model must never answer from a stale copy.
- Before → After: Not documented in the source.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**18. Bilingual glossary bridges the language gap without translating the full advisory corpus**
- Dimension: Data
- Stage: Define
- Type: Toolkit Asset
- Toolkit asset: A two-way Marathi↔English farming-term glossary that lets the system reason over English-language source material while still speaking to the farmer in Marathi — without translating the entire advisory corpus first.
- Reusable as-is: A lightweight language-bridging piece for any advisory system where the source material and the farmer's language don't match.
- Condition — applies when: The authoritative knowledge base is mostly in one language, the population speaks another, and translating the whole corpus isn't practical.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**19. Graceful fallback for data sources with geographic coverage gaps**
- Dimension: Data
- Stage: Pilot
- Type: Failure and Fix
- Failure: Some live data sources, especially weather stations, have real gaps in geographic coverage — a query from certain locations would otherwise come back empty.
- Fix: Widened the search radius and built fallback logic so a nearby data point is used when the exact location has no direct coverage.
- Insight: Assume external data sources have coverage gaps by default, and design the fallback in from the start, rather than finding out through a failed query.
- Condition — applies when: A system depends on external data sources that weren't built with full geographic coverage in mind.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**20. Adversarial test sets maintained for moderation defense**
- Dimension: Data
- Stage: Define
- Type: Toolkit Asset
- Toolkit asset: A maintained set of up to 500 adversarial attack patterns, used to keep testing the moderation layer's resistance to prompt injection and unsafe content.
- Why it matters: A moderation layer that was only checked once, at launch, gives no guarantee it still holds after later changes. A standing test set lets every future change be checked against the same bar.
- Reusable as-is: A concrete starting benchmark size and habit for any deployment that needs to validate its moderation layer, before and after changes.
- Condition — applies when: A moderation layer gates access to a system carrying institutional authority, where a failure has real consequences.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

### Institution

**21. Long-term institutional transformation, not a one-time project**
- Dimension: Institution
- Stage: Explore
- Type: Strategic Decision
- Decision: Framed the deployment as building a long-term, state-level advisory capability — a shared rail for trusted information, a feedback loop that lets real usage improve policy over time, and growth without adding staff at the same rate — rather than commissioning a one-time technology platform.
- Why it matters: A project has an end date and a handover. Once it's "done," nobody is left responsible for updating the corpus, watching the feedback loop, or improving the system. Framing it as an ongoing capability, not a project, keeps a mandate and a budget alive for that continuing work.
- Alternative considered: Treating the deployment as a bounded technology project with a fixed delivery date and no further institutional evolution expected.
- Condition — applies when: The system's value depends on institutions continuing to evolve around it, not just receiving a finished product.
- Before → After: Not documented in the source.
- Source: OAN Diffusion Pathway; mahavistaar.md reference.

**22. Nominate named, accountable institutional ownership before building**
- Dimension: Institution
- Stage: Explore
- Type: Strategic Decision
- Decision: Made the first concrete step the nomination of an Agri Secretary sponsor and nodal officers across agriculture, IT, and field operations — naming who owns this before any technical work began.
- Why it matters: Without a named sponsor, nobody has the standing to approve data-sharing agreements, decide what the AI is allowed to say on the institution's behalf, or take responsibility when something goes wrong. Naming an owner first means those questions have an answer before they come up, instead of after.
- Alternative considered: Beginning technical build-out before formal institutional ownership was assigned.
- Condition — applies when: The system will speak with an institution's name and authority on every answer, making a vendor-led or ownerless start unworkable.
- Before → After: Not documented in the source.
- Source: OAN Diffusion Pathway.

**23. Institution remains the advisory authority; the AI layer never becomes the source**
- Dimension: Institution
- Stage: Define
- Type: Strategic Decision
- Decision: Every answer cites the Department of Agriculture, the state agricultural university, or IMD as its source. The AI delivers and coordinates; it never becomes the authority itself.
- Why it matters: Farmers trust the university or the department, not an unfamiliar piece of software. If the AI presented itself as the authority, it would be asking farmers to extend trust to something with no track record, instead of borrowing trust that already exists.
- Alternative considered: Presenting advisory answers as the AI system's own output, without institutional attribution.
- Condition — applies when: Farmer trust depends on the credibility of institutions the farmer already trusts, not on trust in an algorithm.
- Before → After: Not documented in the source.
- Source: OAN Diffusion Pathway.

**24. Cross-institutional data-sharing alignment as the core system-leadership task**
- Dimension: Institution
- Stage: Define
- Type: Strategic Decision
- Decision: Treated getting universities, weather services, market systems, and scheme platforms to align on data-sharing — and agreeing what the AI could and couldn't do with that data — as the real leadership work of building MahaVistaar, not a technology procurement exercise.
- Why it matters: Without this alignment, the system can be fully built and still have nothing to say — each institution can simply decline to share, and there's no data to answer with. Getting this agreement is what makes the rest of the build possible at all.
- Alternative considered: Commissioning a platform without first securing this cross-institutional alignment.
- Condition — applies when: The system's value depends on data held across institutions with no existing sharing agreement between them.
- Before → After: Not documented in the source.
- Source: OAN Diffusion Pathway.

**25. Negotiate data-sharing agreements before the technical build starts**
- Dimension: Institution
- Stage: Define
- Type: Strategic Decision
- Decision: Treated data-sharing agreement timelines as the critical path — to be settled before technical construction began, not run alongside it.
- Why it matters: If the agreements are still being negotiated once building starts, the technical team ends up waiting on something outside their control, at the point they can least afford to wait.
- Alternative considered: Starting technical build in parallel with data-sharing negotiations, expecting them to conclude in time.
- Condition — applies when: The system depends on data controlled by multiple institutions with no pre-existing agreement, and integration work would otherwise stall waiting for it.
- Before → After: Not documented in the source.
- Source: mahavistaar.md reference.

### Ecosystem

**26. Fifty-four named enablers organised into four layers**
- Dimension: Ecosystem
- Stage: Define
- Type: Toolkit Asset
- Toolkit asset: A complete map of 54 named enablers behind MahaVistaar, sorted into four layers — Institutional & Governance, Technology & AI, Data, and Knowledge & Documents.
- Why it matters: A project spanning this many institutions makes it easy to simply forget an entire category of partner — a data provider, a knowledge source — until the gap shows up later as a missing feature. Mapping all four layers up front catches that before it becomes a problem.
- Reusable as-is: A checklist of partner categories for any similar multi-institutional advisory system, independent of which organisation fills each slot.
- Condition — applies when: Assembling or auditing the full partner landscape for a state-scale, multi-sector advisory platform.
- Source: OAN Diffusion Pathway.

**27. Connect what already exists rather than building it fresh**
- Dimension: Ecosystem
- Stage: Define
- Type: Strategic Decision
- Decision: Treated the project's job as a connecting layer — letting 54 pre-existing systems (schemes, publications, weather services, language models) be found, combined, and delivered as one answer — rather than building fresh versions of any of them.
- Why it matters: Rebuilding what already exists wastes time and risks duplicating something an institution already maintains and trusts. Connecting to it instead gets to a working system much faster, and keeps the institution's own data authoritative.
- Alternative considered: Building new versions of institutional data sources or knowledge bases instead of connecting to existing ones.
- Condition — applies when: The knowledge a farmer needs already exists somewhere in the institutional landscape, just not in a form one query can reach.
- Before → After: Not documented in the source.
- Source: OAN Diffusion Pathway.

**28. Design participation so each actor's own interest is served, not just the shared mission**
- Dimension: Ecosystem
- Stage: Define
- Type: Strategic Decision
- Decision: Designed each partner's role so it served that partner's own interest directly, instead of counting on shared enthusiasm for the mission to keep them involved.
- Why it matters: Partners come from very different worlds — government, academia, a cooperative — with different incentives. Goodwill fades under pressure; a partner who gets something concrete out of participating keeps showing up even when priorities shift elsewhere.
- Alternative considered: Coordinating partners mainly through appeal to the shared public-good mission of the project.
- Condition — applies when: Partners have genuinely different mandates and incentives, such that goodwill alone is unlikely to hold them over time.
- Before → After: Not documented in the source.
- Source: mahavistaar.md reference.

### Workforce

**29. Extension officers' role shifts from sole information source to freed capacity for higher-value work**
- Dimension: Workforce
- Stage: Pilot
- Type: Tactical Decision
- Decision: Let farmers get routine answers directly from the system, instead of requiring an extension officer to answer every question themselves.
- Why it matters: An officer who spends their day answering the same routine questions has no time left for the harder cases that actually need a person. Freeing that time up is what lets officers focus where they add the most value.
- Alternative considered: Not documented in the source.
- Condition — applies when: Frontline workers spend a large share of their time on routine, repeatable questions a system could answer directly.
- Before → After: Before — officers travelled long distances answering questions across crops, livestock, schemes, and markets, carrying scattered notes and paperwork. After — farmers get routine answers directly from the system, freeing officer time for higher-value work.
- Source: mahavistaar.md reference.

**30. Use itself is training — no separate onboarding layer for farmers**
- Dimension: Workforce
- Stage: Pilot
- Type: Strategic Decision
- Decision: Built no separate training step for farmers. A farmer calls the number, asks a question, and gets an answer — nothing to learn first. Farmers were seen moving naturally from simple questions (weather, pest) toward more complex ones (scheme applications, credit, grievances) just through using it.
- Why it matters: Requiring training before access adds a barrier for exactly the population this system is meant to reach — people with limited literacy and no history with formal digital services. Making the first use as simple as making a phone call removes that barrier entirely.
- Alternative considered: Building a formal onboarding or training process before farmers could use the system.
- Condition — applies when: The interaction itself (a phone call) is already familiar enough that no separate training is needed.
- Before → After: Not documented in the source.
- Source: mahavistaar.md reference.

**31. Population-scale usage as an institutional feedback loop**
- Dimension: Workforce
- Stage: Pilot
- Type: Strategic Decision
- Decision: Treated the total volume of farmer queries as a feedback signal in its own right. 205,000+ monthly queries made previously invisible demand visible, letting institutions see their own knowledge gaps — where farmers' questions went unanswered — continuously, not just through occasional surveys.
- Why it matters: A periodic survey only catches a gap if someone thinks to ask about it. Watching real query patterns at scale surfaces gaps institutions didn't know to look for, as they happen.
- Alternative considered: Not documented in the source.
- Condition — applies when: A system gets enough real query volume that patterns in unanswered or frequent questions become a meaningful signal about where institutional knowledge is thin.
- Before → After: Not documented in the source.
- Source: OAN Diffusion Pathway; mahavistaar.md reference.

### Operating Model

**32. Bounded start, run as a time-boxed pilot with a review gate before scaling**
- Dimension: Operating Model
- Stage: Explore
- Type: Playbook
- Playbook:
  1. Start with a bounded scope — Kharif crops, selected districts, one or two languages — instead of trying for statewide, all-crop, all-language coverage from day one.
  2. Run that bounded scope as an eight-week pilot, treated as a learning phase, not a launch event.
  3. Review what the pilot actually revealed, not just whether it worked.
  4. Only then decide whether and how to scale.
- Why it matters: A big-bang launch that fails, fails everywhere at once, and it's hard to tell which part broke. A bounded pilot fails small, and tells you exactly what to fix before you scale it up.
- Condition — applies when: There's no existing proof the underlying pipeline works, and a smaller, time-boxed launch can generate that proof faster than a broad one.
- Before → After: Not documented in the source.
- Source: OAN Diffusion Pathway.

**33. Migrate from commercial per-token inference to a self-hosted GPU cluster to escape a runaway cost trajectory**
- Dimension: Operating Model
- Stage: Pilot
- Type: Failure and Fix
- Failure: Running entirely on GPT-4.1 via Azure OpenAI, spend in November 2025 was roughly ₹2 lakh a day, heading toward roughly ₹6 lakh a day as adoption grew — a cost curve that would have made staying on commercial per-token pricing unworkable at scale.
- Fix: Moved to a self-hosted cluster on 4×H100 GPUs, keeping Azure only as a backup for overflow traffic. Six months of GPU rental for that cluster cost ₹25 lakh; a planned larger build-out is projected at roughly ₹2 crore a year — well under the roughly ₹18 crore a year the Azure path was heading toward.
- Insight: The real question was never whether to move to self-hosted — it was how far to go, and how much reliability to keep in reserve. Once the move was made, the commercial path's job changed: from doing most of the work, to being an expensive backup used rarely.
- Condition — applies when: Per-token commercial cost grows with usage in a way a self-hosted cluster's mostly-fixed cost doesn't, and it's worth paying more occasionally for reliability rather than under-building capacity or making users wait.
- Before → After: Before — roughly ₹9 per question, fully exposed to per-token cost growth. After — roughly ₹0.05 per question at full use (about a 180× drop), with the commercial path kept only as a bounded-cost backup.
- Source: MahaVistaar Production Serving Architecture (Internal Note).

**34. Learn how much traffic the system can handle by watching it live, instead of guessing upfront**
- Dimension: Operating Model
- Stage: Pilot
- Type: Playbook
- Playbook:
  1. Turn on usage tracking (Langfuse), already set up at the time of writing.
  2. Watch, for two weeks, how often the self-hosted setup gets full and starts sending calls to the backup instead — that's the number that shows whether today's limit is set right.
  3. Slowly raise the number of farmers allowed to talk to the system at the same time (in steps: 120, then 140), checking each time that answers aren't getting slower.
  4. Lock in the real "how many farmers at once" number the data supports, instead of the current provisional guess of 60–70.
- Why it matters: "How many farmers can the system talk to at the same moment" is a real number with a cost on both sides. Set it too low, and farmers get pushed to the expensive backup, or turned away, more than they need to be. Set it too high, and the system slows down or struggles under real load. Watching real usage first means the final number reflects what the system can actually handle, not a guess made before anyone had used it.
- Condition — applies when: Nobody yet knows how many farmers the system can safely talk to at once, and guessing wrong in either direction — too cautious or too aggressive — costs real money or real reliability.
- Before → After: Not documented as completed; this is the plan at the time of writing, not yet carried out.
- Source: MahaVistaar Production Serving Architecture (Internal Note).


## 4. Toolkits and playbooks

| Asset | Unit | Reuse condition |
|---|---|---|
| Seven-layer reference architecture | Toolkit (Unit 7) | Use when multiple institutional data sources and channels need to converge into one response pipeline. |
| Bilingual glossary (Marathi↔English) | Toolkit (Unit 18) | Use when the authoritative knowledge base and the served population's language differ, and full corpus translation is impractical. |
| Adversarial test sets for moderation | Toolkit (Unit 20) | Use when validating a moderation layer's robustness before and after changes. |
| Fifty-four-enabler map | Toolkit (Unit 26) | Use when assembling or auditing the full partner landscape for a state-scale, multi-sector advisory platform. |
| Eight-week pilot, then structured review | Playbook (Unit 32) | Use when a new deployment context has no prior evidence of how the pipeline will behave at scale. |
| Watch-then-set traffic limits | Playbook (Unit 34) | Use when nobody knows how many users the system can safely handle at once, and guessing wrong is costly either way. |

---

## 5. Problem→solution patterns

| Problem | Root cause | Solution | Result | Condition |
|---|---|---|---|---|
| Commercial inference spend was on a runaway trajectory (~₹2 lakh/day heading toward ~₹6 lakh/day) | Per-token commercial pricing with input tokens at ~80% of cost and caching under-utilised | Migrated to a self-hosted vLLM cluster with aggressive prefix caching | Cost per question fell from ~₹9 to ~₹0.05 — roughly a 180× reduction | Applies whenever per-token commercial inference cost scales with adoption faster than a self-hosted cluster's largely fixed cost |
| An 8-GPU node was stranding 2 GPUs, capping the main model at TP=4 | Tensor parallelism only accepts power-of-two widths, and moderation's allocation blocked the main model from stepping to TP=8 | Move moderation onto its own dedicated single-H100 node, freeing all 8 GPUs for the main model | Concurrency projected to more than double (~80 → ~160+ users/node) | Applies whenever a lightweight secondary model shares a node with a primary model whose ideal tensor-parallel width is blocked by that allocation |
| Some locations returned no weather data | Live weather-station sources have real geographic coverage gaps | Expanded search radii and built graceful fallback/routing logic | Not quantified in the source | Applies whenever a system depends on external data sources without complete geographic coverage |

---

## 6. Retrieval guide

*"Why does this problem need an AI system at all — couldn't better websites or more staff solve it?"* → Unit 1, Unit 2

*"Why voice specifically, instead of an app or a better website?"* → Unit 3

*"Does the system only answer when asked, or does it reach out too?"* → Unit 5

*"How should we organise use cases — by our own department structure, or some other way?"* → Unit 6

*"How do we keep farmers trusting the system rather than trusting the AI itself?"* → Unit 4, Unit 23

*"What should the overall system architecture look like?"* → Unit 7

*"How do we stop unsafe or off-topic queries from reaching the main model?"* → Unit 8

*"How do we make sure every answer is actually grounded in real data, not the model's own guess?"* → Unit 9

*"Should we centralise all the institutional data, or leave it where it is?"* → Unit 10

*"How do we get both low cost and high reliability out of our serving stack?"* → Unit 11, Unit 12

*"Our model is large — how do we actually get good concurrency out of it?"* → Unit 13

*"Where should we look first if our self-hosted inference costs are higher than expected?"* → Unit 14

*"Should we use a big commercial API or fine-tune our own smaller model?"* → Unit 15

*"We have GPUs sitting idle — why, and what do we do about it?"* → Unit 16

*"How do we bridge farmers' language with English-language source material without translating everything?"* → Unit 18

*"Who actually needs to be involved in a project like this?"* → Unit 26, Unit 27

*"What's the very first institutional step before any building starts?"* → Unit 22

*"Should this be a one-time technology project or something longer-term?"* → Unit 21

*"When should we lock down data-sharing agreements relative to the technical build?"* → Unit 25

*"How do we keep partners committed beyond just sharing a mission?"* → Unit 28

*"What happens to extension officers once farmers can get answers directly?"* → Unit 29, Unit 30

*"How do we know if the system itself is actually improving how institutions work, not just answering questions?"* → Unit 31

*"Should we try to cover every crop, district, and language at launch?"* → Unit 32

*"What's the right way to run a first pilot before deciding to scale?"* → Unit 32

*"How much does something like this actually cost to run, and how did that shape the architecture?"* → Unit 33

*"How do we figure out our real capacity limits without guessing upfront?"* → Unit 34
