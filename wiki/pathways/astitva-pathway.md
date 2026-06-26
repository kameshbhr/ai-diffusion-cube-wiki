# Project Astitva — Enabling a Low-Resource Tribal Language for Voice AI

**Deployment:** Project Astitva — Dehvali Bhili Language Enablement for Voice AI
**Contributor:** District Administration Nandurbar; Karya; EkStep Foundation / IIT Madras
**Sector:** Cross-sector (initial deployment: Agriculture via MahaVISTAAR; planned: Health, Education, Administration)
**Geography:** Nandurbar district, Maharashtra, India
**Actor type:** Government (District Administration) + Civil society (Karya, EkStep) + Academic (IIT Madras) + National infrastructure (Bhashini)
**Journey stage:** Pilot → Scaling
**Dimensions covered:** A, B, C, D, E, F
**Horizontal or vertical:** Horizontal (language enablement as a prerequisite to any AI deployment for low-resource language communities)
**Deployment status:** Active — Dehvali Bhili integrated into MahaVISTAAR; expansion to additional languages and use cases underway
**Last updated:** 2026-06-24
**Contact for peer connection:** District Administration Nandurbar (via NIC Maharashtra); Karya (karya.ms)

---

## Summary

Project Astitva is a district-led initiative in Nandurbar, Maharashtra that built a participatory voice data collection and language enablement pipeline for Dehvali Bhili — a low-resource tribal language spoken by over 9 lakh residents — where no usable digital dataset previously existed. Working with community contributors, linguistic experts, and technology partners, the district collected 60,000+ voice samples, processed them through a quality-assured pipeline, and integrated the resulting language model into MahaVISTAAR, Maharashtra's agricultural extension platform, as the first practical deployment. The entire initial phase was completed within one month. This pathway is useful to any adopter facing the challenge of enabling an under-resourced language for AI before any deployment using that language can be built.

---

## A — Problem Orientation

*What you build on.*

**Who were you trying to serve, and what specific problem were you solving for them?**
The immediate users were tribal farming communities in Nandurbar — over 9 lakh residents, 69% of whom belong to Scheduled Tribes, speaking more than 18 languages and dialects including Bhili, Pawari, Kokani, and Mavchi. The problem was structural exclusion: government advisory services, digital platforms, and AI tools were built in dominant languages (Hindi, Marathi) and assumed literacy. Tribal communities were excluded not because services did not exist, but because the services could not reach them in the language they actually speak. Dehvali Bhili was chosen as the first language to enable under Project Astitva. The Voice AI Interview (EkStep Foundation) confirms the broader pattern: "the moment you think of anyone who is beyond the top 5-6 languages, voice becomes a must-have channel for inclusion."

**Who defined the problem — the deployer, the institution, or the user — and how do you know the user agrees?**
The District Administration of Nandurbar defined the problem and led the initiative. The participatory design approach — community members co-creating datasets, language experts validating outputs, and feedback loops incorporating local dialects — was the mechanism through which user agreement was demonstrated rather than assumed. The Astitva booklet documents that "participation was not assumed — it was designed, facilitated, compensated, and respected." Field demonstrations after integration into MahaVISTAAR confirmed the signal: farmers engaged more confidently when information was delivered in Dehvali Bhili, and frontline workers reported smoother communication with reduced need for repeated explanation and informal translation.

**How did you define your success metrics — are they usage-based or outcome-based?**
The initial phase set supply-side targets: 25,000 agricultural sentences, 15,000 non-agricultural sentences, 60 hours of spontaneous speech data, 6 hours of studio speech data, and 2 hours of conversational speech data — all in Dehvali Bhili. These were input metrics for the language model, not outcome metrics for users. The early field response after integration into MahaVISTAAR provided qualitative outcome signals: improved farmer engagement, greater clarity in advisory delivery, and reduced translation burden for extension workers. Formal outcome metrics beyond these field observations are not documented.

**Did you discover something in the field that you hadn't anticipated when defining the problem or designing the solution?**
Yes — two field discoveries are documented. First, the initial data collection used only read speech (community members reading written sentences aloud). The resulting data did not reflect how people actually converse. Conversational speech — natural, unprompted — had to be added as a separate collection track. The Voice AI Interview is direct: "the way we read from a text is very different from the way we converse with each other. This input requires conversational audio — an important learning that was brought in later and is crucial for future pathway adopters." Second, audio quality mismatch: data collection was done at 16 kHz (smartphone quality) but telephony lines operate at 8 kHz. The model underperformed on live calls until low-quality 8 kHz audio was included in the training data.

**Was there data already available to start with, or did you have to build or collect it first?**
No usable data existed. Dehvali Bhili is not taught in schools to a wide population, has limited written text, and had no digital audio recordings or datasets. The Voice AI Interview describes this starting condition precisely: "you don't have written text of quality, you don't have recordings, you don't have any datasets available — you are in fact starting a journey of zero to one." Project Astitva built the entire dataset from scratch, which was the primary purpose of the initiative.

**Why did this problem need AI — what would a non-AI solution have missed?**
A non-AI solution (human agents speaking Dehvali Bhili) cannot scale to serve hundreds of thousands of speakers across an entire district, cannot operate 24/7, and cannot be replicated across 18+ dialects without unsustainable staffing. The Voice AI Interview documents the structural limits of human-agent alternatives: limited language coverage, fixed hours, high staff churn. The deeper case is about what language enablement unlocks: "bringing a new language also means you are opening the doors for all users who speak that language from being excluded from services, applications, and views — not just with AI, but anything AI can connect."

**What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?**
Language was the primary constraint: Dehvali Bhili speakers had no digital representation of their language. Literacy was a secondary constraint — written interfaces were inaccessible to a significant proportion of users. Connectivity in Nandurbar was sufficient for telephony-based voice interaction; the deployment did not face the offline-only constraint documented for some Africa-based deployments. The combination of language and literacy constraints drove the voice-first architecture: voice is the only channel that does not require literacy.

**Did users interact through voice, an app, or something else — and what drove that choice?**
Voice via telephony (standard phone calls) was the interaction channel for the MahaVISTAAR deployment into which this language data feeds. Data collection from community contributors used a community-driven mobile app (provided by Karya), which captured audio recordings. The choice of voice as the end-user interaction channel was driven by literacy constraints and the absence of a suitable app-based alternative for this population.

**Did you design the system to wait for users to come to it, or did it reach out to them too?**
The initial deployment was inbound — farmers call MahaVISTAAR. Outbound use cases (the system calling farmers with advisory) were identified as a future expansion but were not part of the initial language enablement scope. The Voice AI Interview flags this as a lesson from MahaVISTAAR's broader deployment: the outbound architecture was not planned for at the start, requiring a rearchitecting when the need emerged. A next adopter enabling a language for voice AI should confirm with the downstream deployment team whether outbound calling is in scope, and ensure the architecture is built to support it from the start.

---

## B — Architecture

*What you build with.*

**Did you need data sources that were controlled by other departments or organisations — if so, what did it actually take to get access?**
The data required for language enablement was speech data — created fresh by community contributors, not extracted from existing departmental systems. Contributors spanned domains: health workers contributed sentences in health and social service contexts; revenue staff contributed administrative domain sentences; community members contributed agriculture and daily life sentences. Access to these contributors required the District Collector's convening authority to mobilise multiple line departments simultaneously. The specific administrative steps to secure departmental participation are not documented.

**Did you bring data together into one place or connect to it where it lived — and why?**
All language data was collected centrally through Karya's platform — recordings, transcriptions, and quality validations were managed in one place to enable the multi-layer quality process (contributors → checkers → validators → linguistic experts) to function in real time. This is distinct from the downstream deployment architecture for MahaVISTAAR, which uses an API-separated federated data model; for language model building, centralised collection was the appropriate choice.

**For each major component of your system — did you build it, buy it, or reuse something that existed? Would you make the same choices again?**
The data collection platform was provided by Karya (digital interface, dashboards, leaderboards, task management) — existing infrastructure reused, not built. Model development and technical validation was provided by IIT Madras and EkStep Foundation. Hosting and open-source platform support was provided by Bhashini (national infrastructure). The downstream deployment into MahaVISTAAR used existing MahaVISTAAR infrastructure. The Voice AI Interview notes that building models in-house only makes sense for organisations already in the business of model building or with a specific gap that existing models cannot fill; for this deployment, the right choice was to leverage existing partners and platforms. Whether the same partnerships would be chosen again is not documented.

**Did any data source or system integration turn out to be harder than expected?**
The audio quality mismatch (16 kHz collection vs 8 kHz telephony) was not anticipated and required corrective action: adding low-quality audio data to the training set. The absence of conversational speech data in the initial collection also required a supplementary collection effort. Both were discovered through the deployment into MahaVISTAAR rather than in the collection phase itself. The Voice AI Interview also notes that dialect representation is a common gap: "just because I have access to 10 people who will test the bot, I've used that and given a green signal without having enough representation from all the dialects — which dialect has how much gap often gets neglected."

**Did vendor lock-in become a real constraint — what were your options and how did you resolve it?**
For the language enablement pipeline itself, lock-in was mitigated by using open platforms: Karya for data collection, Bhashini for hosting and open-source model distribution. The Voice AI Interview documents the broader lesson on vendor lock-in in voice AI deployments: single-vendor dependency was the most common failure mode in early pilots. The Astitva design avoided this by placing the resulting language repository on Bhashini as an open-access DPG, ensuring no single vendor controls access to the language assets created.

**What was your design policy for handling peak load?**
Not documented for the language data collection pipeline. For the downstream MahaVISTAAR deployment, this is addressed in the MahaVISTAAR pathway.

**Did the AI produce wrong or harmful outputs that reached users — how did you detect it and what did you put in place to prevent recurrence?**
Not documented for the language enablement phase. For the downstream deployment into MahaVISTAAR, quality checks on the language model's performance were embedded in the integration pipeline. Field demonstrations before full rollout were used to validate that queries were received and understood with clarity. The Voice AI Interview documents a structured multi-step testing protocol for voice deployments generally, but specific error-handling mechanisms for the Dehvali Bhili language model are not described.

**Did data residency, sovereignty, or government policy on technology vendors constrain your architecture — did that come up early or late?**
Data sovereignty was addressed by design: the community-collected language data was placed in Bhashini, a national government-backed open-source repository, rather than in any proprietary vendor system. This ensured the data remained an open community and national asset rather than being held by a technology partner. The decision appears to have been made early, not imposed late.

**If you used voice — did you face any problems such as latency, pronunciation, turn-taking and timing? What did you do to address it?**
The Voice AI Interview documents two technical lessons directly relevant to Dehvali Bhili enablement. First, the read speech vs conversational speech gap: read speech data produces models that perform poorly in natural conversation; spontaneous speech data must be collected separately. Project Astitva included 60 hours of spontaneous speech data for this reason. Second, the 8 kHz telephony vs 16 kHz collection mismatch: the model must be trained on data at the audio quality it will encounter in production. Both lessons are now embedded in the data collection design. Problems encountered in the downstream voice AI deployment (latency, hold messages, introduction length) are documented in the MahaVISTAAR pathway.

**How frequently did the underlying data change, and how did you keep the AI current with those changes?**
Language data does not change frequently, but domain-specific vocabulary can expand. The Astitva booklet documents planned ongoing updates and domain-specific expansions (health, education, administration uses cases beyond the initial agriculture focus). The mechanism for keeping the model current with new vocabulary or domain expansions is expansion of the training data through additional collection cycles. The open repository on Bhashini enables community-level additions over time.

**Did you hit any infrastructure constraint at scale that you didn't anticipate, and how did you resolve it?**
Not documented for the language enablement pipeline. The one-month timeline created speed pressure that the booklet notes could affect quality; "intensive coordination and sustained motivation were essential for meeting targets." Whether any infrastructure bottleneck contributed to quality pressure is not documented.

### Additional Insights

The Voice AI Interview documents a critical point for any future language enablement effort: a neutral orchestrator role is essential. "IIT Madras did not know that such an effort was happening — there was no way for them to connect and provide their input. There is an important role for a neutral orchestrator that can bring all the relevant parties together." In Project Astitva, the District Administration played this orchestrator role. Without a single entity willing and able to convene the full range of actors, key technical partners may simply not be in the room.

---

## C — Institution

*Who owns solving of the problem.*

**Was this deployment treated as a one-time project or as a long-term transformation initiative — did that framing create problems?**
The framing was explicitly long-term, even though the initial data collection phase was structured as a one-month intensive. The Astitva booklet documents planned expansion to three additional languages (Mathwadi Bhili, Mavachi, Pawari), additional domain use cases (health, education, administration), and transition of ownership to the tribal department with state-level support from MahaVISTAAR. The community language repository is described as promoting "sustained use" rather than a one-time release. The time-bound initial phase created speed but the booklet explicitly notes this tradeoff: "limited time can increase speed but affect quality."

**How did you get the deployment approved and funded?**
In Maharashtra, delegated financial powers and district-level funds provided the District Collector flexibility to allocate resources without requiring state-level approval for each step. The booklet notes that Maharashtra's district-level funding structures are a specific enabler: "innovative district level funds provide the flexibility to departments." The specific budget and approval process are not documented.

**If the one or two people driving this deployment had moved to different roles mid-way, what would have happened?**
The deployment was structured around the District Collector as the convening authority. The booklet acknowledges this directly in framing "institutional pride" as a motivator — but institutional pride is person-adjacent. The Voice AI Interview generalises from MahaVISTAAR: "the biggest factor of success was having an institution — a convening authority — that was passionate about the use case and held the ground no matter how long it took." The sustainability plan (tribal department ownership, state transition, Bhashini hosting) is the structural response to this risk, but the initial phase depended heavily on individual leadership.

**Which departments had to cooperate for this to work — where did that cooperation break down or get difficult, and how was it resolved?**
Education, IT, Agriculture, and Tribal Welfare departments were identified as needing to converge. Health workers and revenue staff contributed domain-specific sentence collection. The District Collector heading all line departments was the structural mechanism that made this coordination possible without negotiating independently with each department. Specific friction points and how they were resolved are not documented.

**Did procurement rules become a barrier — and if so how did you navigate through?**
Not documented.

**Were there decisions that needed political support from above — did you have it when you needed it?**
The District Collector's direct involvement provided the political cover needed for cross-departmental coordination and for mobilising the community at the scale required. Whether higher-level (state or national) political support was needed and obtained at any point is not documented. The transition to state-level ownership via MahaVISTAAR implies state-level endorsement was secured at the integration stage.

**When something went wrong, who was accountable — and was that clear from the start?**
The booklet documents "strict monitoring and accountability" and "irregularities addressed immediately" as safeguards during data collection. Accountability for the data quality process rested with Karya's quality management infrastructure (validators, subject experts, checkers) and the District Administration as the convening institution. Whether accountability for the downstream model quality was formally assigned is not documented.

**Which institution did the AI speak on behalf of — and did that institution have credibility with your end users? If not, how did you address it?**
The voice AI ultimately speaks on behalf of MahaVISTAAR, which is backed by the Maharashtra state government and the State Agriculture Department. For Dehvali Bhili speakers who have historically been excluded from government services, the credibility of government backing was enhanced by the participatory nature of the data collection — community members were contributors and validators, not just recipients. The "Tribaldaan conclave with Bhashini" documented in the booklet was an explicit trust-building event.

---

## D — Ecosystem

*Who executes.*

**How many organisations had to work together for this to function?**
Five named partner organisations, each with distinct roles documented in the Astitva booklet:
- District Administration Nandurbar — leadership, coordination, funding support
- Karya — digital interface, dashboards, leaderboards, task management for data collection
- IIT Madras & EkStep Foundation — model development, technical validation
- Bhashini — open-source hosting, national platform support
- State Agriculture Department & POCRA — service integration, deployment through extension systems

Community contributors (native Dehvali Bhili speakers across agriculture, health, and revenue domains) were the primary content creators, not a named organisation but a structured participant group. The Voice AI Interview adds a general principle: "you need annotators, linguistic experts, a data collection platform, a model builder, a hosting provider, a PMU unit, and advisors — all of these actors are needed to bring a language into production."

**Who was specifically responsible for keeping all partners aligned — was that role clearly assigned and resourced?**
The District Collector served as the convening authority and primary coordinator. Karya managed the operational data collection process. The Voice AI Interview identifies the neutral orchestrator role as essential and commonly missing: "there is an important role of a neutral orchestrator that can bring all the relevant parties together." In Astitva, the District Administration filled this role by virtue of its authority over line departments, but whether a dedicated coordination resource was assigned is not documented.

**Were there partners whose commitment weakened over time — what drove that and how did you handle it?**
Not documented. The one-month timeframe of the initial phase compressed the window during which commitment could erode. The use of digital dashboards, leaderboards, and real-time tracking (documented in the quality assurance process) also functioned as visible commitment mechanisms. The booklet notes that "intensive coordination and sustained motivation were essential for meeting targets."

**Where did partners have conflicting priorities or mandates — how were those conflicts resolved?**
Not documented.

### Additional Insights

The ecosystem diagram in the Astitva booklet makes explicit something that is often left implicit: community contributors are not just users or beneficiaries — they are active participants in the production chain, responsible for language data creation, validation, and local ownership. This has a practical implication: their participation must be designed, compensated, and governed, not assumed. "Participation was not assumed — it was designed, facilitated, compensated, and respected."

---

## E — Workforce

*Who absorbs AI.*

**Were there people — field workers, extension officers, call centre staff — whose job changed because of this deployment?**
During the data collection phase, health workers and revenue staff contributed domain-specific sentences — a temporary addition to their work, not a job change. After integration into MahaVISTAAR, agricultural extension workers and frontline workers (ASHA/ANM/AWW) were the primary workforce who absorbed the change. Their experience was documented as positive: the availability of Dehvali Bhili support "reduced the need for repeated explanations and informal translation" during field visits and advisory sessions.

**When the AI gave an answer or recommendation to a user, what was the last-mile human expected to do with it — and were they actually capable of doing that?**
For agricultural extension use cases, frontline workers carried the AI's advisory to communities during field visits — the advisory was in Dehvali Bhili and therefore accessible without translation. For citizen-facing voice AI use cases, there is no last-mile human intermediary; the voice bot is the last mile. What specific capabilities extension workers needed to explain or contextualise AI-generated advisory is not documented.

**How and when were they brought in, and what did they need to learn?**
Health workers and revenue staff were mobilised during the initial data collection phase — their participation was structured and compensated. Extension workers using the MahaVISTAAR system with Dehvali Bhili capability were presumably onboarded as part of the broader MahaVISTAAR deployment rather than as a separate Astitva-specific onboarding. Details are not documented.

**Did you face resistance from staff — what were the reasons and what worked?**
Not documented for Astitva specifically. The booklet frames the initiative as a source of "institutional pride" and community identity — "when initiatives are driven by local leadership, they create a sense of confidence that ripples across all stakeholders." Whether this framing actively neutralised resistance or simply reflected the absence of it is not documented.

**Did frontline staff become dependent on the system in a way that reduced their own capability — how did you know?**
Not documented.

**How did problems or insights from the field reach the people improving the system — was there a structured feedback loop?**
The feedback loop from field deployment to language model improvement is described at the system level: feedback loops "incorporate local knowledge and dialects, allowing AI systems to continuously improve and remain relevant." The mechanism for this — who collects feedback, how it reaches model developers, how corrections are validated — is not described in operational terms. The ongoing updates and domain-specific expansions mentioned in the booklet imply an iterative improvement process, but the feedback pathway is not documented.

---

## F — Operating Model

*What makes it last.*

**Who took ownership of steady state operations after the pilot — how was that transition structured and when did it happen?**
The Astitva booklet documents a clear multi-level handover: ongoing ownership by the tribal department, transition of district work to state level via MahaVISTAAR, and the language repository placed on Bhashini for open access and nationwide adaptability. This was designed as a handover plan, not improvised. The institutional support from MahaVISTAAR provided the bridge between the district-level initiative and the state-level operational home. The timing of the formal transition is not documented.

**What did it cost to build, and what does it cost to run annually — how did those compare to your original estimates? Which cost components surprised you most?**
Not documented in either source. The booklet notes that the initial phase was "time-bound but intensive" and that district-level funds provided flexibility, but specific figures are not given.

**Were there compliance, audit, or regulatory requirements that shaped how you ran operations?**
The data collection process included contributor eligibility criteria (proficiency in Dehvali Bhili, literacy and typing skills, local ownership in language standardisation) and a parallel quality validation track. The Astitva booklet references "strong safeguards against abuse" and "strict monitoring and accountability." Whether specific regulatory or data protection requirements applied to community voice data collection is not documented.

**How long did the deployment actually take versus what you planned — where did time get lost?**
The initial data collection phase was completed within one month — described as a deliberately time-constrained target. The booklet explicitly notes the tradeoff: "limited time can increase speed but affect quality." Whether the one-month target was met exactly or required adjustment is not documented. The time from language enablement to integration into MahaVISTAAR is not documented.

**Was there a point where the whole thing nearly stalled — and what got it through?**
Not documented. The one-month timeframe and the District Collector's direct involvement appear to have maintained momentum through the initial phase. The booklet notes that "intensive coordination and sustained motivation were essential" — implying motivation was a real variable that required active management, not a given.

**What did you measure to know the solution was working — and what did the numbers actually show?**
Input metrics for the data collection phase were met: 25,000 agricultural sentences, 15,000 non-agricultural sentences, 60 hours spontaneous speech, 6 hours studio speech, 2 hours conversational speech — over 60,000 voice samples in total. Early field outcome signals after integration into MahaVISTAAR were positive: farmers engaged more confidently, advisory queries were received with greater clarity, and extension workers reported smoother communication. Formal outcome metrics (usage rates, comprehension scores, advisory uptake) are not documented.

**Did you do a big launch or sequence through small pilots — and looking back was that the right call?**
The Dehvali Bhili language was enabled first, as a scoped initial effort within Project Astitva's broader vision across 18+ tribal languages. Integration into MahaVISTAAR was the first deployment. Expansion to three additional languages (Mathwadi Bhili, Mavachi, Pawari) and additional use cases (ASHA/ANM/AWW health bot, Education, Administration) is documented as the next phase. This sequenced approach — one language, one deployment, then expand — is consistent with the broader lesson from the Voice AI Interview: start with what is manageable, prove it, then scale.

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
## Gaps — Information Not in the Source Documents

1. What specific change in a farmer's life would tell you, at twelve months, that this worked — not that the system was used, but that it made a difference?
2. Who owns the Dehvali Bhili dataset? Under what terms was it published to Bhashini — are there restrictions on commercial use? Does the community have any mechanism to withdraw or restrict it?
3. How was Astitva funded? What did it cost? Who bears the ongoing cost of maintaining the language capability in MahaVISTAAR?
4. Before data collection started, what formal agreements existed between the District Administration and external partners? Were there MOUs or data sharing agreements, or was it informal?
5. Who is responsible for the Dehvali Bhili capability in MahaVISTAAR today when it degrades or needs updating?
6. If a farmer receives wrong information from the system, what is the path from that error to a fix?
7. Were there any legal or policy constraints — DPDP, tribal data rights, procurement rules — that you had to comply with as part of the voice data collection?

## Related Pathways

- [MahaVISTAAR — Pathway](../pathways/mahavistaar.md) — The agricultural AI advisory deployment for which the Dehvali Bhili language model built under Project Astitva was the first practical use case

## Related Entities

- [District Administration Nandurbar](../entities/nandurbar-district-administration.md) — Convening authority and lead institution for Project Astitva
- [Karya](../entities/karya.md) — Social enterprise providing the data collection platform, dashboards, and task management
- [EkStep Foundation / IIT Madras](../entities/ekstep-foundation.md) — Model development and technical validation
- [Bhashini](../entities/bhashini.md) — National open-source language platform and hosting infrastructure for the resulting dataset and model
- [State Agriculture Department & POCRA](../entities/maharashtra-agriculture-pocra.md) — Service integration and deployment through extension systems


