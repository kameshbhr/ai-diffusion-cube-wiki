# Navigator — Enabling Voice AI for a Low-Resource Language
**A guide for someone starting at zero**

---

## How to use this

This Navigator is a structured set of questions to help a new adopter think through what enabling voice AI for a low-resource language will require. It is meant to be used alongside the full pathway document, which contains the detailed knowledge behind each question.

Each question is tagged:

- **[Before you start]** — must be answered before the project begins. If you can't answer these, you're not ready.
- **[During the project]** — questions that need active management once the work is underway.
- **[Before you finish]** — must be resolved before the project closes, even if they feel premature early on.

Each question also points to the relevant section of the pathway where the guidance lives.

A human guide using this should start at A and work through to F, but can jump based on what the adopter already knows or has already decided. Not every question will be relevant to every adopter — the guide's job is to identify which ones surface real uncertainty and spend time there.

---

## A. Problem Orientation

**1. What is the specific language you are enabling?** [Before you start]
Not the language family or group — the specific language. And within it, how many dialects exist, how many speakers each has, and which you are prioritising. → *A. Problem Orientation — Snapshot, Learnings*

**2. What does your dialect map look like?** [Before you start]
How did you identify the dialects? What do you know about the differences between them — vocabulary, pronunciation, grammar? Which dialects will your corpus cover? → *A. Problem Orientation — Gaps*

**3. What already exists for this language?** [Before you start]
Any prior recordings, written materials, linguistic work, datasets — formal or informal. Have you checked Bhashini? What did you find? → *A. Problem Orientation — Learnings*

**4. What is the scope of this project?** [Before you start]
Is it building language infrastructure, deploying a use case, or both? What is the output you are committed to delivering? → *Summary*

**5. What is the first use case that will deploy on this language infrastructure once it is built?** [Before you start]
Who is the downstream team? What domains will they need — agriculture, health, administration? Have you spoken to them about what the corpus needs to contain? → *A. Problem Orientation — Learnings*

**6. What interaction model does the downstream use case require — inbound, outbound, or both?** [Before you start]
Has the downstream team confirmed this? What are the implications for the architecture you are designing? → *A. Problem Orientation — Learnings*

---

## B. Architecture

**7. What is your tech stack?** [Before you start]
Which layers have you identified — speech recognition, language model, text to speech, orchestration, telephony? Which layers are you responsible for building, and which will come from partners or existing infrastructure? → *B. Architecture — Snapshot*

**8. What is your approach to vendor selection and management?** [Before you start]
How many vendors are you working with? What is your thinking on vendor dependency? What happens if a vendor underperforms or exits? → *B. Architecture — Learnings*

**9. What type of corpus are you designing?** [Before you start]
What speech types are you collecting — read, spontaneous, conversational, studio? What domains are covered? How did you arrive at this design? → *B. Architecture — Learnings*

**10. What is your recording quality specification?** [Before you start]
At what audio quality will you collect? What is the audio quality of the channel through which the model will be deployed? How did you arrive at these specifications? → *B. Architecture — Learnings*

**11. How are you designing domain coverage in the corpus?** [Before you start]
Which domains are you collecting for? Are domain-specific sentences being collected as distinct tracks or mixed together? Who is contributing sentences for each domain? → *B. Architecture — Snapshot, Learnings*

**12. What are your contributor eligibility criteria?** [Before you start]
Who qualifies to contribute? How will you enforce the criteria? What happens when a contributor's output doesn't meet quality standards? → *B. Architecture — Snapshot*

**13. What does your quality pipeline look like?** [Before you start]
How many stages? Are they sequential or parallel? Who is responsible for each stage? How are disputes resolved? → *B. Architecture — Snapshot*

**14. Where will the dataset and model be hosted?** [Before you start]
Who controls access to it? What are the licensing terms? What happens if the hosting provider changes? → *B. Architecture — Learnings*

**15. How is the data layer separated from the AI layer?** [During the project]
Who owns each data source? Who is accountable for keeping it accurate and updated? What happens when a data source changes? → *B. Architecture — Learnings*

**16. How are you tracking dialect coverage as testing progresses?** [During the project]
Who has tested the model so far? Which dialects are represented in the testing panel? Which dialects have gaps? → *B. Architecture — Learnings*

**17. What is your understanding of your data protection obligations?** [Before you start]
Who is the data fiduciary for the language corpus? What are the consent and withdrawal rights for contributors? What legal guidance have you sought? → *B. Architecture — Gaps*

---

## C. Institution

**18. What is the authority that says "this runs in my name"?** [Before you start]
Which institution is the convening authority? What standing does it have with the community whose language is being built? Why is it the right institution for this? → *C. Institution — Snapshot, Learnings*

**19. What is the reach of your convening authority across line departments?** [Before you start]
Which departments need to participate? Does the convening authority have a direct line to all of them, or will each need to be negotiated with separately? → *C. Institution — Snapshot*

**20. What is your funding and approval structure?** [Before you start]
Where is the money coming from? What approvals are needed at each stage? How long do approvals take? Are there district-level delegated funds available, or does everything require state-level sign-off? → *C. Institution — Learnings*

**21. What is your project management structure?** [Before you start]
Who is running the day-to-day coordination? Is this a dedicated role or added to someone's existing responsibilities? Who does the PMU report to? → *C. Institution — Learnings*

**22. How is the project framed internally and in the community?** [Before you start]
How is it described to participating departments? How is it described to community contributors? What is the motivation for participation beyond formal instruction? → *C. Institution — Snapshot*

**23. What are your monitoring and accountability mechanisms?** [Before you start]
Who monitors the data collection process? What constitutes an irregularity? What happens when one is identified? Who has authority to act? → *C. Institution — Learnings*

**24. What is your continuity plan if the key champion in the institution changes role?** [Before you start]
Who else in the institution carries the knowledge and relationships? What has been documented so it doesn't walk out with one person? → *C. Institution — Gaps*

---

## D. Ecosystem

**25. Who is filling each of the ten actor roles in your ecosystem?** [Before you start]
For each role — convening authority, community speakers, annotators, linguistic validators, data collection platform provider, specialised data partner, model builder, infrastructure provider, neutral orchestrator, PMU — who is it, and is that confirmed? Where are the gaps? → *D. Ecosystem — Snapshot*

**26. Who is your linguistic validator?** [Before you start]
How did you find them? What is their background? How familiar are they with the specific language and its dialects? If you haven't found one yet, what is your plan? → *D. Ecosystem — Snapshot*

**27. Who is playing the neutral orchestrator role?** [Before you start]
Whose job is it to actively map the ecosystem and connect actors who would otherwise not find each other? How are they doing this? → *D. Ecosystem — Learnings*

**28. What is your data partner's experience with underserved communities?** [Before you start]
Have they done this kind of work before — community-based voice data collection with ethical compensation and quality management? What is their track record? → *D. Ecosystem — Learnings*

**29. What is your community contributor participation model?** [Before you start]
How will contributors be recruited? What are they being compensated, and how? How is consent being obtained? What rights do contributors have over the data they create? → *D. Ecosystem — Learnings*

**30. What has already been built elsewhere that you can learn from or reuse?** [Before you start]
Have you looked at what other states or countries have done for low-resource languages? Have you spoken to anyone who has done this before? → *D. Ecosystem — Learnings*

**31. What formal agreements are in place with your partners?** [Before you start]
What instruments exist — MOUs, data sharing agreements, contracts? What do they cover? What is left to informal understanding? → *D. Ecosystem — Gaps*

---

## E. Workforce

**32. What training and onboarding are you providing to community annotators and validators before collection begins?** [Before you start]
What do they need to know and be able to do? How will you verify they are ready? What happens if quality from a contributor is consistently poor? → *E. Workforce — Gaps*

**33. How are you maintaining quality across a large number of contributors working under time pressure?** [During the project]
What signals tell you quality is slipping? Who is responsible for catching and addressing it? What mechanisms — dashboards, real-time review, spot checks — are in place? → *E. Workforce — Gaps*

**34. What will frontline workers in the downstream use case need — and who is planning for that?** [Before you finish]
When the language model is integrated into a use case, frontline workers absorb the change. Is someone responsible for their onboarding? Has that conversation started with the downstream team? → *E. Workforce — Note on fit*

---

## F. Operating Model

**35. What is your timeline for the initial data collection phase — and what is the trade-off you are accepting?** [Before you start]
What is the target? How was it set? What is the risk if you prioritise speed — and what is the risk if the timeline stretches? → *F. Operating Model — Learnings*

**36. Who is the permanent institutional owner after this project closes?** [Before you start]
Which institution will hold the dataset and model? What does ownership mean for them in practice — who updates it, who governs access, who funds ongoing maintenance? Has that institution agreed to this? → *F. Operating Model — Learnings*

**37. What is your sequencing plan — which language first, which use case first?** [Before you start]
What is the logic behind the sequence? What would need to be true before you expand to a second language or a second use case? → *F. Operating Model — Learnings*

**38. What are the open licensing and reuse terms for the dataset and model?** [Before you start]
Who can use it? Under what conditions? Are there restrictions on commercial use? How are these terms enforced? → *F. Operating Model — Learnings*

**39. How will the dataset be kept current after the initial build?** [Before you finish]
Who is responsible for updates? At what frequency? What triggers an update — new vocabulary, new domains, new dialects? How is this funded? → *F. Operating Model — Gaps*

**40. What is the governance model for the open language repository?** [Before you finish]
Who decides what gets added, corrected, or restricted? What is the process for a contributor or community member to raise a concern about the data? → *F. Operating Model — Gaps*

**41. What is the error-correction pathway once the model is live?** [Before you finish]
If the model produces a wrong output in the field, how does that get reported? Who receives it? Who is accountable for fixing it? How long should a fix take? → *F. Operating Model — Gaps*

---

## A note on what this Navigator doesn't cover

These questions are drawn from the knowledge in the Astitva pathway. Where questions point to Gaps in the pathway, the honest answer is that the knowledge doesn't yet exist in documented form. Those gaps are not rhetorical — they are real unknowns that a new adopter will need to resolve through their own experience, legal counsel, or peer connection with others who have done this.

For peer connection: District Administration Nandurbar (via NIC Maharashtra); Karya (karya.ms).
