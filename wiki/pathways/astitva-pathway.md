# Language Enablement for Voice AI

*A pathway for bringing a language with little or no existing digital footprint into voice AI — speech recognition, translation, and speech synthesis — and into a live public service.*

---

## 0. Reading guide

This pathway is built from one deployment — bringing Dehwali Bhili, a tribal language with zero prior digital resources, into a live government voice service — plus a companion blueprint written to generalize that experience for the next language, anywhere.

**What this is.** Organized around the decisions the next adopter will actually face: what to decide, what was weighed, why one path was chosen, and the conditions under which that choice holds.

**How to navigate it.** Section 3 groups reusable insight into four areas — who you're building for, what you're building, whether your institution can own it, and who else needs to be at the table — each broken out by how far along the effort is. Section 2 shows where this pathway has dense, tested experience and where it's thin. Section 6 is a question-first index.

---

## 1. Pathway identity

| Field | Value |
| --- | --- |
| **Deployment name** | Bhili (Dehwali Bhili) Language Enablement for Voice AI — Project Astitva |
| **Sector** | Government service delivery — agricultural extension advisory, with health, education, and citizen feedback named as near-term extensions |
| **Geography** | Nandurbar district, Maharashtra, India; the companion blueprint is written for global reuse |
| **Population served** | 10 million+ Bhili speakers nationally; within Nandurbar, tribal community members — particularly women farmers with smaller advice networks, limited Marathi exposure, and lower smartphone access |
| **Contributing organisation(s)** | EkStep Foundation (Voice and Language AI team); Nandurbar District Administration (convening authority); AI4Bharat/IIT Madras (model building); Bhashini (national hosting); Karya (data-collection platform); State Agriculture Department and POCRA (deployment, via MahaVISTAAR's Vasudha bot) |
| **Stage reached** | Scale — live public service since approximately May 2026, telephony/IVR version targeted live before October 2026, replication to sibling languages already in motion. As of July 2026. |
| **Key dates** | Phase 1 data collection compressed to roughly one month; full collect→build→deploy cycle roughly 100 days; first live version ~May 2026. As of July 2026. |
| **2-sentence summary** | A district administration's independent effort to collect Bhili voice data was connected to a national AI platform and a live agricultural advisory service, taking a zero-digital-resource tribal language from a standing start to a working ASR/NMT/TTS pipeline in about 100 days. The most transferable finding is that the bottleneck was organisational and relational — trust, a named institutional anchor, a real deployment target — not the AI tooling, which already existed. |
| **Scale/impact achieved** | 60,000+ voice samples and 60,000 Bhili–Marathi translation pairs collected in about one month (~60 hours spontaneous speech, ~2 hours studio voice); live inside MahaVISTAAR's Vasudha bot. As of July 2026. |
| **Cost anchor** | ~₹27 lakh for Phase 1, entirely government-funded; ~₹20 lakh paid directly to community contributors. Model training subsidised by AI4Bharat in exchange for open data access. As of July 2026. |
| **Build effort** | ~100 days end to end (collect → build → deploy) from an absolute zero-resource start. |
| **Known downstream adopters** | Mathwadi Bhili, Mavchi, and Pawari are next in motion on the same playbook; Bodo and Garo are on the roadmap. As of July 2026. |
| **Scope — does not transfer cleanly when** | The target language already has some existing digital presence (this pathway assumes an absolute zero-resource start); or the effort is not tied to a specific service a community will actually use. |

---

## 2. Coverage grid and gaps

| Dimension | Explore | Define | Pilot | Scale |
| --- | --- | --- | --- | --- |
| **Persona** | ● | ●● | ○ | ○ |
| **Solution** | ●● | ●● | ●●● | ○ |
| **Institution** | ●●● | ● | ●● | ● |
| **Ecosystem** | ○ | ●●● | ○ | ● |

**Gaps worth naming**

- **Persona at Pilot and Scale is empty.** No record of how real usage matched or missed the intended scope, or whether new user segments surfaced once Bhili reached real scale.
- **Solution at Scale is empty.** The pathway is documented mid-rollout — no record of which components get unbundled, or whether data SLAs will be needed, as Bhili extends beyond agriculture.
- **Institution at Define is thin (1 unit).** No named content-authority sign-off, no named data steward, no explicit testing gate reported before real users.
- **Ecosystem at Pilot is empty.** No confirmation of whether any partner underperformed once the effort was live, or what contingency existed if one had.
- **Institution at Scale is thin (1 unit) and incomplete.** The one unit here captures the intent to run a standing multi-stakeholder model, but no named operational owner, budget line, or monitoring cadence is confirmed as actually locked in.
- **What "deletion" actually covers once data has been used in a training run is undocumented.** Unit 16 confirms deletion mechanisms exist for stored data, but doesn't say whether a withdrawal request after training also affects a model already fine-tuned on that contributor's data, or only the raw stored copy.

---

## 3. Micro-innovations

### Persona

**1. Anchor to a specific excluded person and a service, not the language**
- Dimension: Persona
- Stage: Explore
- Type: Strategic Decision
- Decision: Start from a specific excluded person and the service they're entitled to but can't reach — not from "let's build a model for this language."
- What this looked like here: Nandurbar's District Collector centered the effort on tribal women farmers with far less Marathi exposure than men in their communities, consequently missing agriculture/health/education scheme benefits, with the state's agricultural advisory system as the named service.
- Alternative considered: Choosing to build a model for the language on its own terms, without first anchoring to a specific excluded population or service.
- Why: A language chosen for its own sake produces a dataset with no one institutionally urgent about it. A named excluded person and a named unreachable service gives the effort a stakeholder whose life visibly changes if it works.
- Condition — applies when: scoping a new low-resource-language effort from scratch.

**2. Scope to one deployment first; extend to new sectors incrementally**
- Dimension: Persona
- Stage: Define
- Type: Tactical Decision
- Decision: Scope tightly to one deployment now rather than building for many future use cases at once, with incremental data collection for the next use case later.
- What this looked like here: Bhili was scoped to the MahaVISTAAR agriculture advisory bot first; health, education, and citizen-feedback use cases were deferred to later, separate efforts.
- Alternative considered: Covering every anticipated future use case within the first data-collection sprint.
- Why: A use-case-agnostic model needs far more data before it's usable for any sector — a harder bar for a genuinely low-resource pool of available speakers. Scoping narrow gets a working system into people's hands faster, and each new sector then needs only incremental top-up data.
- Condition — applies when: resources (financial and human) are constrained, which is the common case here.

**3. Name one dialect variant explicitly; treat sibling languages as separate follow-on efforts**
- Dimension: Persona
- Stage: Define
- Also relevant at: Scale
- Type: Strategic Decision
- Decision: Where a language has more than one identifiable variant, name and record for one of them, rather than trying to represent the whole continuum in the first sprint.
- What this looked like here: The team chose Dehwali Bhili over Bhili's other known variation for this effort. Mathwadi Bhili, Mavchi, and Pawari are next in line as separate efforts, with Bodo and Garo further out.
- Alternative considered: Collecting across both known Bhili variations within this same effort.
- Why: Splitting a first sprint's data collection across multiple variants dilutes what any one of them gets, without making the resulting model good for either.
- Condition — applies when: the target language has more than one identifiable variant or closely related sibling language already known.

### Solution

**4. Reuse and fine-tune an existing open model rather than build from scratch**
- Dimension: Solution
- Stage: Explore
- Type: Strategic Decision
- Decision: Fine-tune an existing open model, bootstrapped from a related higher-resource language, instead of building model architecture from zero.
- What this looked like here: AI4Bharat fine-tuned an existing open model, bootstrapping Bhili from Marathi.
- Alternative considered: Building Bhili's ASR/NMT/TTS models from scratch.
- Why: For a genuinely low-resource language, the real bottleneck is data quality and institutional process, not architecture.
- Condition — applies when: a related, higher-resource language exists to bootstrap from.

**5. First attempt used clean studio audio; failed on real telephony conditions**
- Dimension: Solution
- Stage: Explore
- Also relevant at: Define
- Type: Failure and Fix
- Failure: The first attempt at Bhili data collection gathered clean, studio-style audio.
- Fix: Shifted sampling toward conversational and spontaneous speech, designed explicitly for telephony and low latency, aiming for at least 25% of speech data at 8 kHz.
- Insight: Clean studio audio performs poorly on the real telephony calls most rural users actually make — the deployment channel has to dictate recording conditions from session one.
- Condition — applies when: the deployment channel includes basic-phone or IVR access.

**6. Scope to the three-model minimum (ASR+NMT+TTS)**
- Dimension: Solution
- Stage: Define
- Type: Strategic Decision
- Decision: Treat ASR, NMT, and TTS as the minimum capability bundle needed to bring a language onto the AI map; treat LLM fine-tuning as a separate, later workstream.
- What this looked like here: Bhili's effort scoped to these three models.
- Why: Translating into a higher-resource language lets an already-capable LLM handle downstream sophistication without first needing the far larger data volumes LLM fine-tuning requires.
- Condition — applies when: foundational translation and speech models don't yet exist for the language.

**7. Data volume and composition target table**
- Dimension: Solution
- Stage: Define
- Also relevant at: Pilot
- Type: Toolkit Asset
- Purpose: For sizing a Phase 1 collection plan — how many hours and sentence pairs to collect, of which types — so the effort neither collects too little data to be usable nor spends time and budget collecting more than the current stage needs.
- Toolkit asset: A target table by data type — translation pairs, naturalistic speech, telephony-grade (8 kHz) speech, studio TTS data, conversational speech. Zero-resource practical minimums: ~60–100 hours of speech and 25,000–40,000 sentence pairs. Production-grade targets (Bhashini DMU/AI4Bharat 2022 benchmark): ~300 hours transcribed speech, 100,000 sentence pairs, 40 hours studio TTS per voice artist.
- Reusable as-is: Directly usable to set both a Phase 1 plan and a longer-term production target from any starting point.
- Condition — applies when: setting collection targets for a new low-resource language.

**8. First collection cycle produced Marathi-mixed "impure" Bhili; fixed via iterative small-batch cycles**
- Dimension: Solution
- Stage: Pilot
- Type: Failure and Fix
- Failure: In the first collection cycle, contributors' spoken Bhili was heavily mixed with Marathi, a natural consequence of how often they interface with Marathi-speaking institutions.
- Fix: Running collection in iterative cycles (roughly 50–100 hours at a time) caught the mixing early, before a full dataset was locked in.
- Insight: Data-quality problems specific to a low-resource language surface fastest through iterative small-batch collection with review in between.
- Condition — applies when: the target language coexists closely with a dominant regional language and speakers habitually code-switch in institutional contexts.

**9. Weight data collection toward an already-named deployment domain**
- Dimension: Solution
- Stage: Pilot
- Type: Tactical Decision
- Decision: Where a first deployment domain is already named, weight collection more heavily toward that domain than a generic split.
- What this looked like here: Bhili's collection ran roughly 50% generic / 50% agriculture-specific.
- Alternative considered: A roughly 70% generic / 30% domain-specific split, treated as the more typical default when no use case is yet named.
- Why: Front-loading domain-specific data gets the one deployment that has to work sooner to acceptable accuracy, at the cost of needing supplemental collection before serving a second domain well.
- Condition — applies when: the first deployment target and domain are already named.

**10. Evaluation scorecard — WER / BLEU / MOS plus qualitative field checks**
- Dimension: Solution
- Stage: Pilot
- Also relevant at: Scale
- Type: Toolkit Asset
- Purpose: For deciding, at each stage gate, whether the ASR/NMT/TTS models are accurate and natural enough to move toward deployment, and for holding a technical partner to a shared, objective bar.
- Toolkit asset: Word Error Rate (ASR), BLEU (NMT), Mean Opinion Score (TTS), plus qualitative field checks (naturalness, background-noise handling, turn-taking, whether the conversation feels safe). Rough thresholds: WER <20% usable / <10% production-grade; BLEU >20 usable / >35 near-human; MOS ≥3.5 acceptable.
- Reusable as-is: Hand this scorecard to any technical partner and request the same numbers at each phase gate.
- Condition — applies when: assessing readiness to move an ASR/NMT/TTS pipeline between stages.

### Institution

**11. Champion-led model: a genuinely committed, high-authority champion is a precondition**
- Dimension: Institution
- Stage: Explore
- Type: Strategic Decision
- Decision: Find, or become, a person with real authority and genuine personal commitment to lead the effort — before finalizing a data-collection plan.
- What this looked like here: Nandurbar's District Collector personally drove community engagement, contributor recruitment, and inter-departmental coordination throughout.
- Alternative considered: Approaching a district or region through cold outreach, asking them to build the model without an empowered individual leading from within.
- Why: Coordinating multiple departments and sustaining community engagement over months requires someone empowered to push through friction that procurement sign-off alone can't.
- Condition — applies when: any government, university, or NGO is anchoring a language effort.

**12. The four-phase process: Foundations → Initial Sprint → Deployment → Institutionalisation**
- Dimension: Institution
- Stage: Explore
- Also relevant at: Define, Pilot, Scale
- Type: Playbook
- Playbook:
  1. **Phase 0 — Foundations (Weeks 1–6):** Decide who is leading the effort — a government body itself, a community/civil-society network, or an external funder acting as convener — since this determines who owns the data, how contributors are recruited, and how deployment gets negotiated later. Assign one accountable, empowered project lead. Register the project with the relevant national language-data platform for your context (Bhashini/ULCA in India, Lacuna Fund in Africa, Mozilla Common Voice for global volunteer collection) — this gives the project access to that platform's hosting, compute, and institutional backing from the start, instead of having to arrange each separately once collection is underway. Name the deployment target, select a data-collection approach, hold a community launch event, agree a script with elders and linguists, build a reference lexicon, recruit diverse contributors, set compensation terms.
  2. **Phase 1 — Initial Data Sprint (Weeks 6–10):** Collect the foundational dataset in one focused campaign, with collection, checking, and validation running in parallel. Ship a lightweight keyword-spotting model within weeks as the first tangible community deliverable.
  3. **Phase 2 — Deployment and Deepening (Months 3–12):** Deploy into the live service, run field demonstrations and a structured community feedback loop, expand the dataset toward 100–200 hours.
  4. **Phase 3 — Institutionalisation and Replication (Month 12+):** Transition ownership to standing infrastructure, open the dataset publicly, begin replication to adjacent languages, publish a handbook.
- Note: Skipping Phase 0's governance and community steps to reach data collection faster is the most common failure mode.
- Condition — applies when: starting a language-enablement effort from little or no existing digital presence.
- Before → After: Nandurbar compressed Phase 0 and Phase 1 into roughly one month against a hard external deadline; less centralized or lower-capacity efforts typically take 1.5–2× longer.

**13. The Replication Checklist**
- Dimension: Institution
- Stage: Explore
- Also relevant at: Define
- Type: Toolkit Asset
- Purpose: For checking, before committing to data collection, whether the governance, community, and linguistic preconditions are actually in place.
- Toolkit asset: A go/no-go checklist across Governance (institutional anchor, named deployment platform, data-ownership plan, maintenance plan), Community (community meeting held, trusted local recruitment partner, fair compensation plan, script agreement), and Linguistics (linguist/research institute engaged, 5+ bilingual translators/validators, elder speakers available, dialect variation mapped).
- Reusable as-is: Each "No" becomes a Phase 0 task, not a stop signal.
- Condition — applies when: assessing readiness before significant data collection begins.

**14. Recruit contributors through existing government line-departments**
- Dimension: Institution
- Stage: Define
- Type: Strategic Decision
- Decision: Recruit voice contributors through the local administration's own line departments rather than through independent vendor outreach.
- What this looked like here: Teachers appointed by the education department, ASHA workers from health, and extension workers from agriculture became the first protocol of contributors.
- Alternative considered: Vendor-driven onboarding of contributors not already known to the local administration.
- Why: The administration already knew who the credible, capable bilingual speakers were, collapsing two trust problems (is this legitimate? are these people any good?) into one already-solved relationship.
- Condition — applies when: a trusted government administration is the convening authority and already employs people who speak the target language.

**15. Pay contributors promptly, verifiably, and directly for completed work**
- Dimension: Institution
- Stage: Pilot
- Type: Tactical Decision
- Decision: Pay contributors directly and quickly once a specific task is verified complete, rather than through delayed or batched payment.
- What this looked like here: Contributors were paid per word (~₹1 to validate, ~₹2 to transcribe/translate) via UPI, landing in their account the same day a task was completed; ~₹20 lakh of the ₹27 lakh Phase 1 budget went directly to community compensation this way.
- Why: For communities with legitimate, historically grounded wariness of extraction, payment that is fast, tied to verified work, and visible is itself a trust signal. UPI is the local rail used here; the transferable property is prompt, verifiable, direct payment.
- Condition — applies when: contributors are individual community members providing time and expertise to an institution-led effort.

**16. Explicit, revocable, regulation-aligned consent built in from day one**
- Dimension: Institution
- Stage: Pilot
- Also relevant at: Define
- Type: Strategic Decision
- Decision: Require specific written consent describing what's being contributed and how it will be used, before any data collection begins, with a mechanism to withdraw consent and request deletion.
- What this looked like here: All Bhili contributors gave consent (digital or physical) before contributing; the effort describes DPDP-style mechanisms for storage, withdrawal, and deletion as already working.
- Why: Voice data is personally identifying, and fear of surveillance or misuse is a legitimate concern for these communities — a weak consent process reinforces exactly the extraction fear the effort otherwise works to dispel.
- Condition — applies when: collecting voice or personal data under a jurisdiction with a formal data-protection regime.

**17. Multi-stakeholder standing operating model, not a one-time grant sprint**
- Dimension: Institution
- Stage: Scale
- Type: Strategic Decision
- Decision: Assign each partner a defined, continuing role — monitoring, feedback, retraining — rather than treating the project as complete once the first deployment ships.
- What this looked like here: AI4Bharat, Bhashini, and the local administration are each described as needing standing roles for ongoing monitoring and feedback, with a plan to extend the same infrastructure to sectors beyond agriculture.
- Alternative considered: Treating the effort as complete once the first deployment goes live, with no standing roles afterward.
- Why: A model whose only institutional memory is a single funded team's presence disappears when that funding or those people move on.
- Condition — applies when: initial funding or mandate was tied to a single deployment milestone.

### Ecosystem

**18. Partner-role map**
- Dimension: Ecosystem
- Stage: Define
- Also relevant at: Explore
- Type: Toolkit Asset
- Purpose: For identifying, before model work starts, who needs to be involved and what each person or partner is responsible for, so no essential role is silently missing.
- Toolkit asset: A role-by-role map — convening authority; community contributors (multilingual translators, script-reading contributors, speech-only contributors); linguistic experts/validators; community leaders/influencers; data-collection platform; national AI platform; technical partner; deployment partner — each with what they do.
- Reusable as-is: Copy the table and fill in local names against each role before starting.
- Condition — applies when: assembling a new language-enablement effort of any kind.

**19. Data-collection platform comparison and selection criteria**
- Dimension: Ecosystem
- Stage: Define
- Also relevant at: Explore
- Type: Toolkit Asset
- Purpose: For choosing which data-collection platform or vendor fits a given context, instead of defaulting to whichever platform is best known.
- Toolkit asset: Categorized comparison — ethical/community-centred (BhashaDaan, Shoonya, Karya, Josh Talks AI), global volunteer (Mozilla Common Voice, Zindi), commercial (Appen, TELUS/Lionbridge, Sama, NextWealth, isahit), university/research-network-led — against connectivity, community literacy, and budget.
- Reusable as-is: Use directly to shortlist a platform for a new context.
- Condition — applies when: selecting a data-collection approach for a new effort.

**20. Release data openly rather than keeping it inside one vendor's platform**
- Dimension: Ecosystem
- Stage: Define
- Type: Tactical Decision
- Decision: Negotiate explicitly with the technical partner to release the resulting dataset openly on a national platform, in exchange for subsidised model-building, rather than keeping the data exclusive to one vendor's platform.
- What this looked like here: AI4Bharat trained the Bhili models at no direct cost to the district; in exchange, the dataset was released openly on AI Kosh and Bhashini/ULCA rather than remaining solely inside Karya's platform.
- Alternative considered: Paying for model-building outright and keeping the resulting dataset exclusive to the district and its vendor.
- Why: This makes one asset serve two purposes — it funds the model-building work without extra project budget, and it keeps the data portable and reusable beyond whichever single vendor collected it.
- Condition — applies when: a technical partner is willing to subsidise model training in exchange for open data.

**21. Isolated local data-collection effort connected late to technical/deployment partners**
- Dimension: Ecosystem
- Stage: Define
- Type: Failure and Fix
- Failure: Nandurbar's original Bhili data-collection work order ran independently of the model-building and deployment side, with no explicit target for conversational speech and no named deployment platform.
- Fix: EkStep connected the effort to AI4Bharat, Bhashini, and MahaVISTAAR, and revised the collection scope before the sprint was complete.
- Insight: A data-collection effort with no tie to a technical or deployment partner produces a dataset, not a pathway — the connection has to happen early.
- Condition — applies when: a sub-national government unit begins language data collection before technical and deployment partners are engaged.

**22. Source scarce linguistic-expert capacity through local government channels**
- Dimension: Ecosystem
- Stage: Define
- Also relevant at: Explore
- Type: Strategic Decision
- Decision: Where qualified bilingual linguistic experts are scarce, use local government identification channels to locate them, rather than relying on open or vendor-led recruitment to surface them.
- What this looked like here: Finding linguistic experts for Bhili was genuinely difficult given how few exist in the community; the task was handled by local government teams and administration, with the education department suggesting candidates.
- Alternative considered: Open or vendor-led recruitment to find linguistic experts.
- Why: In a genuinely low-resource-language community, qualified bilingual experts are rare and not easily found through open recruitment; local government departments already have visibility into who in the community has this skill.
- Condition — applies when: the target language has very few qualified bilingual linguistic experts, which is typical for tribal or zero-resource languages.

**23. Open methodology handbook and open dataset release**
- Dimension: Ecosystem
- Stage: Scale
- Also relevant at: Define
- Type: Toolkit Asset
- Purpose: The handbook is for transferring the step-by-step method — governance steps, recruitment approach, data specs — to a new team with no direct access to the original implementers. The open dataset release is for letting others — researchers, other government departments, other language efforts — build on the underlying data without re-collecting it themselves.
- Toolkit asset: A published process handbook documenting the methodology end-to-end, alongside the open dataset release described in Unit 20.
- Reusable as-is: Publishing the handbook is what let another team pick up the work directly — a working bot alone would not have made that possible.
- Condition — applies when: the goal is reusable public infrastructure rather than a single deployment.

---

## 4. Toolkits and playbooks

| Unit | Asset | Reuse condition |
| --- | --- | --- |
| 7 | Data volume & composition target table | Setting Phase 1 collection targets for any low-resource language |
| 10 | WER / BLEU / MOS scorecard + qualitative field checks | Assessing readiness to move between stages |
| 12 | Four-phase process | Any effort starting from little or no digital presence |
| 13 | The Replication Checklist | Pre-flight readiness check before data collection |
| 18 | Partner-role map | Assembling the ecosystem for a new effort |
| 19 | Data-collection platform comparison | Choosing a data-collection approach |
| 23 | Open methodology handbook + dataset release | Enabling another team to replicate without the original implementers |

---

## 5. Problem→solution patterns

| Problem | Root cause | Solution | Result | Condition |
| --- | --- | --- | --- | --- |
| Collected audio performed poorly on real usage | First collection used clean, studio-style recordings, not telephony-grade audio | Shifted sampling toward conversational speech, designed for 8 kHz telephony and low latency | Recordings matched the real channel most rural users actually use | Applies when the deployment channel includes basic-phone or IVR access |
| Collected "Bhili" speech was mixed with Marathi | Contributors habitually code-switch when interfacing with institutions | Ran collection in iterative small-batch cycles with review between cycles | Mixing was caught and corrected before the full dataset was locked in | Applies when the target language coexists closely with a dominant regional language |
| Data collection produced a dataset with nowhere to go | Effort ran independently of model-building and deployment partners | Connected to a technical partner and deployment platform; revised the collection scope | Requirements corrected mid-course, before the sprint completed | Applies when a government unit starts collection before technical/deployment partners are engaged |

---

## 6. Retrieval guide

- *"How do we pick which language or community to start with?"* → Unit 1
- *"Should we build one model that covers everything, or start narrow?"* → Unit 2
- *"Our language has multiple dialects — how do we handle that?"* → Unit 3
- *"Do we need to build our own model architecture from scratch?"* → Unit 4
- *"Our audio doesn't work well on phone calls — why?"* → Unit 5
- *"What's the minimum viable set of AI capabilities we need?"* → Unit 6
- *"How much data do we need to collect, and of what kind?"* → Unit 7
- *"How do we make sure collected language data is actually 'pure'?"* → Unit 8
- *"What mix of general vs. domain-specific data should we collect?"* → Unit 9
- *"How do we know if our models are good enough to deploy?"* → Unit 10
- *"We don't have a strong internal champion — does that matter?"* → Unit 11
- *"What's the overall sequence for running an effort like this?"* → Unit 12
- *"Are we actually ready to start collecting data?"* → Unit 13
- *"Should we use a vendor to recruit contributors, or do it ourselves?"* → Unit 14
- *"How should we pay contributors to keep them motivated?"* → Unit 15
- *"What consent process do we need for voice data?"* → Unit 16
- *"How do we sustain this after initial funding ends?"* → Unit 17
- *"Who needs to be involved in an effort like this?"* → Unit 18
- *"Which data-collection platform should we use?"* → Unit 19
- *"A technical partner is offering free model training — what's the catch?"* → Unit 20
- *"We already started collecting data on our own — is it too late to bring in partners?"* → Unit 21
- *"We can't find anyone who can validate our language — what do we do?"* → Unit 22
- *"How do we help another team replicate what we did?"* → Unit 23

---
---

### Provenance appendix *(internal — not adopter-facing)*

| Source file | Covers | Notes |
| --- | --- | --- |
| Bhili pathway v1 (docx/PDF), as of July 2026 | Section 1 (all fields); Units 1, 3, 4, 5, 9, 11, 14, 17, 18 (partial), 19 (partial), 20, 21; Section 5 | Primary source — the finished narrative write-up of the deployment |
| Bringing a Language to the AI Map (blueprint), Santosh Kevlani / EkStep Foundation | Units 2, 6, 7, 10, 12, 13, 18 (partial), 19 (partial), 23; Section 0 framing | Primary source — adds the four-phase process, cost components, thresholds, and checklist not in the Bhili write-up |
| Otter_Bhili_transcript (interview, Santosh Kevlani) | Units 8, 9, 16, 22; additional detail supporting Units 1, 4, 11, 14, 15, 18 | Primary source for the code-mixing fix (Unit 8), domain-mix decision (Unit 9), and linguistic-expert sourcing (Unit 22); otherwise largely confirms the Bhili pathway document |
