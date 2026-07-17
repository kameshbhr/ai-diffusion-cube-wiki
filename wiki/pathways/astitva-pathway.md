# Language Enablement for AI

## 0. Reading guide

This is a **horizontal pathway**: it captures language enablement as a prerequisite step, upstream of any specific use case — the output is language infrastructure (a trained ASR/NMT/TTS/LLM stack plus the open data behind it), not a deployment in itself. It draws on Project Astitva, a district-led effort in Nandurbar, Maharashtra, that built Dehvali Bhili — a tribal language with no prior digital footprint — into a usable voice AI stack in roughly a hundred days, then fed the result into an existing agricultural advisory deployment (MahaVISTAAR).

**Why this pathway exists.** For a language with no script, no formal teaching, and no digital footprint, every other AI-deployment decision is blocked until the language itself exists as an asset. No commercial actor had a market reason to build that infrastructure on its own, so the gap was never going to close without a deliberate, publicly-led effort. This pathway exists because language enablement has its own lifecycle, its own actor map, its own failure modes, and its own economics — distinct from the deployment that eventually uses the resulting language capability. The throughline across this material is a deployment-first discipline: data collection is the easy part to talk about and the wrong thing to optimise for; what determines impact is a committed downstream deployment, a convening authority who owns it, and a use case identified early enough to anchor the whole effort.

**How to navigate**
- If you're deciding whether a language actually needs to be built from scratch — start with Problem Orientation, Explore stage (Units 1–2), and the data audit in Unit 6.
- If you're choosing what to build the model stack on top of — start with Architecture.
- If you're scoping the data collection design itself — start with Data, Define stage.
- If you're trying to figure out who needs to be in the room — start with Ecosystem, especially the ten-role blueprint (Unit 19).
- If you're worried about cost, funding, or who owns this after the pilot — start with Operating Model.
- If your model works in testing but breaks on real calls — go to Data, Pilot stage (Units 11–12).
- If you want the actual build sequence end to end — go straight to the playbook in Unit 28.

---

## 1. Pathway identity

| Field | Detail |
|---|---|
| Deployment/Pathway name | Enabling Voice AI Models for Bhili Language (Project Astitva) |
| Sector | Cross-sector (initial deployment: Agriculture via MahaVISTAAR; planned: Health, Education, Administration) |
| Actor type | Government, Technologist, Social Sector-Enterprise |
| Geography | Nandurbar district, Maharashtra, India (Dehvali Bhili is spoken by a much larger community — roughly ten million tribal speakers across a wider multi-state region) |
| Population served | 9+ lakh tribal residents of Nandurbar across 18+ languages and dialects; Dehvali Bhili itself spoken by roughly ten million speakers regionally |
| Stage reached | Pilot → Scaling (Dehvali Bhili integrated into MahaVISTAAR; expansion to further languages and domains underway) |
| Contributing organisation | EkStep Foundation|
| Dimensions covered | Architecture, Data, Institution, and Ecosystem are all densely and specifically documented, including named tooling and partner roles. Workforce is out of scope by design — the source material frames workforce and dependency questions as belonging to the downstream deployment that consumes this language infrastructure, not to language enablement itself. Governance, licensing, and maintenance economics after the pilot are the thinnest area within the dimensions this pathway does cover. |
| Last updated | Not stated in the source |
| Contact for peer connection | Not stated in the source |
| Summary | A district-led, EkStep Foundation-coordinated effort built Dehvali Bhili — a tribal language with no script, no formal teaching, and no digital footprint — into a working ASR/NMT/TTS/LLM stack in roughly a hundred days, at a government-funded pilot cost of about ₹27 lakh. The resulting open language infrastructure was integrated into MahaVISTAAR as its first practical use, with expansion to three more languages and new sectors planned next. |

---

## 2. Coverage grid

Density: ●●● = 3+ units · ●● = 2 units · ● = 1 unit · ○ = 0 units

| Dimension | Explore | Define | Pilot | Scale |
|---|---|---|---|---|
| Problem Orientation | ● | ○ | ○ | ○ |
| Architecture | ○ | ●●● | ○ | ○ |
| Data | ● | ●●● | ●● | ● |
| Institution | ○ | ●●● | ○ | ○ |
| Ecosystem | ● | ●●● | ○ | ○ |
| Workforce | ○ | ○ | ○ | ○ |
| Operating Model | ○ | ●●● | ○ | ○ |

*Workforce shows no units by design, not by omission: the people who apply the resulting model in a live use case — and any training, feedback, or dependency questions that come with that — belong to the downstream deployment that consumes this language infrastructure, not to this pathway.*

### Known gaps in the pathway

- *(Problem Orientation, Scale)* Beyond usage numbers, did the project track any real-world outcome — like an actual change in a farmer's life — to show impact on the community?
- *(Data, Define)* Did the project use a specific sentence-selection methodology — like a coverage logic or sourcing method — beyond just the volume targets, to guide corpus construction for a language with limited written material?
- *(Data, Pilot)* Was there a specific WER, BLEU, or MOS score that the team used as the bar for "accurate enough to release more widely"?
- *(Data, Define)* How does the project handle India's DPDP 2023 data protection law for this data — who is the data fiduciary, and can contributors withdraw consent even though the dataset is hosted openly?
- *(Institution, Define)* What kinds of problems did the monitoring process actually catch during data collection — fake submissions, unfair treatment of contributors, misuse of funds, something else — and how were they handled?
- *(Institution, Scale)* Once the PMU winds down, is there a plan to make sure knowledge about the dataset, the model, and community relationships doesn't just leave with the team?
- *(Ecosystem, Define)* For a language with no academic tradition, how do you actually find or train someone to serve as a linguistic validator?
- *(Ecosystem, Define)* Beyond having the pipeline and role structure in place, how were community annotators and validators actually trained and quality-checked at volume?
- *(Ecosystem, Pilot)* Besides the one Tribaldaan conclave at the start, were there other touchpoints that kept the community's trust through the weeks of data collection?
- *(Operating Model, Scale)* If a downstream deployment like MahaVISTAAR finds the model getting something wrong, is there a process to report that back to the team that owns the model — and does it trigger a fix or retraining?
- *(Operating Model, Scale)* Now that the dataset is open and the plan is to hand over from district to state, who's actually responsible for updating it, funding it, and deciding what happens to it next?

---

## 3. Micro-innovations

### Problem Orientation

**1. Frame the problem as language exclusion, not technology absence**
- Dimension: Problem Orientation
- Stage: Explore
- Type: Strategic Decision
- Decision: Framed the effort as solving language exclusion — a specific Dehvali Bhili speaker in Nandurbar, often with low or no literacy, using a keypad phone or basic Android handset, unable to access services designed for majority languages — rather than starting from a technology capability.
- Alternative considered: Not documented in the source.
- Condition — applies when: A project risks starting with "what can this technology do" instead of "who is excluded, and why."
- Before → After: Not documented in the source.
- Source: Project Astitva.

### Architecture

**3. Reuse existing assets wherever possible**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Decision: Reused existing assets at every layer rather than building from scratch — fine-tuned an existing open AI4Bharat/IIT Madras base across ASR, NMT, and TTS (with an LLM fine-tuned on a Qwen base) instead of training foundation models fresh, and separately bootstrapped Dehvali Bhili itself from Marathi, a linguistically related higher-resource neighbour, rather than relying purely on the very limited Bhili data collected.
- Alternative considered: Training models from scratch; relying solely on Bhili-only data without cross-lingual bootstrapping.
- Condition — applies when: An open, adequately-licensed model base already exists to fine-tune, and/or the target low-resource language has a linguistically related higher-resource neighbour with existing model or data assets.
- Before → After: Not documented in quantified terms; framed as saving both time and cost.
- Source: Project Astitva.

**4. Open, model-agnostic stack and sovereign hosting to avoid lock-in**
- Dimension: Architecture
- Stage: Define
- Type: Strategic Decision
- Decision: Chose open, model-agnostic components and Bhashini's sovereign hosting specifically to stay independent of any single commercial platform whose priorities could shift.
- Alternative considered: Not documented in the source.
- Condition — applies when: The resulting asset needs to remain usable regardless of any one vendor's future direction.
- Before → After: Not documented in the source.
- Source: Project Astitva.

**5. Reuse an existing community radio station for recording**
- Dimension: Architecture
- Stage: Define
- Type: Tactical Decision
- Decision: Used an existing community radio station for audio recording rather than building a purpose-built studio.
- Alternative considered: Building a dedicated recording studio.
- Condition — applies when: A suitable existing recording facility is already available in the community, avoiding new capital spend.
- Before → After: Not documented in the source.
- Source: Project Astitva.

### Data

**6. Audit existing language assets before assuming zero**
- Dimension: Data
- Stage: Explore
- Type: Strategic Decision
- Decision: Audited what already existed for Dehvali Bhili — textbooks, written material, prior recordings, prior linguistic work, including checking Bhashini for prior work — before committing to a zero-to-one collection effort. The audit confirmed a genuine zero-to-one starting point: no script, no formal teaching, fewer than a hundred existing books, no audio or video assets.
- Alternative considered: Not documented in the source.
- Condition — applies when: Any project is about to commit a zero-to-one data-collection budget and plan without first checking what may already exist.
- Before → After: Not documented in the source.
- Source: Project Astitva.

**7. Multi-domain sentence corpus specification**
- Dimension: Data
- Stage: Define
- Type: Toolkit Asset
- Toolkit asset: A quantified corpus specification — 25,000 agricultural sentences, 15,000 non-agricultural sentences (40,000+ sentence recordings total), plus roughly 68 hours of speech across spontaneous (60 hrs), studio (6 hrs), and conversational (2 hrs) recordings, all in Dehvali Bhili.
- Reusable as-is: A concrete, bounded collection target for any similar language-enablement effort.
- Condition — applies when: Starting a language-enablement effort with no prior sense of how much or what kind of data is needed.
- Source: Project Astitva.

**8. Kathbath as the underlying collection methodology**
- Dimension: Data
- Stage: Define
- Type: Toolkit Asset
- Toolkit asset: Kathbath was used as the underlying collection process for gathering voice recordings from community contributors.
- Reusable as-is: An existing, tested collection methodology rather than a bespoke process built from nothing.
- Condition — applies when: Standing up voice-data collection from a distributed community of contributors.
- Source: Project Astitva.

**9. Maker–Checker–Superchecker multi-layer quality pipeline**
- Dimension: Data
- Stage: Define
- Type: Toolkit Asset
- Toolkit asset: Three parallel tracks running simultaneously — production (contributors/makers recording), checking (checkers reviewing contributor output in real time via Shoonya, the annotation tool), and validation (linguistic experts and the Tribal Research Institute reviewing checker output) — following a Maker–Checker–Superchecker model, tracked through digital dashboards and leaderboards. All recordings, transcriptions, and quality validations were managed centrally through Karya's platform in one place — a deliberate contrast to the federated data model used downstream in MahaVISTAAR itself, chosen specifically so this real-time multi-layer pipeline could run against a single dataset being built from nothing.
- Reusable as-is: A ready-made quality structure for high-volume, time-bound community data collection.
- Condition — applies when: Collecting data at volume, under time pressure, from a distributed community rather than a small in-house team.
- Source: Project Astitva.

**10. Separate domain-specific data from general data by design**
- Dimension: Data
- Stage: Define
- Type: Strategic Decision
- Decision: Deliberately separated domain-specific sentence collection by contributor domain — health workers contributed health/social-service sentences, revenue staff contributed administrative sentences, community members and Bhili-speaking agriculture officers contributed agriculture and daily-life sentences — as a design decision, not an incidental outcome.
- Alternative considered: Collecting general-purpose sentences without domain tagging.
- Condition — applies when: The resulting model will be deployed across multiple sectoral use cases that each need domain-accurate vocabulary.
- Before → After: Not documented in quantified terms; framed as mattering directly for model accuracy in sectoral deployments.
- Source: Project Astitva.

**11. Read speech does not produce conversational-grade models**
- Dimension: Data
- Stage: Pilot
- Type: Failure and Fix
- Failure: Initial collection leaned on read speech; people read differently from how they speak, and read-only data produces models that fail in real conversation. This gap was discovered post-deployment, requiring rework.
- Fix: Added dedicated conversational speech collection (2 hours) alongside spontaneous (60 hrs) and studio (6 hrs) recordings, since conversational data cannot simply be scripted — it requires deliberate design.
- Insight: Both read/scripted and natural/conversational speech types are needed, and both must be planned into the original collection design rather than discovered afterward.
- Condition — applies when: The model is intended for live, spoken, conversational deployment.
- Source: Project Astitva.

**12. Telephony audio-quality mismatch**
- Dimension: Data
- Stage: Pilot
- Type: Failure and Fix
- Failure: Data was recorded at 16kHz (smartphone/laptop quality); telephony lines operate at 8kHz. A model trained only at 16kHz fails on actual telephony calls. This mismatch was also discovered post-deployment, requiring rework.
- Fix: Either collect at 8kHz directly or deliberately downsample during training — decided as part of the recording specification before collection, not after, going forward.
- Insight: Recording quality must be matched to deployment conditions from the start; this and the read-vs-conversational gap were both discovered too late in Astitva and both belong in the original collection plan for any future effort.
- Condition — applies when: Data-collection tooling (smartphones, laptops) has higher audio fidelity than the deployment channel (telephony).
- Source: Project Astitva.

**13. Deliberate dialect representation in testing**
- Dimension: Data
- Stage: Define
- Type: Failure and Fix
- Failure: Approval from a small group of testers does not constitute proof of dialect coverage if dialect variation isn't represented in the testing panel.
- Fix: Map which dialects have gaps and target supplementary collection accordingly, rather than relying on whichever testers happen to be available.
- Insight: Dialect representation must be deliberate and tracked, not incidental to who is easiest to reach for testing.
- Condition — applies when: The target language has multiple dialects and formal testing capacity is limited.
- Source: Project Astitva.

**14. Open dataset release via Bhashini and AI Kosh**
- Dimension: Data
- Stage: Scale
- Type: Toolkit Asset
- Toolkit asset: The resulting dataset — 40,000+ sentence recordings plus roughly 68 hours of speech — is released as an open repository on Bhashini and also on AI Kosh, for nationwide replication.
- Reusable as-is: Any deployer building voice AI for Dehvali Bhili can draw on the dataset directly rather than recollecting it.
- Condition — applies when: Building any AI system, not limited to agriculture, that needs to serve Dehvali Bhili speakers.
- Source: Bhashini national language repository; AI Kosh.

### Institution

**15. Convening authority must have local standing**
- Dimension: Institution
- Stage: Define
- Type: Strategic Decision
- Decision: Used the District Collector's office — which in Maharashtra sits above all line departments — as the convening authority, on the basis that an external organisation could support and implement but could not substitute as convener; the convening authority must be local and trusted.
- Alternative considered: An external organisation acting as convener.
- Condition — applies when: Cross-department mobilisation is needed and the convening actor must already be trusted locally.
- Before → After: Not documented in the source.
- Source: Project Astitva.

**16. District-level financial delegation as an enabling condition**
- Dimension: Institution
- Stage: Define
- Type: Strategic Decision
- Decision: Relied on Maharashtra's delegated district-level financial powers to act without requiring state-level approval at each step.
- Alternative considered: Not documented in the source.
- Condition — applies when: Working within an administrative structure with equivalent district-level fiscal delegation.
- Condition — fails when: That delegation doesn't exist elsewhere — in which case a different institutional anchor (a state-level ministry, a national programme) may be needed; a next adopter should check for this explicitly before designing a funding and approval model.
- Before → After: Not documented in the source.
- Source: Project Astitva.

**17. District and community pride, made concrete through a dedicated trust-building event**
- Dimension: Institution
- Stage: Define
- Type: Strategic Decision
- Decision: Framed the project explicitly as a matter of district and community pride, not just a technical exercise — and made that framing concrete for the community itself through the Tribaldaan conclave with Bhashini, held before data collection began to establish what was being built, why, and on what terms.
- Alternative considered: Not documented in the source.
- Condition — applies when: A short, high-intensity, multi-actor effort risks losing momentum without an identity-level motivator, and/or the community being asked to contribute has reason to distrust a government-led technology effort.
- Before → After: Not documented in the source.
- Source: Project Astitva.

**18. In-house institutional testing at each phase, non-negotiable**
- Dimension: Institution
- Stage: Define
- Type: Strategic Decision
- Decision: Required the institution whose name is on the model to put a human lens on it at each phase before wider release — this could not be outsourced to the technology partner or a third-party testing team.
- Alternative considered: Outsourcing testing to the technology partner.
- Condition — applies when: A government institution's name and credibility stand behind what the AI system says.
- Before → After: Not documented in the source.
- Source: Project Astitva.

### Ecosystem

**19. Ten-role replicable actor blueprint**
- Dimension: Ecosystem
- Stage: Define
- Type: Toolkit Asset
- Toolkit asset: A generalised ten-role blueprint for any low-resource language project: convening authority, community speakers, annotators, linguistic validators, data collection platform provider, specialised data partner, model builder, infrastructure/hosting provider, neutral orchestrator, and PMU.
- Reusable as-is: A checklist of roles that need filling, independent of which specific organisation fills each one.
- Condition — applies when: Assembling partners for any similar language-enablement effort from scratch.
- Source: Project Astitva.

**20. Neutral orchestrator must actively map and connect actors**
- Dimension: Ecosystem
- Stage: Explore
- Type: Failure and Fix
- Failure: IIT Madras had relevant model-building capability but had no way of knowing the Astitva effort was happening at all.
- Fix: EkStep Foundation held coordination across every actor and drove the effort to launch, acting as neutral orchestrator by actively mapping the relevant ecosystem and making introductions.
- Insight: The neutral orchestrator role is not a passive coordination function — without someone actively mapping and reaching out, relevant partners simply may not know an effort exists.
- Condition — applies when: More than a few independent organisations need to coordinate and none has natural authority over the others.
- Source: Project Astitva.

**21. Specialised data partner is not substitutable by a general implementation partner**
- Dimension: Ecosystem
- Stage: Define
- Type: Strategic Decision
- Decision: Engaged Karya specifically as a specialised data partner with distinct expertise in ethical data collection from underserved communities, rather than using a general implementation partner.
- Alternative considered: A general implementation partner without this specific expertise.
- Condition — applies when: Data collection touches vulnerable or underserved communities and requires ethical-collection expertise that a general partner would not have.
- Before → After: Not documented in the source.
- Source: Project Astitva.

**22. Compensation, consent, and eligibility design for community contributors**
- Dimension: Ecosystem
- Stage: Define
- Type: Strategic Decision
- Decision: Designed community contributor compensation and consent as one integrated pattern — contributors selected against explicit eligibility criteria (proficiency in the target language, literacy and typing skills, and local ownership in language standardisation), anonymised through unique registration codes, paid directly via UPI at roughly ₹1–2 per word, with payment tied only to verified contributions rather than submission alone, and told transparently before any recording began that data was being collected for open-source ASR, NMT, and TTS.
- Alternative considered: Not documented in the source.
- Condition — applies when: Compensating and protecting a large, distributed group of community contributors producing personal voice data directly, at scale.
- Before → After: Not documented in the source; roughly ₹20 lakh of the pilot spend reached community contributors directly through this design.
- Source: Project Astitva.

**23. Linguistic validator as a distinct, non-substitutable role**
- Dimension: Ecosystem
- Stage: Define
- Type: Strategic Decision
- Decision: Treated linguistic validation — checking grammatical and phonetic accuracy — as a distinct role from native-speaker recording, since fluent speakers cannot reliably validate their own grammatical accuracy; used linguistic experts and the Tribal Research Institute for this function.
- Alternative considered: Relying on native-speaker contributors alone to self-validate.
- Condition — applies when: The target language has no academic tradition, meaning this role may need to be developed through the project itself rather than sourced externally.
- Before → After: Not documented in the source.
- Source: Project Astitva.

### Operating Model

**24. Anchor to a committed deployment: data collection is infrastructure, not the deliverable**
- Dimension: Operating Model
- Stage: Define
- Type: Strategic Decision
- Decision: Anchored data collection to the MahaVISTAAR use case and a deadline tied to the India AI Impact Summit — after early collection had drifted without a fixed use case or deadline — on the underlying principle that a committed downstream deployment, a convening authority who owns it, and an early-identified use case are what determine impact, not the volume of data collected. A model built without a deployment-first approach creates no impact.
- Alternative considered: Continuing an open-ended collection effort without a forcing function (the actual early state, which drifted); treating data collection as the primary deliverable.
- Condition — applies when: A language-building effort risks becoming an open-ended documentation exercise without a real deployment and a hard deadline attached to it, or risks being scoped and measured as a data-collection project rather than as infrastructure for a committed downstream use.
- Before → After: Before — collection drifted without a fixed use case or deadline. After — anchoring to MahaVISTAAR and the Summit deadline turned it into purposeful work, completed in roughly a hundred days.
- Source: Project Astitva.

**25. Plan institutional handover before the project begins**
- Dimension: Operating Model
- Stage: Define
- Type: Strategic Decision
- Decision: Designed tribal-department ownership and a district-to-state transition (via MahaVISTAAR) as the intended handover plan before the project began, rather than improvising ownership later.
- Alternative considered: Not documented in the source.
- Condition — fails when: The plan is designed but not verified as operating — the source itself does not confirm whether this transition, or a standing governance model, is actually functioning today.
- Before → After: Not documented in the source.
- Source: Project Astitva.

**26. Design for reuse and openness from day one**
- Dimension: Operating Model
- Stage: Define
- Type: Strategic Decision
- Decision: Decided on open licensing, platform-neutral hosting, and documented methodology early, rather than retrofitting openness after the fact — retrofitting is harder and often simply doesn't happen.
- Alternative considered: Building a closed or partner-specific asset and opening it up later.
- Condition — applies when: The resulting dataset or model is meant to be reused by future deployers beyond the current partner set.
- Before → After: Not documented in the source.
- Source: Project Astitva.

**27. Absorb model-build cost via research partnership in exchange for open data**
- Dimension: Operating Model
- Stage: Define
- Type: Tactical Decision
- Decision: Structured the partnership so that model-training cost was effectively absorbed by the research partner (AI4Bharat/IIT Madras) in exchange for the resulting dataset being released openly, rather than paying directly for model-building.
- Alternative considered: Commissioning and paying for model-building directly.
- Condition — applies when: A research partner has enough independent interest in access to a novel open dataset that it will absorb training costs in exchange for it.
- Before → After: Not documented in comparative cost terms.
- Source: Project Astitva.

**28. Build-process playbook: from zero to a live integration**
- Dimension: Operating Model
- Stage: Define
- Type: Playbook
- Playbook:
  1. Audit what already exists for the target language (scripts, texts, recordings, prior Bhashini work) before assuming a zero-to-one build (Unit 6).
  2. Map dialect and linguistic variation precisely before setting collection targets (Unit 2).
  3. Set a quantified, domain-balanced corpus specification and assemble the partner and actor roles needed to deliver it (Units 7, 19).
  4. Run data collection through a multi-layer quality pipeline — production, checking, validation — rather than collecting first and validating later (Unit 9).
  5. Build the model layer by reusing existing open bases and bootstrapping from linguistically related higher-resource languages wherever possible, rather than training from scratch (Unit 3).
  6. Anchor the whole sprint to a committed downstream deployment and a hard external deadline, so the effort doesn't drift into an open-ended data-collection exercise (Unit 24).
  7. Integrate into one existing deployment and prove it there before expanding to additional languages or domains.
- Note: Skipping the ordering — most commonly collecting data before dialect variation is mapped, or building without a downstream deployment committed — is the failure mode this sequence exists to prevent.
- Condition — applies when: Starting a language-enablement effort from zero, where the full sequence from problem framing to a live integration hasn't been run before.
- Before → After: Not documented in the source as a single tracked sequence; assembled here from decisions and milestones documented separately across the project (roughly a month for the foundational data sprint, about two months for the wider Phase 1).
- Source: Project Astitva.

---

## 4. Toolkits and playbooks

| Asset | Unit | Reuse condition |
|---|---|---|
| Multi-domain sentence corpus specification | Toolkit (Unit 7) | Use when starting a language-enablement effort with no existing sense of how much or what kind of data is needed. |
| Kathbath collection methodology | Toolkit (Unit 8) | Use when standing up voice-data collection from a distributed community of contributors. |
| Maker–Checker–Superchecker quality pipeline | Toolkit (Unit 9) | Use when collecting data at volume, under time pressure, from a distributed community. |
| Open dataset on Bhashini and AI Kosh | Toolkit (Unit 14) | Use directly when building any AI system that needs to serve Dehvali Bhili speakers. |
| Ten-role replicable actor blueprint | Toolkit (Unit 19) | Use when assembling partners for a similar language-enablement effort from scratch. |
| Build-process playbook: zero to live integration | Playbook (Unit 28) | Use as the end-to-end sequence when running a language-enablement effort for the first time. |

---

## 5. Problem→solution patterns

| Problem | Root cause | Solution | Result | Condition |
|---|---|---|---|---|
| Model performed poorly in natural conversation | Data collection leaned on read speech; not discovered until post-deployment | Added a dedicated conversational speech collection track | Rework required; conversational data now planned in from the start | Applies to any voice model intended for live conversational deployment |
| Model underperformed on live telephony calls | Data recorded at 16kHz; telephony operates at 8kHz; not discovered until post-deployment | Collect at 8kHz directly or deliberately downsample during training | Rework required; audio spec now decided before collection begins | Applies whenever collection tooling has higher audio fidelity than the deployment channel |
| Small-panel testing gave false confidence in dialect coverage | Dialect variation wasn't represented in the testing panel | Map which dialects have gaps and target supplementary collection accordingly | Not documented in comparative terms | Applies whenever the target language has multiple dialects and testing capacity is limited |
| A directly relevant technical partner (IIT Madras) was unaware the effort existed | No neutral orchestrator actively mapping and connecting the ecosystem | EkStep Foundation took on the neutral orchestrator role, actively mapping actors and making introductions | Enabled coordination across the full ten-role actor map | Applies whenever several independent organisations must coordinate and none has natural authority over the others |
| Early data collection drifted without clear purpose | No fixed use case or deadline attached to the collection effort | Anchored the sprint to the MahaVISTAAR use case and a deadline tied to the India AI Impact Summit | Completed in roughly a hundred days from zero digital footprint to live service component | Applies whenever a language-building effort risks becoming open-ended without a forcing function |

---

## 6. Retrieval guide

*"How do we know if a language actually needs to be built from scratch, or does something already exist?"* → Unit 6

*"Our target population speaks one 'language' — do we need to worry about dialects?"* → Unit 2, Unit 13

*"What should we build our model stack on top of instead of starting from nothing?"* → Unit 3

*"How do we avoid vendor lock-in on the model and hosting side?"* → Unit 4

*"What should our data collection targets and structure actually look like?"* → Unit 7, Unit 10

*"What tools or methodology should we use to actually run the collection process?"* → Unit 8, Unit 9

*"Our model sounds fine in training but fails on real phone calls — why?"* → Unit 12

*"Our model reads fine but breaks down in natural conversation — why?"* → Unit 11

*"How do we pay and protect community contributors fairly?"* → Unit 22

*"Who actually needs to be involved in a project like this?"* → Unit 19, Unit 20

*"Should this be run by an external organisation or must it be government-led?"* → Unit 15

*"How do we keep this from stalling if the person driving it moves roles?"* → Unit 15, Unit 25

*"What does this actually cost, and how is it typically funded?"* → Unit 22, Unit 27

*"Should we try to build support for every dialect and sector at once, or go step by step?"* → Unit 28

*"How do we make sure this doesn't turn into an endless data-collection exercise with nothing to show for it?"* → Unit 24

*"What's the actual end-to-end sequence for a language-enablement project?"* → Unit 28
