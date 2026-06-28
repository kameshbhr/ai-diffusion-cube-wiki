# Enabling Voice AI for a Low-Resource Language
**A Pathway for Adopters**

---

**Deployment:** Project Astitva — Dehvali Bhili Language Enablement for Voice AI
**Contributor:** District Administration Nandurbar; Karya; EkStep Foundation / IIT Madras
**Sector:** Cross-sector (initial deployment: Agriculture via MahaVISTAAR; planned: Health, Education, Administration)
**Geography:** Nandurbar district, Maharashtra, India
**Actor type:** Government (District Administration) + Civil society (Karya, EkStep) + Academic (IIT Madras) + National infrastructure (Bhashini)
**Journey stage:** Pilot → Scaling
**Dimensions covered:** A, B, C, D, E, F
**Deployment status:** Active — Dehvali Bhili integrated into MahaVISTAAR; expansion to additional languages and use cases underway
**Contact for peer connection:** District Administration Nandurbar (via NIC Maharashtra); Karya (karya.ms)

---

## Summary

Project Astitva is a district-led initiative in Nandurbar, Maharashtra that built a participatory voice data collection and language enablement pipeline for Dehvali Bhili — a low-resource tribal language spoken by over 9 lakh residents — where no usable digital dataset previously existed. Working with community contributors, linguistic experts, and technology partners, the district collected 60,000+ voice samples, processed them through a multi-layer quality-assured pipeline, and integrated the resulting language model into MahaVISTAAR, Maharashtra's agricultural extension platform, as the first practical deployment. The entire initial phase was completed within one month.

This pathway is useful to any adopter facing the challenge of enabling an under-resourced language for voice AI before any deployment using that language can be built. It is upstream of any specific use case. The output is language infrastructure — a trained ASR model and the data that enables LLM and TTS — that can then be deployed across multiple use cases by any adopter.

---

## A. Problem Orientation

**Snapshot**

Millions of speakers of tribal and low-resource languages are excluded from public services and AI-enabled tools because no voice models exist for their language. The person is specific: a tribal community member who speaks Dehvali Bhili, has no smartphone, limited dominant-language proficiency, and cannot access services designed for majority languages. The problem is not a lack of internet or devices — it is a lack of language infrastructure.

In Nandurbar, over 9 lakh tribal residents speak over 18 languages and dialects including Bhili, Pawari, Kokani, and Mavchi. 69% of the population belongs to Scheduled Tribes. The linguistic diversity within a single district signals how quickly a language name can mask enormous dialect variation. Dehvali Bhili was chosen as the first language to enable under Project Astitva.

The participatory design approach — community members co-creating datasets, language experts validating outputs, feedback loops incorporating local dialects — was the mechanism through which user agreement was demonstrated rather than assumed. Early field signals after integration into MahaVISTAAR confirmed the direction: farmers engaged more confidently when information was delivered in Dehvali Bhili, and frontline workers reported smoother communication with reduced need for repeated explanation and informal translation.

**Learnings**

- Frame the problem as language exclusion, not technology absence. Voice AI is the response to exclusion, not the starting point. Projects that start with the technology rather than the excluded person tend to build for the wrong user.
- Voice as the channel of choice is not a technology preference — it is a deliberate inclusion decision. For anyone beyond the top 5-6 languages, voice is a must-have channel, not a nice-to-have.
- Define the target language precisely before starting. A language name can mask enormous dialect variation. Dialect mapping must precede data collection, not follow it.
- Before assuming zero, audit what already exists for the target language — textbooks, written materials, earlier recordings, prior linguistic work, even informal. Any existing material reduces the zero-to-one effort. In the Indian context, check Bhashini for prior work on the language.
- Confirm with the downstream deployment team whether outbound calling (the system reaching out to users) is in scope before fixing the architecture. The initial Astitva deployment was inbound — farmers call MahaVISTAAR. Outbound was identified as a future expansion. The Voice AI Interview flags this as a lesson from MahaVISTAAR's broader deployment: the outbound architecture was not planned for at the start, requiring a rearchitecting when the need emerged.
- Voice alone may not be sufficient in all downstream use cases — multimodal accessibility may eventually be needed. But this is a use-case decision, not a language-building decision. Don't let it complicate the infrastructure project.

**Gaps**

- No documented method for mapping dialect variation before data collection begins — how to identify which dialects exist, how many speakers each has, and how to prioritise coverage.
- The initial phase set supply-side input targets (sentences, hours of speech) but not outcome metrics — what change in a user's life would indicate success at twelve months. Formal outcome metrics beyond early field observations are not documented.
- What failure modes arise when problem framing is wrong at this stage — e.g. choosing a language without adequate dialect mapping — is not captured.

---

## B. Architecture

**Snapshot**

The technical stack for voice AI has five layers: ASR (speech to text), LLM (understanding and response generation), TTS (text to speech), an orchestration layer connecting these three, and a telephony layer for voice-channel delivery. The fundamental architectural choice is whether to assemble these as a full stack from one vendor or unbundle and procure each layer separately.

For model selection in a low-resource language context, language support is the threshold criterion — if the model doesn't support the language, nothing else matters. Beyond that: latency optimisation for telephony, sectoral precedent, open source preference, and cost.

The gap Astitva identified was that individual language models were being built through Bhashini and other efforts, but there was no open-source orchestration platform to run them on — building cars without roads. The project contributed an open-source, model-agnostic, language-agnostic, telephony-provider-agnostic orchestration platform hosted on Bhashini. The dataset itself — 60,000+ voice samples — is available as an open repository on Bhashini for nationwide replication.

The Astitva corpus comprised 25,000 agriculture sentences, 15,000 non-agriculture sentences, 60 hours of spontaneous speech, 6 hours of studio speech, and 2 hours of conversational speech — all in Dehvali Bhili, completed in one month.

All language data was collected centrally through Karya's platform — recordings, transcriptions, and quality validations managed in one place. This is distinct from the downstream MahaVISTAAR deployment architecture, which uses an API-separated federated data model. For language model building, centralised collection was the appropriate choice.

The multi-layer quality pipeline ran three parallel tracks simultaneously: production (contributors recording), checking (checkers reviewing contributor output in real time), and validation (linguistic validators and subject experts reviewing checker output). Digital dashboards and leaderboards provided real-time visibility into progress and accountability across all tracks.

Contributors were selected against explicit eligibility criteria: proficiency in the target language, literacy and typing skills, and local ownership in language standardisation. Quality begins at the selection stage, not the review stage.

Contributors spanned multiple domains: health workers contributed sentences in health and social service contexts; revenue staff contributed administrative domain sentences; community members contributed agriculture and daily life sentences.

**Learnings**

- Start full-stack for pilots; unbundle as you mature. Full-stack reduces complexity at the start. Unbundling gives cost control and vendor independence as the deployment grows.
- Single-vendor dependency is the most documented failure mode in these materials. Pilots that started with one vendor and encountered problems faced a painful choice — persist or exit, both costly. Run three vendors in parallel from the pilot stage with split traffic (e.g. 33/33/33 or 60/20/20). The cost premium is marginal (2-5%); the insurance value is far larger.
- Do not use speech-to-speech models at this stage. They bypass the ASR+LLM+TTS stack, are less configurable, less controllable, and significantly more expensive. They have not been reliably implemented for low-resource languages.
- Build the orchestration layer as a DPG and make the dataset an open repository from day one. The intent to share shapes decisions during collection — open licensing, platform-neutral hosting, documented methodology. Retrofitting openness after the fact is harder and often doesn't happen.
- Separate the data layer from the AI layer via standardised APIs, with a named accountable owner for each data source. Data accountability is as important as data quality.
- Token costs for non-English languages are significantly higher — the same sentence requires more tokens. For low-resource languages with conversational back-and-forth interactions, this cost concentration can be severe. Account for it explicitly in model and cost selection.
- Collect conversational speech, not just read speech. People read differently from how they speak. Read-only datasets produce models that fail in real conversation. Both types are needed; conversational data cannot simply be scripted and recorded — it requires deliberate design.
- Match recording quality to deployment conditions. Smartphones and laptops record at 16kHz; telephony lines operate at 8kHz. Data collected at 16kHz produces a model that fails on actual telephony calls. Either collect at 8kHz or deliberately downsample during training. Design the recording specification before collection begins, not after.
- The 8kHz vs. 16kHz mismatch and the read vs. conversational speech gap were both discovered post-deployment in Astitva, requiring rework. Both must be in the original collection plan.
- Separate domain-specific data from general data in the collection design. Domain specificity matters for model accuracy in sectoral deployments. In Astitva, contributors from different professional domains (health, revenue, agriculture) collected domain-relevant sentences — this was a design decision, not an incidental outcome.
- Scope the data collection explicitly to its intended use and communicate this transparently to participants upfront. In Astitva, data was collected explicitly for open-source ASR, machine translation, and TTS — this purpose was stated clearly before any recording began. Participants were anonymised through unique registration codes. Payments were tied to verified contributions only, with direct transfers to registered accounts.
- Dialect representation must be deliberate in testing. Approval from a small group of testers does not constitute proof if dialect variation is not represented in the testing panel. Map which dialects have gaps and target supplementary collection accordingly.

**Gaps**

- Minimum viable dataset threshold is not documented — how many hours, how many speakers, how many sentences before a model reaches usable accuracy. A new adopter cannot answer "is our dataset large enough yet?"
- Sentence selection methodology is not documented — which domains to prioritise, what coverage logic, how sentences are constructed or sourced for a language with limited written material.
- No cost model for the language-building phase — what it costs to collect, annotate, train, and host a model for a low-resource language from scratch.
- No documented accuracy benchmarks or ASR error rates at different data volumes for low-resource languages. A new adopter cannot answer "is our model good enough yet?"
- What formal agreements existed between the District Administration and external partners before collection started — MOUs, data sharing agreements — is not documented. Whether participation was governed by formal instruments or informal arrangements is unknown.
- The mechanics of community data ownership — what legal or governance structure this implies, how it is enforced in practice — are not documented.
- DPDP 2023 compliance for community voice data collection is not addressed in these materials. Key open questions for any adopter in India: who is the data fiduciary for the language corpus; what are the consent and withdrawal rights for community contributors whose voice recordings are embedded in a publicly hosted model; and how DPDP obligations apply when the dataset is hosted as an open repository on Bhashini. These are unresolved and a new project should seek legal guidance before beginning data collection.
- Whether there were any tribal data rights considerations specific to the community whose language was collected is not addressed.

---

## C. Institution

**Snapshot**

The district administration led Project Astitva, with the District Collector as the convening authority. In Maharashtra, the DC sits above all line departments, enabling cross-sector data pooling — from Education, Agriculture, IT, and Tribal Welfare — in a legally and practically feasible way. Maharashtra's delegated financial powers and innovative district-level funds provided flexibility to act without requiring state-level approval for each step — a specific structural enabler that may not exist in the same form in other states or geographies.

The project was framed as a matter of district and community pride, not just a technical exercise. This framing sustained motivation through a demanding one-month intensive effort across multiple actors. When initiatives are driven by local leadership, a sense of confidence ripples across all stakeholders.

The Tribaldaan conclave with Bhashini was an explicit trust-building event — bringing the community together before data collection began to establish what was being built, why, and on what terms. Accountability for the data quality process rested with Karya's quality management infrastructure and the District Administration as the convening institution.

**Learnings**

- The institution that convenes must have standing in the community whose language is being built. An external organisation cannot substitute for this. It can support and implement; the convening authority must be local and trusted.
- In-house testing at each phase before wider release is non-negotiable. The institution whose name is on the model must put a human lens on it. This cannot be outsourced to the technology partner or a third-party testing team.
- Build a dedicated PMU before the project begins. Cross-actor coordination across community, government, academic, and technology domains under time pressure cannot be a part-time responsibility added to someone's existing role.
- The 70/30 rule applies here as much as in any AI deployment: technology is only 30% of success. The institution's commitment, the champion's persistence, and the quality of coordination determine whether the data collection exercise produces a usable model or a one-time effort that stalls.
- Build strong safeguards against abuse into the institutional design from the start — not as a compliance layer added later. In Astitva, strict monitoring was maintained throughout the data collection phase and irregularities were addressed immediately. This is an institutional accountability function, not a technical one.
- Check whether the financial flexibility mechanisms available in Maharashtra (delegated district-level funds) exist in the target state or geography before designing the funding and approval model. Where they don't exist, a different institutional anchor — state-level ministry, a national programme — may be needed.

**Gaps**

- What happens when the institutional champion transfers mid-project is not addressed. This is a real and common risk in government-led district projects in India.
- What specific resistances were encountered — departmental reluctance, community scepticism, concerns about data use — and how they were overcome is not documented.
- What institutional knowledge needs to be retained after the project ends — who holds understanding of the dataset, the model, the community relationships — is not captured. The risk of knowledge walking out when the PMU disbands is unaddressed.
- How the monitoring and irregularity-response mechanism was structured operationally — what was monitored, by whom, at what frequency, and what constituted an irregularity — is not described.
- Whether higher-level political support (state or national) was needed and obtained at any point is not documented.

---

## D. Ecosystem

**Snapshot**

The actor map for a low-resource language project is more complex than a standard AI deployment. Five named partner organisations worked together in Project Astitva, each with a distinct role:

- **District Administration Nandurbar** — leadership, coordination, funding support, convening authority
- **Karya** — data collection platform, dashboards, leaderboards, task management, quality process
- **IIT Madras and EkStep Foundation** — model development, technical validation
- **Bhashini** — open-source hosting, national platform support
- **State Agriculture Department and POCRA** — service integration, deployment through MahaVISTAAR extension systems

Community contributors — native Dehvali Bhili speakers across agriculture, health, and revenue domains — were the primary content creators. They are not a named organisation but a structured participant group, with defined eligibility, compensation, and accountability.

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
- Knowledge exchange across geographies accelerates the work. India-Africa knowledge transfer on voice AI for low-resource languages is already active — what India built on orchestration, Africa built on offline edge deployment for low-connectivity contexts. A new adopter should seek out what has already been learned elsewhere before starting.

**Gaps**

- How to find or assess a linguistic validator for a language with no academic tradition is not documented. This is a genuine bottleneck with no replication guidance.
- How annotators are recruited, trained, and quality-checked beyond the eligibility criteria is not described. The annotation methodology — what the transcription process looks like, what quality standards apply, how disagreements are resolved — is absent.
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

The initial data collection phase of Astitva was completed in one month — intensive and time-bound, with the booklet explicitly noting the tradeoff: "limited time can increase speed but affect quality." Input targets were met: 25,000 agricultural sentences, 15,000 non-agricultural sentences, 60 hours of spontaneous speech, 6 hours of studio speech, 2 hours of conversational speech — over 60,000 voice samples in total.

The sequenced expansion plan is documented: Dehvali Bhili first, then Mathwadi Bhili, Mavachi, and Pawari; agriculture first, then health, education, and administration. One language, one deployment, prove it, then expand.

The dataset is available on Bhashini as an open repository. Ongoing ownership sits with the tribal department, with the state having taken over from the district via MahaVISTAAR. The work has already informed deployments in Africa, where the open-source orchestration platform is being adopted for local use cases.

**Learnings**

- Set a time-bound target for the initial data collection phase. Open-ended timelines reduce urgency and participation quality. Acknowledge explicitly that limited time increases speed but may affect quality — this trade-off must be actively managed, not assumed away.
- Sequence deliberately: one language, one deployment, prove it, then expand. The Astitva model — Dehvali Bhili into agriculture first, then additional languages and use cases — is a replicable sequencing principle.
- Plan the handover to a permanent institutional owner before the project begins, not after. The tribal department's ongoing ownership in Astitva was a designed outcome, not an improvised one.
- Design for reuse from day one. Open licensing, platform-neutral hosting, and documented methodology must be decided at the start, not retrofitted at the end.

**Gaps**

- How the dataset stays current over time — who is responsible for updates, at what frequency, funded how — is entirely unaddressed. The risk of a static one-time corpus that degrades in relevance is real and undocumented.
- The governance model for the open community language repository is absent — who decides what gets added, what gets corrected, who can use it and on what terms, whether there are restrictions on commercial use.
- The mechanics of the district-to-state transition — what was handed over, to whom, under what terms, with what ongoing support — are not documented.
- What it cost to build the initial phase, and what it costs to maintain and expand annually, is not documented.
- If the language model produces a wrong output in the field — a farmer receives incorrect advisory — what is the path from that error to a fix? This error-correction and accountability pathway is absent.
- The timing of the formal transition from district to state ownership is not documented.

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
- [Karya](../entities/karya.md) — Social enterprise providing the data collection platform, dashboards, and task management
- [EkStep Foundation / IIT Madras](../entities/ekstep-foundation.md) — Model development and technical validation
- [Bhashini](../entities/bhashini.md) — National open-source language platform and hosting infrastructure for the resulting dataset and model
- [State Agriculture Department & POCRA](../entities/maharashtra-agriculture-pocra.md) — Service integration and deployment through extension systems


