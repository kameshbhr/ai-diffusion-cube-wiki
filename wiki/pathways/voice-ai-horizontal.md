# Voice AI for Inclusion — Horizontal Pathway

---

## 0. Reading guide

This pathway is **horizontal** — it cuts across sectors and compresses lessons from seven deployments (MahaVISTAAR, Bharat Vistaar, Amul/Sarlaben, Jal Jeevan Mission Assam, the Bhili low-resource language effort, Lend A Hand, and the India–Africa exchange with Crane AI Labs) into one reusable set of voice-AI decisions.

### Why this pathway exists

Voice AI demos are easy; reliable voice AI services are not. The gap between the two is the hidden institutional, safety, data-governance, and operating work that never shows up in a demo but determines whether a deployment survives contact with real users. The single most important principle running through every deployment in this pathway: when a voice agent fails publicly, users and officials read that failure as **the institution's failure, not the model's**. Refusal design, ownership questions, staged testing, and cost tracking all exist to make sure that failure, when it happens, is one the institution can own and recover from — not one that ends the deployment.

### How to navigate

- If you're deciding **whether** to use voice AI at all → start with the Problem Orientation units.
- If you're **mid-build** and stuck on a stack decision → the Architecture and Data units, or jump to the problem→solution patterns.
- If you're **about to go live** → the Institution units, and the safety toolkit.
- If something is **already breaking** → the problem→solution patterns first, then the specific unit it points to.
- If you want the fastest orientation → the retrieval guide, or the coverage grid to see where the dense knowledge actually sits.

---

## 1. Pathway identity

| Field | Value |
|---|---|
| Deployment / Pathway name | Voice AI for Inclusion — Horizontal Pathway |
| Sector | Cross-sector (agriculture, water, workforce/livelihoods) |
| Actor type | Cross-actor — relevant to Government (approval and ownership authority), Technologist (architecture, safety, and data decisions), and Social Sector/Enterprise (cost, workforce, and operating-model decisions) |
| Geography | India, with an India–Africa reference case |
| Population served | Rural and low-literacy users excluded from existing digital/human service channels — women farmers, dispersed interns, rural households, low-resource language speakers |
| Stage reached | Pilot through Scale (varies by source deployment) |
| Contributing organisation | EkStep Foundation |
| Source deployments | MahaVISTAAR, Bharat Vistaar, Amul/Sarlaben, Jal Jeevan Mission Assam, Bhili low-resource language effort, Lend A Hand, India–Africa exchange (Crane AI Labs) |
| Dimensions covered | All seven dimensions are touched somewhere, but coverage is heavily Define/Pilot-weighted — see the coverage grid. Explore stage is only answered for Problem Orientation, Architecture, and (partially) Institution; the other four dimensions have no Explore-stage unit yet. |
| Last updated | 2026-07-03 |
| Contact for peer connection | EkStep Foundation |
| Summary | Synthesises practitioner experience across seven voice AI deployments in India and Africa to compress the "implementation tax" — the hidden institutional, safety, and operating work between a voice AI demo and a reliable service channel — for the next adopter. |

---

## 2. The coverage grid

Symbols show density only — how many tagged units exist per cell.

**Legend:** ●●● = 3+ units · ●● = 2 units · ● = 1 unit · ○ = 0 units

| Dimension ↓ / Stage → | Explore | Define | Pilot | Scale |
|---|---|---|---|---|
| **Problem Orientation** | ● | ● | ○ | ● |
| **Architecture** | ● | ●●● | ●●● | ●● |
| **Data** | ○ | ●● | ● | ○ |
| **Institution** | ● | ● | ○ | ○ |
| **Ecosystem** | ○ | ●● | ○ | ○ |
| **Workforce** | ○ | ● | ○ | ● |
| **Operating Model** | ○ | ○ | ● | ●● |

### Known gaps in the pathway

- *(Data, Explore)* What data would this system need, and does any of it already exist in usable form?
- *(Institution, Explore)* Who inside the institution has to personally want this to work, and do they know yet — by name?
- *(Ecosystem, Explore)* Who else has tried to solve this for this population, and what happened?
- *(Workforce, Explore)* Who are the frontline people who reach this user, and how do they see AI?
- *(Operating Model, Explore)* What would this cost to set up and run annually, at least as an order of magnitude?
- *(Problem Orientation, Define)* What is the one question a user will ask that this system must answer, and what does success look like in binary terms?
- *(Problem Orientation, Pilot)* Which user interactions are actually failing during the pilot — is it a scope problem or a quality problem?
- *(Data, Pilot)* When a data source starts giving stale or wrong answers, how quickly does its owner fix it — and what's the response time?
- *(Data, Scale)* Which data source is breaking under scale, and is there a formal SLA in place for it?
- *(Institution, Pilot)* What has the institution seen fail publicly, and did it own the failure or disown it?
- *(Institution, Scale)* Has the institution absorbed this as an ongoing service — budget line, named owner, review cadence — or is it still the project team's problem?
- *(Ecosystem, Pilot/Scale)* Which partner is underperforming, and is there a named alternative to switch to?
- *(Workforce, Pilot)* Are the intended users actually using this system, or working around it?
- *(Workforce, Scale)* Is there evidence that users are becoming more capable over time, or just more dependent on the system?
- *(Operating Model, Define)* What does this need to demonstrate for the institution to commit to a real pilot, and by when?

---

## 3. Micro-innovations

### Problem Orientation

**1. Define the excluded user before the channel**
- Dimension: Problem Orientation
- Stage: Explore
- Type: Strategic Decision
- Decision: Start from a precisely named excluded user (e.g., "women farmers in remote districts who rely on small trust circles and cannot easily visit an agriculture office"), not a generic persona ("farmers") and not the technology.
- Alternative considered: Starting from "we want to use voice AI" and working backward to a user.
- Condition — applies when: Any deployment where voice is being proposed as an access solution.
- Condition — fails when: The channel choice is already fixed for non-access reasons and user definition is a downstream design input rather than a channel decision.
- Before → After: Before — deployments that started with the technology "romanticized voice" and discovered post-launch that some users needed images, some needed text in noisy environments, some needed human escalation. After — user definition made the channel, model, data, and testing decisions fall out naturally.
- Source: Cross-deployment synthesis (MahaVISTAAR, Lend A Hand, JJM Assam).

**2. Design for multichannel, not voice-only**
- Dimension: Problem Orientation
- Stage: Define
- Type: Strategic Decision
- Decision: Map the full user journey before committing to voice as the only channel.
- Alternative considered: Treating voice as the complete front end.
- Condition — applies when: The user journey includes steps voice can't complete alone (e.g., document upload, complex written record).
- Condition — fails when: The interaction is fully self-contained in a spoken exchange.
- Before → After: Not documented in the source.
- Source: Cross-deployment synthesis.

**3. Multilingual demand surfaces after launch, not before**
- Dimension: Problem Orientation
- Stage: Scale
- Type: Failure and Fix
- Failure: Several deployments launched in one language and found the helpline receiving calls in others.
- Fix: Anticipate multilingual need at Define stage, not Scale.
- Insight: Retrofitting language support is architecturally harder than designing for it from the start — it touches ASR/TTS selection, data, and testing all over again.
- Condition — applies when: The user population's language distribution wasn't fully mapped before launch.
- Source: Cross-deployment synthesis.

### Architecture

**4. Compare voice honestly against the current channel and its failure mode**
- Dimension: Architecture
- Stage: Explore
- Type: Tactical Decision
- Decision: Benchmark voice AI against the channel it's actually replacing (human calling, paper forms, nothing) and name that channel's specific failure mode — not an idealised "no channel" baseline.
- Alternative considered: Assuming voice AI is additive rather than replacing a specific, already-failing channel.
- Condition — applies when: An institution already runs some version of this interaction through another channel.
- Condition — fails when: No prior channel exists at any scale to compare against.
- Before → After: Before — Lend A Hand's two human callers couldn't reach thousands of interns at the needed frequency. After — voice AI extended reach for structured, repeated interactions while humans stayed for complex/sensitive cases.
- Source: Lend A Hand.

**5. Start bundled to learn fast; design so unbundling is possible later**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Relevant to: Technologist, Government
- Decision: Begin with a bundled full-stack provider for speed; treat unbundling as a deliberate later decision, not an accident of inertia.
- Alternative considered: Unbundling from day one (slower, requires more technical capacity you may not have yet).
- Condition — applies when: Limited technical capacity at the outset and speed-to-pilot matters more than long-term control.
- Condition — fails when: Vendor lock-in risk is unacceptable from day one.
- Before → After: Before — staying bundled "by accident" leaves institutions dependent on a single vendor's pricing and roadmap once real users and stakes exist. After — a deliberate unbundling decision point preserves control without sacrificing pilot speed.
- Source: Cross-deployment synthesis.

**6. WebSocket APIs over WebRTC for Indian telephony conditions**
- Dimension: Architecture
- Stage: Define
- Type: Tactical Decision
- Decision: Match infrastructure choice to local network reality rather than external best practice.
- Alternative considered: WebRTC (more commonly recommended in general voice-AI literature).
- Condition — applies when: Deploying over Indian telephony networks with variable connectivity.
- Condition — fails when: Operating on high-bandwidth, stable connections where WebRTC's advantages apply.
- Before → After: Before — call quality failures. After — stable 8kHz performance.
- Source: Cross-deployment synthesis.

**7. Design for refusal, not just response**
- Dimension: Architecture
- Stage: Define
- Type: Toolkit Asset
- Relevant to: Government, Technologist
- Toolkit asset: A safety and stress-test bank covering in-scope questions, out-of-scope questions, sensitive/distress scenarios, abuse or harassment, romantic/inappropriate prompts, complaints about officials or policy, jailbreak attempts, and questions requiring human escalation — run before public launch.
- Reusable as-is: another adopter can lift the category list and adapt it to their own mandate without rebuilding it from scratch.
- Condition — applies when: The agent is public-facing and could plausibly receive off-mandate or adversarial input.
- Source: Cross-deployment synthesis.

**8. Follow a fixed order when selecting a model**
- Dimension: Architecture
- Stage: Define
- Type: Playbook
- Playbook: Before committing to a model, work through five questions in order — does it support the target language conversationally (not just via translation)? Is it fast enough for the channel (telephony vs. app)? Has it been used in a comparable sector or population before? Does it give enough control for the long term (can you retrain, fine-tune, or switch providers)? What will it cost at the volumes expected at scale, not just at pilot volumes?
- Note: The order matters — language and latency are disqualifying if they fail; cost is evaluated last, since pricing a model that doesn't clear the first two gates is meaningless.
- Condition — applies when: Any deployment selecting a voice/ASR/TTS/LLM model for a live channel.
- Source: Cross-deployment synthesis.

**9. Only build your own model if existing models clearly fail and you have the talent to maintain one**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Relevant to: Technologist
- Decision: Treat building a proprietary ASR/TTS/language model as the exception, not the default — justified only when both conditions hold: existing models demonstrably fail the use case, and the team has the ongoing ML talent to maintain a model over time.
- Alternative considered: Building a custom model because existing options feel generic or because the team wants full control.
- Condition — applies when: No existing model, after real testing, clears the bar for the specific language, population, or channel.
- Condition — fails when: Either condition is missing — existing models are adequate, or the team lacks sustained ML capacity — since deployments that proceed anyway tend to abandon or outsource the custom model within months.
- Source: Cross-deployment synthesis.

**10. Dead silence during backend fetch reads as a dropped call**
- Dimension: Architecture
- Stage: Pilot
- Type: Failure and Fix
- Failure: 3–4 seconds of silence while a backend call resolves felt like a failure to the user.
- Fix: A hold message ("Please wait while I fetch that information").
- Insight: Voice UX fails on the order of seconds, not minutes — a much tighter tolerance than most teams design for initially.
- Condition — applies when: Any backend call in the response path takes more than ~2 seconds.
- Source: MahaVISTAAR.

**11. Use lab metrics to reject, real users to select**
- Dimension: Architecture
- Stage: Pilot
- Type: Tactical Decision
- Decision: Two-step model evaluation — technical metrics (WER, latency, noise cancellation) filter candidates; real user and institutional testing makes the final call.
- Alternative considered: Treating vendor lab benchmarks as sufficient proof of readiness.
- Condition — applies when: Any model selection decision for a live user-facing channel.
- Condition — fails when: The use case has no meaningful dialect/accent variation the lab test wouldn't have captured.
- Before → After: Before — one deployment passed technical evaluation and then struggled with a district dialect absent from the test set. After — the two-step process catches this before public exposure.
- Source: Cross-deployment synthesis.

**12. Keep introductions under 30 seconds**
- Dimension: Architecture
- Stage: Pilot
- Type: Tactical Decision
- Decision: Cap the voice agent's opening introduction at 30 seconds before handing control to the user.
- Alternative considered: A longer, fully explanatory introduction covering everything the system can do.
- Condition — applies when: The channel is voice-only and users are calling in with a specific need already in mind.
- Before → After: Long introductions caused users to hang up or talk over the system before it finished; shorter introductions let users reach their actual question faster.
- Source: Cross-deployment synthesis.

**13. Drop the reflexive "would you like to know more" follow-up nudge**
- Dimension: Architecture
- Stage: Pilot
- Type: Tactical Decision
- Decision: Remove automatic follow-up prompts offering more information after the user's question is answered, unless the user asks for more.
- Alternative considered: Always offering a follow-up nudge, on the assumption that more information is always welcome.
- Condition — applies when: Users are calling with a narrow, specific need and want to end the call once it's met.
- Before → After: The nudge added call length and friction without a corresponding increase in useful information delivered.
- Source: Cross-deployment synthesis.

**14. Use yes/no questions instead of open-ended ones where accuracy matters most**
- Dimension: Architecture
- Stage: Pilot
- Type: Tactical Decision
- Decision: Where getting an accurate answer matters more than natural conversation flow, phrase the system's questions to elicit yes/no or short, constrained responses rather than open-ended ones.
- Alternative considered: Open-ended questions throughout, for a more natural conversational feel.
- Condition — applies when: ASR accuracy on open-ended, free-form speech is a known weak point for the deployment's language or telephony conditions.
- Before → After: Open-ended questions produced more ASR misrecognitions that propagated into wrong answers; constrained questions reduced that error path.
- Source: Cross-deployment synthesis.

**15. Unbundling triggers become concrete at scale**
- Dimension: Architecture
- Stage: Scale
- Type: Strategic Decision
- Relevant to: Technologist, Social Sector/Enterprise
- Decision: Revisit the bundled architecture once cost and control arguments turn into real numbers (e.g., TTS cost per million calls vs. per thousand).
- Condition — applies when: Query volume has grown enough that per-unit costs are now material to the operating budget.
- Source: Cross-deployment synthesis.

**16. Voiceera — build the orchestration layer, not just the model layer**
- Dimension: Architecture
- Stage: Scale
- Type: Toolkit Asset
- Relevant to: Technologist
- Toolkit asset: An open-source orchestration layer designed to be model-agnostic, language-agnostic, and telephony-provider-agnostic — connecting to different ASR/TTS/LLM providers and telephony partners without rebuilding the integration each time.
- Reusable as-is: Adopters can connect their own model and telephony choices to the same orchestration layer rather than building bespoke integration code for each new component.
- Condition — applies when: The gap blocking scale isn't the absence of capable models, but the absence of a layer that lets those models be swapped, combined, or upgraded without a rebuild.
- Source: Cross-deployment synthesis.

### Data

**17. Keep the data layer separate from the AI layer via APIs**
- Dimension: Data
- Stage: Define
- Type: Tactical Decision
- Decision: The AI system consumes data from accountable sources through standardized APIs; it does not own the data.
- Alternative considered: Direct/hardwired connections to source databases (faster to build).
- Condition — applies when: Multiple data sources with different owners and update cadences; government deployments where data accountability must stay with named departments.
- Condition — fails when: A single, stable, internally-owned data source with no departmental accountability separation requirement.
- Before → After: Before — data errors required rebuilding the bot's prompt architecture. After — data errors are fixed by the data owner without touching the AI layer.
- Source: MahaVISTAAR.

**18. Data requirement size follows the use case, not a generic AI-readiness assumption**
- Dimension: Data
- Stage: Define
- Type: Strategic Decision
- Decision: Size the data requirement to what the specific use case needs.
- Alternative considered: Assuming any AI deployment needs a large training dataset before it can start.
- Condition — applies when: The use case is narrow and well-defined enough to name its exact data need.
- Before → After: Jal Jeevan Mission Assam needed only phone numbers and five questions; MahaVISTAAR needed multiple live, governed sources. Same framework, very different data footprints — both correct for their use case.
- Source: JJM Assam, MahaVISTAAR.

**19. Read speech and studio audio don't represent telephony conditions**
- Dimension: Data
- Stage: Pilot
- Type: Failure and Fix
- Failure: Models trained/tested on read speech and studio-quality audio underperform on conversational, telephony-quality audio.
- Fix: Train or test on actual phone-line audio conditions before deployment.
- Insight: Voice AI evaluation environments need to match the deployment channel, not just the language.
- Condition — applies when: The deployment channel is a phone line.
- Source: Bhili low-resource language effort.

### Institution

**20. Institutional backing is the trust mechanism, not the AI itself**
- Dimension: Institution
- Stage: Explore
- Type: Strategic Decision
- Relevant to: Government, Social Sector/Enterprise
- Decision: Design the system's identity and framing around the institution that stands behind it, on the understanding that users extend trust to the institution, not to the technology.
- Alternative considered: Presenting the system primarily as an AI tool or innovation, on the assumption that novelty or capability alone earns trust.
- Condition — applies when: The target users have limited pre-existing trust in unfamiliar digital tools but do trust a specific institution (government department, cooperative, NGO).
- Before → After: Users who were wary of "a bot" engaged readily once the system was framed as a service channel of an institution they already trusted.
- Source: Cross-deployment synthesis (MahaVISTAAR).

**21. Name who owns the channel before users arrive**
- Dimension: Institution
- Stage: Define
- Type: Strategic Decision
- Relevant to: Government
- Decision: Before launch, the institution answers: who owns this channel, who approves what the agent says, who decides what it must not say, who reviews failures, who updates the knowledge base, who handles complaints, who is accountable for a wrong answer.
- Alternative considered: Deferring these questions until after launch, once the system is "technically working."
- Condition — applies when: The voice agent will be perceived by users as speaking on behalf of an institution.
- Before → After: Before — a technically functional system officials wouldn't stand behind, because they were never asked to before users arrived. After — named ownership and approval authority in place pre-launch.
- Source: Cross-deployment synthesis.

### Ecosystem

**22. Shortlist and test multiple vendors in parallel, not sequentially**
- Dimension: Ecosystem
- Stage: Define
- Type: Tactical Decision
- Decision: Run 2+ vendors side by side under similar conditions during the pilot.
- Alternative considered: Testing and committing to one vendor at a time, sequentially.
- Condition — applies when: Switching cost is still low (pre-scale) and more than one credible vendor exists for the component in question.
- Before → After: Before — sequential vendor testing means discovering a vendor's limits only after you're already committed to them. After — parallel testing gives real comparison under similar conditions and competitive pressure on cost/quality before lock-in.
- Source: Cross-deployment synthesis.

**23. Low-resource language work is ecosystem assembly, not a data task**
- Dimension: Ecosystem
- Stage: Define
- Type: Strategic Decision
- Decision: Treat near-zero-resource language deployment (no large speech dataset, no ASR/TTS model, limited digital text) as requiring a full assembled ecosystem: a convening authority, native speakers, annotators, linguistic experts, model builders, hosting infrastructure, a real-world application, and a neutral orchestrator.
- Alternative considered: Treating it as a data-collection sprint that a small technical team can run alone.
- Condition — applies when: The target language has no meaningful existing ASR/TTS or digital text corpus.
- Source: Bhili low-resource language effort.

### Workforce

**24. Stage institutional testing before any public rollout**
- Dimension: Workforce
- Stage: Define
- Type: Playbook
- Relevant to: Government
- Playbook: Move through builder/project team → small institutional group → wider institutional group (across geographies, accents, scenarios) → limited user rollout. Each stage needs its own gate before proceeding.
- Note: Do not outsource testing entirely to the vendor — the vendor's credibility isn't the one at stake publicly.
- Condition — applies when: The system speaks on behalf of an institution and any public failure would be read as an institutional failure.
- Before → After: MahaVISTAAR moved to citizen-facing rollout only after internal testing and a limited district-level rollout before wider expansion.
- Source: MahaVISTAAR.

**25. Frame voice AI as capacity extension, not replacement**
- Dimension: Workforce
- Stage: Scale
- Type: Strategic Decision
- Relevant to: Government, Social Sector/Enterprise
- Decision: Voice AI handles structured, scalable, repeated interactions; humans stay for sensitive, complex, ambiguous, or high-risk cases. Frame it this way explicitly to frontline staff.
- Alternative considered: Framing voice AI as reducing headcount need, which risks frontline resistance and mis-scoped design.
- Condition — applies when: Frontline staff have an existing relationship with the population being served that the system would otherwise seem to replace.
- Source: Cross-deployment synthesis.

### Operating Model

**26. Track cost per minute, per interaction, per language, for failed calls**
- Dimension: Operating Model
- Stage: Pilot
- Type: Tactical Decision
- Relevant to: Social Sector/Enterprise, Government
- Decision: Build cost visibility into the operating model from the pilot, broken down by TTS tier, model choice, language, and call outcome (completed vs. abandoned/failed).
- Condition — applies when: Any voice AI deployment moving toward scale, where per-unit cost assumptions modeled on English-language benchmarks will be wrong.
- Source: Cross-deployment synthesis.

**27. Validate first, then scale — as two distinct phases with distinct success criteria**
- Dimension: Operating Model
- Stage: Scale
- Type: Strategic Decision
- Relevant to: Government, Social Sector/Enterprise
- Decision: Phase 1 (Validate) succeeds when users can complete the intended interaction and the institution trusts the agent enough to continue. Phase 2 (Scale) succeeds when the institution can change vendors, models, languages, or data sources without rebuilding everything, and cost/quality/safety are all monitored.
- Alternative considered: Treating "it works in pilot" as sufficient grounds to scale.
- Source: Cross-deployment synthesis.

**28. Someone must own continuous post-launch monitoring, or degradation is invisible until trust is already damaged**
- Dimension: Operating Model
- Stage: Scale
- Type: Strategic Decision
- Decision: Name an owner for monitoring failed calls, misunderstood queries, drop-offs, unsafe responses, latency, cost drift, language gaps, and backend data errors — as an ongoing role, not a launch-week task.
- Source: Cross-deployment synthesis.

---

## 4. Toolkits and playbooks

| Asset | Type | Reuse condition |
|---|---|---|
| Safety and stress-test bank (categories: in-scope, out-of-scope, distress, abuse, romantic/inappropriate, policy complaints, jailbreak, escalation-required) | Toolkit (Unit 7) | Any public-facing conversational agent speaking on an institution's behalf |
| Five-question model selection order | Playbook (Unit 8) | Any model selection decision, worked through before committing to a pilot |
| Staged institutional testing progression (builder → small group → wide group → limited rollout, with named gate per stage) | Playbook (Unit 24) | Any deployment where public failure reads as institutional failure |
| Voiceera (open orchestration layer) | Toolkit (Unit 16) | Where model-, language-, and telephony-provider-agnosticism matters long-term |

---

## 5. Problem→solution patterns

| Problem | Root cause | Solution | Result | Condition |
|---|---|---|---|---|
| Silence during backend fetch feels like a dropped call | Latency in data-layer round trip exposed directly to the user | Insert a hold message during the wait | Perceived reliability restored without any backend speed-up | Any response path with >~2s backend latency |
| Vendor lock-in discovered only once scale makes switching expensive | No deliberate unbundling decision point was ever set | Start bundled, but name the trigger condition for unbundling in advance; test 2+ vendors in parallel pre-scale | Control preserved without sacrificing pilot speed | Limited technical capacity at pilot; more at stake at scale |
| Data errors require rebuilding the AI layer | AI layer directly hardwired to source database | API-separate the data layer from the AI layer; accountability stays with the named data owner | Data fixes no longer touch the AI layer | Multiple data sources, distinct owners/cadences |
| Institution disowns the bot after its first visible mistake | Ownership, approval, and escalation questions were never assigned before launch | Name channel owner, content approver, and failure-review process before go-live | Institution can absorb a failure and tighten boundaries instead of disowning the whole system | Bot is perceived as speaking for the institution |
| Model passes lab benchmarks, then fails on a specific dialect in the field | Lab test set didn't represent real dialectal/accent variation | Two-step evaluation: metrics to shortlist/reject, real user + institutional testing to confirm | Dialect gaps caught before public exposure | Any model selection for a live channel |
| Multilingual demand appears only after launch | Language distribution of the real user base wasn't mapped before Define | Map multilingual need at Define stage; design retrofit path if full coverage isn't feasible at launch | Avoids the much higher cost of retrofitting language support post-launch | Any deployment where the user population's language mix wasn't fully known upfront |
| Users are wary of "a bot" regardless of how well it works | Trust framing centred the technology instead of the institution behind it | Frame the channel explicitly as a service of the trusted institution, not as an AI product | Wary users engaged once the institutional framing was made explicit | Target users trust a specific institution more than unfamiliar digital tools |

---

## 6. Retrieval guide

*"I need to avoid vendor lock-in at Define stage"* → Units 5, 22

*"I'm choosing a voice/ASR/TTS model and don't know how to evaluate it"* → Units 8, 11, 24

*"Should we build our own model instead of using an existing one?"* → Unit 9

*"Our data sources have different owners and I don't know how to structure the connection"* → Unit 17

*"We're about to go live and need a safety checklist"* → Unit 7

*"The department won't commit to owning this bot"* → Unit 21

*"Users don't trust the system because it's AI"* → Unit 20

*"We only have one language today but might need more later"* → Unit 3

*"We have no data or models for our target language at all"* → Units 23, 19

*"Our conversations feel clunky or too long"* → Units 12, 13, 14

*"Costs are higher than we projected"* → Unit 26

*"Field staff see the bot as a threat to their role"* → Unit 25

*"We're moving from pilot to scale and don't know what 'ready' means"* → Unit 27

*"We want to avoid rebuilding every time we change a model or telephony provider"* → Unit 16
