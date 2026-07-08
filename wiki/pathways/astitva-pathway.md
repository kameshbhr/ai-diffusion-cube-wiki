# Enabling Voice AI Models for Bhili Language

---

**Deployment:** Project Astitva — Dehvali Bhili Language Enablement for Voice AI
**Contributor:** EkStep Foundation
**Sector:** Cross-sector (initial deployment: Agriculture via MahaVISTAAR; planned: Health, Education, Administration)
**Geography:** Nandurbar district, Maharashtra, India
**Actor type:** Government (District Administration) + Civil society (Karya, EkStep) + Academic (IIT Madras) + National infrastructure (Bhashini)
**Journey stage:** Pilot → Scaling
**Dimensions covered:** A, B, C, D, E, F
**Deployment status:** Active — Dehvali Bhili integrated into MahaVISTAAR; expansion to additional languages and use cases underway
**Contact for peer connection:** 

---

## Summary

Project Astitva is a district-led initiative in Nandurbar, Maharashtra that built a participatory voice data collection and language enablement pipeline for Dehvali Bhili — a tribal language. Nandurbar district has over 9 lakh tribal residents across 18+ languages and dialects, while Dehvali Bhili itself is spoken by a much larger community of roughly ten million tribal speakers across the wider multi-state region. No usable digital dataset for Bhili previously existed. Bhili had no script, no formal teaching, fewer than a hundred existing books, and no prior audio or video assets. Rather than building from zero, the project reused an existing open AI4Bharat/IIT Madras model base, bootstrapped Bhili from Marathi as a linguistically related high-resource neighbour, recorded through an existing community radio station, and hosted the results on Bhashini's sovereign infrastructure. Working with community contributors, linguistic experts, and technology partners, the district collected 40,000+ sentence recordings (25,000 agricultural, 15,000 non-agricultural) plus roughly 68 hours of spontaneous, studio, and conversational speech, processed them through a multi-layer quality-assured pipeline, and integrated the resulting language model into MahaVISTAAR, Maharashtra's agricultural extension platform, as the first practical deployment. The foundational data sprint ran in roughly a month and the wider Phase 1 in about two months; the pilot cost approximately ₹27 lakh, government-funded, of which about ₹20 lakh reached community contributors directly via UPI.

This pathway is useful to any adopter facing the challenge of enabling an under-resourced language for voice AI before any deployment using that language can be built. It is upstream of any specific use case. The output is language infrastructure — a trained ASR/NMT/TTS/LLM stack and the open data that enables it — that can then be deployed across multiple use cases by any adopter.

---

## A. Problem Orientation

**Snapshot**

Millions of speakers of tribal and low-resource languages are excluded from public services and AI-enabled tools because no voice models exist for their language. The person is specific: a Dehvali Bhili speaker in Nandurbar, often with low or no literacy, using a keypad phone or basic Android handset, unable to access services designed for majority languages. Governance operates in a few dominant languages while people speak in many — the disconnect left farmers dependent on agriculture officers as intermediaries. The problem was not a lack of internet or devices; it was a lack of language infrastructure. Because Bhili had no digital foundation — no script, no formal teaching, fewer than a hundred books, no audio or video assets — no commercial actor had a market reason to build one, and the gap was never going to close on its own.

In Nandurbar, over 9 lakh tribal residents speak over 18 languages and dialects including Bhili, Pawari, Kokani, and Mavchi — a district-level headcount across multiple tribal languages, not a Bhili-specific count. Dehvali Bhili itself is spoken by a much larger community of roughly ten million tribal speakers across the wider region spanning several states, of whom Nandurbar's Bhili speakers are one part. The linguistic diversity within a single district signals how quickly a language name can mask enormous dialect variation. Dehvali Bhili was chosen as the first language to enable under Project Astitva.

The participatory design approach — community members co-creating datasets, language experts validating outputs, feedback loops incorporating local dialects — was the mechanism through which user agreement was demonstrated rather than assumed. Early field signals after integration into MahaVISTAAR confirmed the direction: farmers engaged more confidently when information was delivered in Dehvali Bhili, and frontline workers reported smoother communication with reduced need for repeated explanation and informal translation.

**Learnings**

- Frame the problem as language exclusion, not technology absence. Voice AI is the response to exclusion, not the starting point. Projects that start with the technology rather than the excluded person tend to build for the wrong user.
- Define the target language precisely before starting. A language name can mask enormous dialect variation. Dialect mapping must precede data collection, not follow it.
- Before assuming zero, audit what already exists for the target language — textbooks, written materials, earlier recordings, prior linguistic work, even informal. Any existing material reduces the zero-to-one effort. In the Indian context, check Bhashini for prior work on the language.
- Voice alone may not be sufficient in all downstream use cases — multimodal accessibility may eventually be needed. But this is a use-case decision, not a language-building decision. Don't let it complicate the infrastructure project.
- The non-AI alternative — human translators or officers acting as intermediaries — does not scale to a community of this size and leaves nothing reusable behind. A single investment in language infrastructure becomes a public asset that many services can draw on later; the case for AI here is about what removing the language barrier permanently unlocks, not a preference for automation over people.

**Gaps**

The initial phase set supply-side input targets (sentences, hours of speech) but not outcome metrics. Success was defined qualitatively — a farmer asking a question in Bhili and receiving an accurate answer in Bhili as a live public service — and the standard measurement framework (Word Error Rate, BLEU, Mean Opinion Score) was used alongside field testing, but audited, live, post-deployment figures for Bhili are not documented, so no outcome numbers can be stated with confidence.
- What failure modes arise when problem framing is wrong at this stage — e.g. choosing a language without adequate dialect mapping — is not captured.

---

## B. Architecture

**Snapshot**
The gap Astitva identified was that individual language models were being built through Bhashini and other efforts, but there was no open-source orchestration layer to run them on — building cars without roads. The project's models were fine-tuned from an existing open AI4Bharat/IIT Madras base across ASR, NMT, and TTS, with an LLM fine-tuned on a Qwen base, and connected via the VoiceERA orchestration layer hosted on Bhashini's sovereign infrastructure. 

The dataset itself — 40,000+ sentence recordings plus roughly 68 hours of spontaneous, studio, and conversational speech — is available as an open repository on Bhashini (also released on AI Kosh) for nationwide replication. Choosing open, model-agnostic models and sovereign hosting kept the project free of vendor lock-in and independent of any commercial platform whose priorities could shift.

The Astitva corpus comprised 25,000 agriculture sentences, 15,000 non-agriculture sentences, 60 hours of spontaneous speech, 6 hours of studio speech, and 2 hours of conversational speech — all in Dehvali Bhili, with the foundational sprint completed in roughly a month. Recording used an existing community radio station rather than a purpose-built studio.

All language data was collected centrally through Karya's platform — recordings, transcriptions, and quality validations managed in one place. The multi-layer quality pipeline ran three parallel tracks simultaneously: production (contributors recording), checking (checkers reviewing contributor output in real time via Shoonya, the annotation tool), and validation (linguistic experts and the Tribal Research Institute reviewing checker output), following a Maker–Checker–Superchecker model. Kathbath was used for the underlying collection process. Digital dashboards and leaderboards provided real-time visibility into progress and accountability across all tracks.

**Learnings**

- Reuse the existing model layer wherever possible. Fine-tuning an existing open model base, and bootstrapping a very low-resource language from a linguistically related higher-resource one, saved both time and cost compared with building from scratch.
- Build the orchestration layer as an open, model-agnostic component and make the dataset an open repository from day one. The intent to share shapes decisions during collection — open licensing, platform-neutral hosting, documented methodology. Retrofitting openness after the fact is harder and often doesn't happen.
- Collect conversational speech, not just read speech. People read differently from how they speak. Read-only datasets produce models that fail in real conversation. Both types are needed; conversational data cannot simply be scripted and recorded — it requires deliberate design.
- Match recording quality to deployment conditions. Smartphones and laptops record at 16kHz; telephony lines operate at 8kHz. Data collected at 16kHz produces a model that fails on actual telephony calls. Either collect at 8kHz or deliberately downsample during training. Design the recording specification before collection begins, not after.
- The 8kHz vs. 16kHz mismatch and the read vs. conversational speech gap were both discovered post-deployment in Astitva, requiring rework. Both must be in the original collection plan.
- Separate domain-specific data from general data in the collection design. Domain specificity matters for model accuracy in sectoral deployments. In Astitva, contributors from different professional domains (health, revenue, agriculture) collected domain-relevant sentences — this was a design decision, not an incidental outcome.
- Dialect representation must be deliberate in testing. Approval from a small group of testers does not constitute proof if dialect variation is not represented in the testing panel. Map which dialects have gaps and target supplementary collection accordingly.

**Gaps**
- Sentence selection methodology is not documented — which domains to prioritise, what coverage logic, how sentences are constructed or sourced for a language with limited written material.
- No documented accuracy benchmarks or ASR/NMT/TTS error rates at different data volumes for Bhili specifically. The measurement framework (WER, BLEU, MOS) is known, but audited results are not, so a new adopter cannot answer "is our model good enough yet?"
- What formal agreements existed between the District Administration and external partners before collection started — MOUs, data sharing agreements — is not documented. Whether participation was governed by formal instruments or informal arrangements is unknown.
- The precise licence terms for the dataset are not settled. It is known to be released openly on AI Kosh and hosted on Bhashini, and is framed as community-owned, but whether that is a permissive open licence or a more tiered, community-protective one is not stated for Bhili specifically.
- DPDP 2023 compliance for community voice data collection is not addressed in these materials. Key open questions for any adopter in India: who is the data fiduciary for the language corpus; what are the consent and withdrawal rights for community contributors whose voice recordings are embedded in a publicly hosted model; and how DPDP obligations apply when the dataset is hosted as an open repository on Bhashini. These are unresolved and a new project should seek legal guidance before beginning data collection.
- Whether there were any tribal data rights considerations specific to the community whose language was collected is not addressed.

---

## C. Institution

**Snapshot**

The District Administration Nandurbar led Project Astitva, with the District Collector's office as the convening authority. In Maharashtra, the Collector sits above all line departments, enabling cross-sector mobilisation — Education, Agriculture, IT, and Tribal Welfare — in a legally and practically feasible way. Maharashtra's delegated financial powers and district-level funds provided flexibility to act without requiring state-level approval for each step — a structural enabler that may not exist in the same form elsewhere. This authority is what compressed coordination timelines that no technology team could have compressed alone.

The project was framed as a matter of district and community pride, not just a technical exercise. This framing sustained motivation through a demanding one-month intensive effort across multiple actors. When initiatives are driven by local leadership, a sense of confidence ripples across all stakeholders.

The Phase 1 collection sprint was government-funded, at a pilot spend of approximately ₹27 lakh, with no separate model-build cost since training was effectively absorbed by the research partner in exchange for open data. Who funds ongoing operation beyond the pilot is not specified in the source documents.

The Tribaldaan conclave with Bhashini was an explicit trust-building event, bringing the community together before data collection began to establish what was being built, why, and on what terms. Strict monitoring and accountability were maintained throughout the data collection phase, with irregularities addressed immediately. Accountability for the data quality process rested with Karya's quality management infrastructure and the District Administration as the convening institution.

**Learnings**

- The institution that convenes must have standing in the community whose language is being built. An external organisation cannot substitute for this. It can support and implement; the convening authority must be local and trusted.
- In-house testing at each phase before wider release is non-negotiable. The institution whose name is on the model must put a human lens on it. This cannot be outsourced to the technology partner or a third-party testing team.
- Build a dedicated PMU before the project begins. Cross-actor coordination across community, government, academic, and technology domains under time pressure cannot be a part-time responsibility added to someone's existing role.
- Build strong safeguards against abuse into the institutional design from the start — not as a compliance layer added later. In Astitva, strict monitoring was maintained throughout the data collection phase and irregularities were addressed immediately. This is an institutional accountability function, not a technical one.
- Check whether the financial flexibility mechanisms available in Maharashtra (delegated district-level funds) exist in the target state or geography before designing the funding and approval model. Where they don't exist, a different institutional anchor — state-level ministry, a national programme — may be needed.

**Gaps**

- What happens when the institutional champion transfers mid-project is not addressed. This is a real and common risk in government-led district projects in India.
- The specific risks that had to be managed are named at a high level — community mistrust, data quality, and the tension between speed and quality, addressed through transparency and repeated engagement, multi-layer validation, and a mid-course correction toward the MahaVISTAAR use case — but no specific interpersonal or contractual friction between named partners is recorded, so the operational detail of how resistance was overcome is not fully captured.
- What institutional knowledge needs to be retained after the project ends — who holds understanding of the dataset, the model, the community relationships — is not captured. The risk of knowledge walking out when the PMU disbands is unaddressed.
- How the monitoring and irregularity-response mechanism was structured operationally — what was monitored, by whom, at what frequency, and what constituted an irregularity — is not described.
- Who is responsible for governance or oversight of the live Bhili deployment today is not documented. What is recorded is that the data sits openly on Bhashini and is framed as community-owned; no standing governance body is described.
- Whether higher-level political support (state or national) was needed and obtained at any point is not documented.

---

## D. Ecosystem

**Snapshot**

The actor map for a low-resource language project is more complex than a standard AI deployment. Five named partner organisations worked together in Project Astitva, each with a distinct role:

- **District Administration Nandurbar** — leadership, coordination, funding support, convening authority
- **EkStep Foundation** — held coordination across every actor and drove the effort to launch, acting as a neutral orchestrator
- **Karya** — data collection platform, dashboards, leaderboards, task management, quality process
- **AI4Bharat / IIT Madras** — model development across ASR, NMT, TTS, and LLM fine-tuning; technical validation
- **Bhashini** — open-source hosting, national platform support
- **State Agriculture Department and POCRA** — service integration, deployment through MahaVISTAAR extension systems

Community contributors — native Dehvali Bhili speakers across agriculture, health, and revenue domains — were the primary content creators. They are not a named organisation but a structured participant group, with defined eligibility, compensation, and accountability. Contributors were selected against explicit eligibility criteria — proficiency in the target language, literacy and typing skills, and local ownership in language standardisation — and spanned multiple domains: health workers contributed sentences in health and social service contexts, revenue staff contributed administrative domain sentences, and community members and the district's own Bhili-speaking agriculture officers contributed agriculture and daily-life sentences. Contributors were compensated directly over UPI without an intermediary, on the order of one to two rupees per word; of the roughly ₹27 lakh pilot spend, about ₹20 lakh reached communities directly.
Linguistic experts and the Tribal Research Institute validated outputs. 

The practitioner interview generalises this actor map into a replicable blueprint for any low-resource language project:
1. **Convening authority** — holds the project and says "this runs in my name"
2. **Community speakers** — native speakers who provide recordings
3. **Annotators** — people who transcribe spoken audio into text of the language
4. **Linguistic validators** — experts who validate annotator output for grammatical and phonetic accuracy. Native speakers can record and are essential, but they cannot validate their own grammatical accuracy — the same way a fluent speaker cannot always identify errors in written text. A linguistic expert who understands the structure of the target language is a distinct and non-substitutable role. For languages with no academic tradition, this person may be hard to find and may need to be developed through the project itself.
5. **Data collection platform provider** — the tool and infrastructure for recording and transcription
6. **Specialised data partner** — an organisation with expertise in ethical data collection from underserved communities (Karya in Astitva)
7. **Model builder** — an institution that uses the dataset to train ASR and other models (IIT Madras in Astitva)
8. **Infrastructure and hosting provider** — where the model lives (Bhashini, national GPU)
9. **Neutral orchestrator** — a party that brings actors together who would otherwise not find each other
10. **PMU** — project management unit for day-to-day coordination

**Learnings**

- Do not assume actors will find each other. IIT Madras had relevant model-building capability but had no way of knowing the Astitva effort was happening. The neutral orchestrator must actively map the relevant ecosystem and make introductions — this is not a passive coordination role.
- The specialised data partner is not substitutable by a general implementation partner. The skills for ethical, high-quality data collection from underserved communities are distinct and specific.
- Community contributors are not just users or beneficiaries — they are active participants in the production chain, responsible for language data creation, validation, and local ownership. Their participation must be designed, compensated, and governed — not assumed.
- Compensation for community contributors must be explicit, fair, and paid reliably — payments tied to verified contributions, with direct transfers to registered accounts.
- Scope the data collection explicitly to its intended use and communicate this transparently to participants upfront. In Astitva, data was collected explicitly for open-source ASR, machine translation, and TTS — this purpose was stated clearly before any recording began. Participants were anonymised through unique registration codes. Payments were tied to verified contributions only, with direct transfers to registered accounts.

**Gaps**

- How to find or assess a linguistic validator for a language with no academic tradition is not documented. Linguistic experts and the Tribal Research Institute are named as the validating body, but the recruitment or assessment process is not described. This is a genuine bottleneck with no replication guidance.
- How annotators are recruited, trained, and quality-checked beyond the eligibility criteria is not described. Shoonya is named as the annotation tool used, but the annotation methodology itself — what the transcription process looks like, what quality standards apply, how disagreements are resolved — is absent.
- What the coordination mechanism looked like day-to-day — how actors communicated, how decisions were escalated, what the PMU's authority was — is not documented.
- How community trust was built operationally beyond the Tribaldaan conclave — what was said, how scepticism was handled, what commitments were made — is not captured. Nor is what could cause community trust to collapse mid-project.
- Where partner commitments weakened and how that was managed is not documented.

---

## E. Workforce

**Note on fit**

This dimension was designed for deployments where a frontline workforce absorbs AI into daily practice. At the language-building stage there is no such workforce. Training depth on the AI system and the agency test (whether users become more capable or dependent) both belong to the use-case deployment project that follows, not this one.

The relevant capacity question here is narrower: the community contributors — recorders, annotators, validators — need to be equipped for their role. A second workforce question emerged post-integration: agricultural extension workers and frontline health workers (ASHA/ANM/AWW) absorbed the change when Dehvali Bhili was integrated into MahaVISTAAR. Their experience was positive — the availability of Dehvali Bhili support reduced the need for repeated explanation and informal translation during field visits. But detailed documentation of their onboarding is absent.

**Gaps**

- The training and capacity-building process for community annotators and validators is entirely absent from these materials. This is a significant operational gap for any adopter attempting replication.
- How quality was maintained across a large number of community contributors under time pressure is not documented.
- What specific capabilities extension workers needed to explain or contextualise AI-generated advisory in Dehvali Bhili is not documented.
- Whether there was a structured feedback loop from frontline workers back to model developers — and what that looked like operationally — is not described.

---

## F. Operating Model

**Snapshot**

The foundational data sprint ran in roughly a month, and the wider Phase 1 in about two months — taking Bhili from no digital footprint to a live government-service component in the order of a hundred days. The source documents themselves cite this headline inconsistently, from around sixty to a hundred days, and note that production quality is iterative: this was a strong starting point, not a finished destination. Input targets were met: 25,000 agricultural sentences, 15,000 non-agricultural sentences, 60 hours of spontaneous speech, 6 hours of studio speech, and 2 hours of conversational speech.

The sequenced expansion plan is documented: Dehvali Bhili first, then Mathwadi Bhili, Mavachi, and Pawari; agriculture first, then health, education, and administration. One language, one deployment, prove it, then expand.

The Phase 1 sprint was government-funded at a pilot spend of approximately ₹27 lakh, with no separate model-build cost since training was effectively absorbed by the research partner in exchange for open data; about ₹20 lakh of that reached community contributors directly via UPI. The dataset is available openly on AI Kosh and hosted on Bhashini. Ongoing ownership is intended to sit with the tribal department, with the state having taken over from the district via MahaVISTAAR, though the source documents do not describe a standing governance body for the live deployment today.

**Learnings**

- Set a time-bound target for the initial data collection phase, anchored to a real deployment and a hard external deadline. Astitva's own documents show that early collection drifted without a fixed use case or deadline; anchoring to the MahaVISTAAR use case and a deadline tied to the India AI Impact Summit is what turned a slow documentation exercise into purposeful work. Acknowledge explicitly that limited time increases speed but may affect quality — this trade-off must be actively managed, not assumed away.
- Sequence deliberately: one language, one deployment, prove it, then expand. The Astitva model — Dehvali Bhili into agriculture first, then additional languages and use cases — is a replicable sequencing principle.
- Plan the handover to a permanent institutional owner before the project begins, not after. Tribal department ownership and state-level transition were designed outcomes in Astitva's plan, though the source documents do not confirm whether this transition, or a standing governance model, is actually operating today.
- Design for reuse from day one. Open licensing, platform-neutral hosting, and documented methodology were decided early in Astitva rather than retrofitted, and choosing open, model-agnostic models and sovereign hosting kept the project free of vendor lock-in.
- Data collection is the easy part to talk about and the wrong thing to optimise for. What determines impact is a committed deployment, a convening authority who owns it, and identifying the use case early — a model built without a deployment-first approach creates no impact.

**Gaps**

- How the dataset stays current over time — who is responsible for updates, at what frequency, funded how — is entirely unaddressed. The risk of a static one-time corpus that degrades in relevance is real and undocumented.
- The governance model for the open community language repository is absent — who decides what gets added, what gets corrected, who can use it and on what terms, whether there are restrictions on commercial use.
- The mechanics of the district-to-state transition — what was handed over, to whom, under what terms, with what ongoing support — are not documented.
- What it costs to maintain and expand the Bhili capability annually, beyond the roughly ₹27 lakh Phase 1 pilot spend, is not documented.
- If the language model produces a wrong output in the field — a farmer receives incorrect advisory — what is the path from that error to a fix? This error-correction and accountability pathway is absent.
  
---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| Dehvali Bhili language dataset | Language data / DPG | A validated, open voice dataset for Dehvali Bhili covering agricultural, non-agricultural, spontaneous speech, studio speech, and conversational speech. Immediately reusable by any deployer building a voice AI system for this language. | Bhashini national language repository — bhashini.gov.in |
| Participatory data collection model (Project Astitva) | Process model | Step-by-step model for community co-creation of voice language data: eligibility criteria for contributors, multi-layer quality pipeline (contributors → checkers → validators → linguistic experts), real-time tracking via dashboards. Replicable for any low-resource language. | Project Astitva Booklet, District Administration Nandurbar |
| Data collection quality pipeline | Quality assurance framework | Three parallel task tracks (production + checking + validation simultaneously), digital dashboards and leaderboards for real-time progress and accountability. Designed for high-volume, time-bound collection without sacrificing quality. | Project Astitva Booklet |
| Multi-domain sentence corpus design | Data specification | Template for balancing agricultural (25K sentences), non-agricultural/daily services (15K sentences), spontaneous speech (60hrs), studio speech (6hrs), and conversational speech (2hrs) — with the lesson that conversational speech must be collected separately from read speech. | Project Astitva Booklet; Voice AI Interview transcript (EkStep Foundation) |
| Contributor eligibility criteria | Governance guideline | Selection criteria for community language data contributors: proficiency in the target language, literacy and typing skills, and local ownership in language standardisation. Ensures quality begins at the selection stage. | Project Astitva Booklet |

---

## Related Pathways

- [MahaVISTAAR — Pathway](../pathways/mahavistaar.md) — The agricultural AI advisory deployment for which the Dehvali Bhili language model built under Project Astitva was the first practical use case

## Related Entities

- [District Administration Nandurbar](../entities/nandurbar-district-administration.md) — Convening authority and lead institution for Project Astitva
- [EkStep Foundation](../entities/karya.md) — Cross-partner coordination and orchestration; drove the effort to launch
- [Karya](../entities/karya.md) — Social enterprise providing the data collection platform, dashboards, and task management
- [AI4Bharat / IIT Madras](../entities/AI4Bharat.md) — Model development and technical validation
- [Bhashini](../entities/bhashini.md) — National open-source language platform and hosting infrastructure for the resulting dataset and model
- [State Agriculture Department & POCRA](../entities/maharashtra-agriculture-pocra.md) — Service integration and deployment through extension systems


