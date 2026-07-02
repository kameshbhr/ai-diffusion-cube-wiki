# Voice AI for Inclusion — Horizontal Pathway

**Deployment:** Voice AI for Inclusion
**Contributor:** EkStep Foundation
**Sector:** Cross-sector
**Geography:** India (with India-Africa reference)
**Actor type:** Government / Civil society / Enterprise
**Journey stage:** Pilot to Scaling
**Dimensions covered:** A, B, C, E, F
**Horizontal or vertical:** Horizontal
**Source deployments:** MahaVISTAAR, Bharat Vistaar, Amul/Sarlaben, Jal Jeevan Mission Assam, Bhili low-resource language effort, Lend A Hand, India–Africa exchange with Crane AI Labs
**Last updated:** 2026-07-03
**Contact for peer connection:** EkStep Foundation

---

## Summary

This pathway synthesises practitioner experience across seven voice AI deployments in India and Africa. It is written for the next adopter — not as a record of what was done, but as a transfer of what was learned and what it cost to learn it. 

---

## What This Pathway Is Trying to Prevent

Every deployment in this pathway made avoidable mistakes. Not because the teams were careless. Because the knowledge did not exist in a form they could use before they needed it.

Some started with the technology and worked backwards to the user. Some discovered too late that their architecture gave them no control over the components that mattered most. Some built in one language and then found — after launch — that the helpline was receiving calls in four others. Some tested with their vendors and not with their institutions, and then watched officials disown the bot the first time it gave a wrong answer. Some found out what the implementation tax was only after they had already paid it.

The implementation tax is the name for the hidden work that sits between a voice AI demo and a reliable service channel: use-case clarity, architecture decisions, language readiness, institutional testing, safety design, data governance, and the operating model that sustains it after launch. It is not a small amount of work. It is often larger than the technical work. And it is almost always underestimated.

The core lesson, before anything else:

> Voice AI should not be treated as a bot-building exercise. A voice agent backed by a government department, social sector organization, or enterprise is experienced by the user as the institution itself. If the bot gives a wrong answer, stays silent, misunderstands a dialect, or mishandles a sensitive question, the failure is not seen as a model failure. It is seen as an institutional failure.

---

## Phase 1 — Before You Start: The User, the Problem, and the Channel

### Define the excluded user precisely — before anything else

The deployments that worked started with a precise description of a person who was being failed by existing service channels. The deployments that struggled started with a technology they wanted to try.

Voice AI is most valuable when it solves an access problem — for users excluded by literacy, language, device access, trust, or connectivity. Voice matters because it reaches users in their own language through a medium they already use. But voice is not always enough on its own, and it is not always the right channel.

Several deployments romanticized voice. They discovered later that some users needed to send images, some preferred text in noisy environments, and some needed a human escalation route the bot could not provide.

**Not:** farmers. **But:** women farmers in remote districts who rely on small trust circles and cannot easily visit an agriculture office.

**Not:** youth. **But:** interns across dispersed locations from whom fortnightly feedback is needed, but where two human callers cannot keep up with the volume or frequency.

**Not:** citizens. **But:** rural households receiving piped water where the government needs to know whether water is actually arriving daily, on time, and in usable quality.

The sharper the user and problem, the easier it becomes to decide the channel, model, data, workflow, language, and testing process. User definition is not a preliminary step. It is the decision that makes all subsequent decisions possible.

### Compare voice honestly against what you do today

Many organizations already use human callers for outreach, feedback, counseling, or reminders. Voice AI should be compared honestly against that process. Humans understand nuance, build trust, improvise, and handle ambiguity. But human-only calling is constrained by scale, language range, working hours, turnover, and cost.

The Lend A Hand example shows this constraint directly. The organization needed to collect regular feedback from thousands of interns. Two human callers could not do it at the frequency required. Expanding the human team would have required hiring, training, managers, and infrastructure. Voice AI extended the reach without replacing the human judgment required for complex cases.

The right design is almost always a combination. Voice AI for repeated, structured, scalable interactions. Humans for sensitive, complex, ambiguous, or high-risk cases. If you frame voice AI as human replacement, you will design the wrong system and lose institutional trust quickly.

### On trust: the institution behind the voice is part of the product

A market study in Maharashtra surfaced something important. Many women farmers were doing the actual farming while land titles remained in their husbands' names. These women often had smaller advice networks — less access to agriculture offices, less presence on digital channels. A government-backed voice advisory in their own language changed the trust equation. Users do not trust a voice system because it is AI. They trust it because of who stands behind it.

**For GOVERNMENT:** The intended beneficiaries of a government service are often the least served by conventional digital channels. Starting with the excluded user is not just a design principle — it is the justification for the channel itself.

**For TECHNOLOGIST:** Treat user definition as a prerequisite to architecture selection. The user profile determines language requirements, latency tolerance, data complexity, and safety design. You cannot pick the right stack without it.

**For SOCIAL SECTOR / ENTERPRISE:** Frame voice AI as capacity extension, with clear rules for when humans must remain in the loop. If your organization already has trusted relationships with beneficiaries or customers, voice AI should deepen that trust — not substitute for it.

**What this means for the next adopter:** Do not begin with 'we want to use voice AI.' Begin with 'which users are we failing to reach, and what would they trust enough to use?' If you cannot answer that question precisely, you are not ready to choose a channel.

---

## Phase 2 — Getting the Architecture Right

### The basic architecture

For a telephony-led use case, five layers connect in sequence: telephony enables the phone interaction; ASR converts speech to text; LLM interprets the query and generates a response; TTS converts that response back to speech; and orchestration ties all of it together with data sources, moderation, and analytics. In offline or edge deployments — as in the India–Africa exchange with Crane AI Labs, where some areas have no reliable internet — the telephony layer may not be needed and the ASR–LLM–TTS pipeline runs locally on a device.

### Start bundled. Plan to unbundle.

If you are starting from zero with limited technical capacity, begin with a bundled full-stack provider. Once the use case is proven, the architecture recommendation changes — begin to unbundle, selecting telephony, ASR, LLM, TTS, orchestration, hosting, moderation, and analytics layers separately.

The mistake is not starting bundled. The mistake is staying bundled by accident — never making a deliberate decision to unbundle, and finding yourself dependent on a single vendor's pricing, roadmap, and limitations at a point when the service has real users and real stakes.

### Avoid vendor lock-in by testing more than one provider

One of the strongest lessons across these deployments: shortlist multiple vendors and test them in parallel during the pilot wherever feasible. This allows real comparison under similar conditions, shows which vendor adapts fastest to feedback, creates competitive pressure on cost and quality, and reduces the risk of being stuck mid-way.

### Open orchestration as shared infrastructure

The gap that kept emerging across deployments was not the absence of language models — it was the absence of an orchestration layer that could connect them into a deployable, maintainable system. This is what led to Voiceera: an open-source orchestration platform designed to work with open-source Indic voice models, connect with telephony partners through WebSocket APIs, and support deployment through infrastructure such as Bhashini.

Open orchestration matters because it can be model-agnostic, language-agnostic, telephony-provider-agnostic, and reusable across sectors and organizations. Ecosystems need roads, not just cars.

WebSocket APIs were found more practical for Indian telephony conditions than WebRTC. Match infrastructure choices to local network realities — not to external best practice alone.

**For GOVERNMENT:** For public deployments, unbundling is eventually necessary. Design the pilot so that unbundling is possible later, even if you start bundled.

**For TECHNOLOGIST:** Speech-to-speech models may sound natural and reduce latency, but they were not the default choice in these deployments — they were newer, less proven, harder to configure, and more expensive. Controllability, safety, and deployment maturity matter more than demo quality.

**For SOCIAL SECTOR / ENTERPRISE:** Consider whether your use case will eventually need outbound calling as well as inbound. If this is likely, include it in early architecture and procurement design.

**What this means for the next adopter:** Use a bundled stack to learn fast, but design the pilot so that you can unbundle later without rebuilding everything. Do not let architecture decisions made in the pilot become permanent constraints at scale.

---

## Phase 3 — Making It Work for Real Users: Models, Language, and Data

### How to select a model

Five questions, in this order:
1. Does the model actually support the target language in conversation — not nominally, but conversationally?
2. Is it fast enough for the channel? On a phone call, the user expects a response within one or two seconds.
3. Has it been used in a sector like yours?
4. Does it give you enough control for the long term?
5. What will it cost at scale — including Indic language tokenization, agentic tool calls, and long conversations?

### Use metrics to reject; use users to select

Technical metrics — word error rate, latency, noise cancellation — are good rejection criteria. But they cannot show whether the voice agent is acceptable to real users. A model can perform well in the lab and still fail on the ground. One deployment passed technical evaluation and then struggled with a specific district's dialect that had not been represented in the test group.

Use a two-step process: lab metrics to shortlist or reject, real user and institutional testing to decide what is good enough. Do not let a vendor report become the final proof of readiness.

### Low-resource languages require ecosystem-building, not just data collection

For low-resource languages like Bhili, the starting point is close to zero — no large speech dataset, no widely available ASR model, no TTS model, limited digital text. The Bhili effort showed that the work requires a convening authority, native speakers, annotators, linguistic experts, model builders, hosting infrastructure, a real-world application, and a neutral orchestrator.

Two data lessons from this experience are critical everywhere, not just in low-resource contexts:
- Read speech is not conversational speech
- Studio-quality audio is not telephony-quality audio

If the model will be used over a phone line, it must be trained or tested on phone-line audio conditions.

### Keep data with accountable owners

The AI layer should not become the owner of the data. It should consume data from accountable sources through standardized APIs, while accountability stays with the data custodian. For an agriculture advisory system, that means state agriculture university advisories, weather data, mandi prices, and pesticide information each have an owner responsible for accuracy and updates.

Not every voice AI deployment needs a large dataset. Jal Jeevan Mission Assam needed phone numbers and five questions. MahaVISTAAR needed multiple live, governed data sources. The minimum viable data requirement comes from the use case — not from generic assumptions about what AI deployment requires.

**For GOVERNMENT:** Data ownership must be explicit before deployment. Each data source the voice agent draws on should have a named departmental owner responsible for accuracy and updates.

**For TECHNOLOGIST:** Unless existing models clearly fail the use case and the institution has the capacity to build and maintain a model, start by adapting available models.

**For SOCIAL SECTOR / ENTERPRISE:** Identify what data the bot needs to answer its core questions, who owns it, and how often it changes. Build from there.

**What this means for the next adopter:** Model selection should begin with the user's language and the channel's latency needs. Keep data with accountable owners and expose it through APIs. For low-resource languages, plan the full ecosystem — community, linguistics, data, infrastructure, application, and orchestration.

---

## Phase 4 — Making It Safe and Governable

### Institutional ownership must be established before users arrive

Before launch, the institution should be able to answer: who owns this channel; who approves what the agent can say; who decides what it must not say; who reviews failures; who updates the knowledge base; who handles complaints; and who is accountable when the bot gives a wrong answer.

In more than one deployment, these questions were deferred to after launch. The result was a technically functional system that officials would not stand behind — because they had never been asked to stand behind it before users arrived.

### Design for refusal, not just response

Voice agents will not only receive intended questions. Users may ask out-of-scope questions, complain about officials or policies, seek emotional support, try inappropriate conversations — especially if the bot uses a female voice — or attempt to jailbreak the system.

Before public launch, build a safety and stress-test bank covering:
- In-scope questions
- Out-of-scope questions
- Sensitive questions and distress scenarios
- Abuse or harassment
- Romantic or inappropriate prompts
- Complaints about officials or policies
- Jailbreak attempts
- Questions requiring human escalation
- Questions where the bot should politely decline

The goal is not only to make the bot answer well. The goal is to make it refuse well.

### Institutional testing is not optional

Testing should move through stages: builder and project team; a small institutional group; a wider institutional group across geographies, accents, and scenarios; and then a limited user rollout. In MahaVISTAAR, the rollout moved to citizens only after internal testing, beginning with a limited district-level rollout before wider expansion.

Fully outsourcing testing to a vendor is risky because the vendor is not the one whose public credibility is on the line. Do not outsource trust.

**For GOVERNMENT:** The institution must be willing to stand behind the voice agent. Institutional owners — not just the technical team — must test it, approve it, and be willing to take accountability for it before it speaks to the public.

**For TECHNOLOGIST:** Build moderation into the architecture and prompt design from the start. Safety design must include stress-testing across sensitive, out-of-scope, and adversarial scenarios before any public rollout.

**For SOCIAL SECTOR / ENTERPRISE:** For deployments serving vulnerable populations — women in informal work, migrant laborers, first-generation digital users — safety design must include consideration of distress scenarios and escalation paths to human support.

**What this means for the next adopter:** If the user will hear the bot as your institution speaking, your institution must design, test, and govern it as its own voice. Ownership questions are design questions — they cannot be answered after launch.

---

## Phase 5 — The Experience, the Cost, and Sustaining It After Launch

### Small experience choices that decide whether the call feels alive or broken

**Dead silence.** In MahaVISTAAR, some backend responses took a few seconds to return. On a phone line, three or four seconds of silence feels like failure. The fix was a hold message: 'Please wait while I fetch that information.'

**Long introductions.** The opening message must identify the agent, explain what it can do, and capture consent. Keep introductions under 30 seconds.

**Unnecessary follow-up nudging.** LLMs often end with 'Would you like to know more?' In voice, this becomes repetitive and increases token use. A lighter prompt — 'Is there anything else I can help you with?' — works better.

**Question design.** Sometimes the way to improve accuracy is not to improve the model — it is to ask a simpler question. For feedback use cases, a yes/no question may work better than an open-ended prompt.

**Multilingual expansion as an afterthought.** Several deployments began with one language and discovered after launch that the helpline was receiving calls in languages it could not serve. Multilingual needs should be anticipated early. Retrofitting is significantly harder than designing for it.

### Cost is shaped by architecture, not only by negotiation

Voice AI costs have been falling, but cost still needs to be designed carefully. Premium TTS voices cost more. Proprietary LLMs can be expensive. Indic language interactions may consume more tokens than equivalent English interactions. Agentic workflows with multiple tool calls increase token usage.

Track: cost per minute, cost per completed interaction, average conversation length, token use by language, TTS cost, and cost of failed or abandoned calls.

### The work does not end at launch

The system must be monitored for failed calls, misunderstood queries, user drop-offs, unsafe responses, latency issues, cost increases, language gaps, and backend data errors. Someone must own continuous improvement. If no one does, the system degrades — and the degradation is often invisible until it has already damaged institutional trust.

### Two phases: validate first, then scale

**Phase 1 — Validate:** Prove that voice is the right channel for a specific user, problem, and institutional context. Success means: users can complete the intended interaction; the institution trusts the agent enough to continue; the pilot reveals what must be fixed.

**Phase 2 — Scale:** Move from a useful pilot to a controlled, scalable, and governable service channel. Decide which layers to unbundle. Compare vendors. Separate data from the AI layer through APIs. Plan multilingual expansion. Success means: the institution can change vendors, models, languages, or data sources without rebuilding everything; costs are visible; quality is monitored; safety is governed.

**For GOVERNMENT:** Scale readiness means control. If you cannot change vendors, update data, monitor failures, or govern safety, you are not ready to scale.

**For TECHNOLOGIST:** Build cost visibility into the operating model from day one. Cost is shaped by TTS quality, model choice, language, call design, and stack structure — not only by what you negotiate with vendors.

**For SOCIAL SECTOR / ENTERPRISE:** The deployments that succeed are not the ones that avoid all failure. They are the ones that create a learning loop around failure.

**What this means for the next adopter:** Voice AI becomes durable when the hidden work is named, assigned, resourced, and governed. The next decision is not whether voice AI matters. It is whether the institution is willing to do that work.

---

## The Five Phases, Compressed

- **Before you start:** Identify the excluded user precisely; compare voice honestly against what you do today; treat the institution behind the voice as part of the product.
- **Architecture:** Start bundled to learn fast; plan to unbundle for control; test multiple vendors; invest in open orchestration where long-term sovereignty matters.
- **Models, language, data:** Select by language, latency, sector, control, and cost; use metrics to reject but users to select; keep data with accountable owners; treat low-resource language work as ecosystem-building.
- **Safety and governance:** Establish institutional ownership before users arrive; design for refusal as much as for response; do not outsource the trust question to a vendor.
- **Experience and sustaining:** Design for silence, introductions, follow-up prompts, and multilingual expansion before scale; build the operating model before launch; expect early failure and build the loop to learn from it safely.

---

## The 20 Learnings: Reference Summary

| # | Learning | Summary |
|---|----------|---------|
| 1 | Start with the excluded user, not the voice bot | Voice AI is most valuable when it solves an access problem. Define the user precisely before anything else. The sharper the user definition, the easier it becomes to decide on channel, model, data, language, and testing process. |
| 2 | Treat voice as a service channel, not a front-end | A voice agent backed by an institution is experienced by the user as the institution itself. Every failure is an institutional failure, not a model failure. |
| 3 | The architecture is simple; the ownership decision is hard | The five-layer stack is fairly stable. The harder decision is how much of it the adopter should own and control. |
| 4 | Start bundled for speed, but plan to unbundle for control | Begin with a bundled full-stack provider to test use-case feasibility quickly. Once proven, begin to unbundle layers separately. The mistake is staying bundled by accident. |
| 5 | Choose models based on language, latency, sector, control, and cost | The best model works for the user, channel, and service context — not the most impressive model. |
| 6 | Lab metrics can reject a model, but users must select it | Use a two-step process: metrics to shortlist or reject, real user and institutional testing to decide what is good enough. |
| 7 | Institutional testing is not optional because the bot represents the institution | Testing should move through stages: builder team, small institutional group, wider institutional group, then limited user rollout. |
| 8 | Safety is about defining what the bot must not answer | Build a safety and stress-test bank before public launch. The goal is to make the bot refuse well, not just answer well. |
| 9 | Small experience choices decide whether the call feels alive or broken | Dead silence, long introductions, unnecessary follow-up nudges, and open-ended questions where yes/no would work better each have known fixes. |
| 10 | Keep the data layer separate from the AI layer | The AI system should consume data from accountable sources through APIs — not own the data. |
| 11 | Data requirements depend on the use case, not the technology | Not every deployment needs a large dataset. The minimum viable data requirement comes from the use case. |
| 12 | Low-resource language work is ecosystem-building, not just data collection | Requires a convening authority, native speakers, annotators, linguistic experts, model builders, hosting infrastructure, and a real-world application. |
| 13 | Do not build your own model unless existing models fail and you have the talent to maintain one | Most deploying institutions are not model-building organizations. Start by adapting available models. |
| 14 | Avoid single-vendor lock-in by testing multiple vendors where possible | Shortlist multiple vendors and test in parallel where feasible. Creates competitive pressure and reduces risk of being stuck. |
| 15 | Cost control comes from architecture, not only negotiation | Track cost per minute, per interaction, by language, and for failed calls from the pilot. Match voice quality to the use case. |
| 16 | Voice AI should extend human capacity, not automatically replace it | The right design combines both: voice AI for structured, scalable interactions; humans for sensitive, complex, or high-risk cases. |
| 17 | Voice should be part of a multichannel design | Voice opens the door, but the service may need other channels to complete the journey. Map the full user journey before committing to voice alone. |
| 18 | Trusted institutional voice matters, especially for users with small trust networks | Users do not trust a voice system because it is AI. They trust it because of who stands behind it, whether it speaks their language, and whether it solves a real problem. |
| 19 | Open orchestration can become reusable public infrastructure | Models need an orchestration layer to become deployable systems. Voiceera — model-agnostic, language-agnostic, telephony-provider-agnostic — was built to address this gap. |
| 20 | Expect early failure; it is how the deployment becomes real | Start small enough that failure is safe, but serious enough that the learning is real. The deployments that succeed are those that create a learning loop around failure. |

---

*This pathway draws from practitioner experience across MahaVISTAAR, Bharat Vistaar, Amul/Sarlaben, Jal Jeevan Mission Assam, the Bhili low-resource language effort, Lend A Hand, and the India–Africa exchange with Crane AI Labs.*
