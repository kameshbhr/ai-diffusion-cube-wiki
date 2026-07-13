# The Seven Dimensions Framework

This framework exists to answer a single practical question: what does an adopter actually need to decide, in order to take an AI deployment from idea to scale in a public-interest context? It was distilled from the lived experience of deployers who have walked this path — in Maharashtra, Gujarat, Bihar, Ethiopia, and district livelihoods economies — and from the patterns that became visible only when those experiences were examined side by side.

The framework has four parts: the seven dimensions themselves (what must be navigated), the four stages (where an adopter is on their journey), the question bank (what to actually ask, at every stage × dimension intersection), and the five unit types plus pathway document structure (the shape reusable knowledge takes once it's captured).

## Why these seven dimensions

A diffusion pathway has to answer two questions: what are you deploying? (the 30% — technology) and how does it get absorbed? (the 70% — everything else). Most AI deployments over-invest in the first question and under-invest in the second. The result is technically functional systems that nobody uses, or that collapse when the project champion moves on.

The dimensions are orthogonal — failure in any one of them can stop a deployment regardless of how well the others are handled. They are not a checklist to complete once; they are the questions an adopter needs to keep returning to as their journey unfolds, from first exploring whether AI is the right answer through to scaling a deployment the founding team can walk away from.

## The seven dimensions

| # | Dimension | Central question | Sub-components |
|---|---|---|---|
| 1 | **Problem & Foundation** | What are we building on? | Use case, persona, current service delivery, what fails today, success definition, geographic and institutional context |
| 2 | **Architecture** | What are we building with? | Stack choice, bundled vs. unbundled, component selection, integration, vendor posture, sovereignty, infrastructure |
| 3 | **Data** | What fuels it — and who owns it? | Sources and owners, readiness level, residency, consent and governance, update cadence, what stays with the institution vs. what travels to the model |
| 4 | **Institution** | Who transforms? | Internal mandate, governance structure, policy anchors, approval process, content authority, funding model, absorption vs. delegation |
| 5 | **Ecosystem** | Who executes? | Partner map, trust network, last-mile delivery, convening authority, precedent deployments, what cannot be done alone |
| 6 | **Workforce** | Who absorbs? | Frontline roles, current reach, training design, adoption friction, capability vs. dependency |
| 7 | **Operating Model** | What makes it last? | Who pays in year two, who maintains, who retrains, who governs failures, escalation routes, staffing plan not just funding plan |

### 1 — Problem & Foundation

The specific problem being solved, for whom, and why the current system fails them. This is the foundation everything else rests on. If you cannot name the specific person who is excluded today, what they do instead in the absence of a solution, and why that workaround falls short, the rest of the framework rests on an unstable base.

### 2 — Architecture

The technology stack that keeps the deployment flexible and evolvable. The question is not "which model is best?" It is "which of these choices, if wrong, would take six months to undo?" Irreversible decisions — data residency, vendor lock-in points, model sovereignty, who owns the orchestration layer — need to be identified before a line of code is written.

### 3 — Data

Data sources and their owners, readiness level, residency, consent and governance, update cadence, and — critically — what stays with the institution versus what travels to the model. This dimension behaves differently from Architecture: a deployment can have the right architecture and still fail because no named person is accountable for a data source's accuracy, update frequency, or correction. "We'll find data" is not an answer; naming the type, the likely source, and whether that source is willing to participate is the minimum bar.

### 4 — Institution

The deploying institution — its internal mandate, governance structure, policy anchors, approval process, content authority, funding model, and whether it absorbs the change or delegates it away. Not procurement sign-off, but the named person whose professional stake is tied to this succeeding, and — as the deployment matures — whether the institution has genuinely absorbed the work (budget line, named owner, regular review) or whether it is still, quietly, the founding team's problem.

### 5 — Ecosystem

The partner map, trust network, last-mile delivery mechanisms, convening authority, relevant precedent deployments, and — importantly — what cannot be done alone. Every unnamed dependency is an unmanaged risk. This dimension also captures what can be transferred to the next adopter and under what conditions: what works when certain conditions hold, and fails when they don't.

### 6 — Workforce

The frontline roles that reach the end user, their current reach, how training is designed, where adoption friction shows up, and — the central test of this dimension — whether the deployment leaves people more capable or more dependent. A frontline worker's stance toward the technology — as threat, tool, or irrelevant — shapes the entire training and adoption design, and is worth surfacing explicitly rather than assuming.

### 7 — Operating Model

Who pays in year two, who maintains the system, who retrains, who governs failures, what the escalation routes are, and — critically — the staffing plan, not just the funding plan. A deployment dies when the founding team moves on if no one else has been named to run it. This dimension also carries the order-of-magnitude cost sense an adopter needs early, and the actual cost-per-interaction data a deployment needs once live.

## The four stages

An adopter moves through four stages. Each dimension above must be revisited at each stage — the questions worth asking about Data at Explore are different from the questions worth asking about Data at Scale.

| Stage | What's happening | Central question | Done when... |
|---|---|---|---|
| **Explore** | Understanding whether AI is the right answer, and what it would actually take. | Who exactly is failing to get what — and is there evidence AI helps? | Precise excluded-user definition. Honest comparison with current alternatives. Order-of-magnitude cost sense. |
| **Define** | Scoping and building a minimal testable version — architecture, data, team, mandate. | What are the irreversible decisions, and have we made them correctly? | Named data owners. Named internal mandate holder. Architecture posture chosen. Safety boundaries designed. |
| **Pilot** | Live with real users in a constrained context. Learning what breaks. | What's breaking — and is it fixable before we scale? | Failure taxonomy (scope vs. quality vs. experience) established. Named institutional response to first public failure. Real cost-per-interaction data. |
| **Scale** | Expanding to population and institutionalising so the deployment survives the founding team. | Can the institution own, govern, and improve this without us? | Budget line in place. Named operational owner. Monitoring mechanism live. Operating model written down. |

## The question bank — four stages × seven dimensions

What to probe at every stage × dimension intersection. The core question is what you ask. "What you're listening for" is the signal that tells you you've found a unit worth capturing. The insight form is what you're extracting. The corpus example shows the level of specificity required.

Before an interview: mark which cells a document review already answers. Ask only the unmarked cells. Stop when you have a decision, the alternative considered, and the condition that made it right — that is one complete unit.

### Explore — Understanding: is AI the right answer, and what would it actually take?

| Dimension | Core question | What you're listening for | Insight form | Corpus example |
|---|---|---|---|---|
| Problem & Foundation | Who specifically is excluded from this service today — and why? | The workaround is key data. What do they do instead? The replacement baseline shapes everything. | Excluded user + named barrier + current workaround | MahaVISTAAR: women farmers receiving contradictory advice from fertiliser sellers. No trusted official source in their language. |
| Architecture | What channel or system are you replacing — and what does it fail at? | Two human callers. Paper forms. Nothing. The failure mode of the current channel sets the architecture bar. | Current channel + its specific failure mode | Lend A Hand: two human callers couldn't collect fortnightly feedback from thousands of dispersed interns. |
| Data | What data does this system need — and does any of it currently exist in usable form? | Name the data type, the likely source, whether that source is willing. "We'll find data" is not an answer. | Data requirement map: type × source × availability | JJM Assam: needed only phone numbers + 5 questions. No large dataset. Use case determines data shape. |
| Institution | Who inside the institution has to personally want this to work — and do they know yet? | Not procurement sign-off. The person whose professional stake is tied to this succeeding. | Named internal champion + their specific stake | MahaVISTAAR: Commissioner-level ownership required before any department would authorise data connections. |
| Ecosystem | Who else has tried to solve this for this population? What happened? | Precedent deployments, failed attempts, adjacent tools. Who do they trust as a reference peer? | Named precedent + what transferred + what didn't | Ethiopia ATI drew on MahaVISTAAR: 9 months → 3 months. Architecture transferred. Farmer-trust mechanics needed local adaptation. |
| Workforce | Who are the frontline people who reach this user — and how do they see AI? | Threat, tool, or irrelevant? Their stance shapes the entire training and adoption design. | Frontline role + current reach + stance on AI | MahaVISTAAR: extension workers saw the bot as a replacement. Reframe: "bot handles the 3am question, you handle the relationship." |
| Operating Model | Order-of-magnitude: what would this cost to set up and run annually? | Not a precise quote. A reality check. | Cost anchor (order of magnitude) + who absorbs it | MahaVISTAAR ~$250K setup, ~$250K/year at 205K queries/month is a useful anchor. Bharat-VISTAAR national layer: ₹150 crore for shared infrastructure amortised across states. |

### Define — What are the irreversible decisions? What must be true before we build?

| Dimension | Core question | What you're listening for | Insight form | Corpus example |
|---|---|---|---|---|
| Problem & Foundation | What is the one question a user will ask that this system must answer — or the pilot fails? | Forces scope to its minimum. This question determines the data model, prompt design, and safety boundaries. | Single critical use case + binary success definition | MahaVISTAAR: "What should I spray this week in my village?" Required live mandi data, weather API, pest calendar, conversational Marathi. |
| Architecture | Which architecture choices, if wrong, would take six months to undo? | Data residency, vendor lock-in points, model sovereignty, orchestration layer ownership. Identify before writing code. | Irreversible decisions list + alternatives considered | Voice AI: a fully proprietary bundled stack means you can't change TTS, ASR, or the data pipeline without rebuilding. Design the unbundling path in now. |
| Data | Name every data source this system needs — and the named person accountable for each one's accuracy. | Not "government data." ICAR. IMD. APMC. NIPHM. Each with a named human accountable for accuracy, update frequency, and correction. | Data source registry: source × owner × update cadence × accountability | MahaVISTAAR: four named data owners before launch. Each connected via API — the AI layer consumes but doesn't own the data. |
| Institution | Who in your institution approves what the bot says — and have they agreed to own that? | Content authority, not technical sign-off. A named official accountable for every answer. Without this, the bot has no institutional standing. | Content authority + approval and escalation process | Voice AI: the bot speaks in the department's name. The department must own every answer — including wrong ones. |
| Ecosystem | Which parts can you not build yourself — and do you have a named partner for each? | Data owners, language models, telephony partners, integrators, field networks. Unnamed dependencies are unmanaged risks. | Dependency map: component × build-or-source × named partner | Bhili: eight distinct ecosystem roles, all named before model work. The project stalled when the linguist role went unnamed for three months. |
| Workforce | Who inside the institution must test this before users hear it — and have they agreed to that timeline? | Staged: builder team → small institutional group → wider group → limited rollout. Each stage needs a gate criterion. | Testing progression: stage × named tester × gate criterion | MahaVISTAAR moved to district rollout only after department officials had done field testing. Outsourcing testing to a vendor is a known failure pattern. |
| Operating Model | What does this prototype need to demonstrate for the institution to commit to a real pilot — and by when? | The scale trigger. Without a named criterion and timeline, prototypes never end — they just lose momentum. | Success criterion + timeline + named decision-maker | Voice AI: teams that skipped institutional testing spent 2–3 months managing public failures that a 2-week test would have caught. |

### Pilot — Live with real users. What's breaking?

| Dimension | Core question | What you're listening for | Insight form | Corpus example |
|---|---|---|---|---|
| Problem & Foundation | Which user interactions are failing — is that a scope problem or a quality problem? | Scope = users asking outside mandate. Quality = the bot answering mandate questions badly. Different fixes. | Failure taxonomy: scope vs. quality vs. experience | Voice AI: out-of-mandate answers = institutional boundary crossing. Required explicit refusal design, not better prompting. |
| Architecture | Which component is causing the most pain — and is it replaceable in this architecture? | Bundled-vs-unbundled plays out in practice here. Can you swap TTS? Is the ASR failure in the model or the data? | Component failure + replaceability assessment + switching cost | Voice AI: silence during backend fetch felt like a dropped call. Fix: hold message. The lesson is in the UX layer, not the model. |
| Data | Which data source is going stale or giving wrong answers — and how fast is the owner fixing it? | Data quality failures at Pilot look like AI failures to users. The fix is a governance conversation, not a model improvement. | Data quality issue + accountable owner + response time + resolution | MahaVISTAAR: a 48-hour mandi price lag caused wrong harvest-timing advice. Fix: governance call with APMC to a 6-hour cadence — not a technical fix. |
| Institution | What has the institution seen fail publicly — and did they own it or disown it? | How the institution responds to the first failure is the most important signal about whether this will scale. | First public failure + institutional response (own vs. disown) | Voice AI: the bot answered outside mandate. The department tightened refusal boundaries — it didn't shut down. Ownership held. |
| Ecosystem | Which partner is underperforming — and do you have an alternative? | Mid-pilot switching is painful but possible. Post-scale switching requires a rebuild. The time to diversify is now. | Partner performance log + contingency plan | Voice AI: parallel vendor testing is recommended precisely because mid-pilot switching is possible. Post-scale switching typically requires a rebuild. |
| Workforce | Are the people supposed to be using this actually using it — or working around it? | Workarounds are the most honest feedback signal. If field workers call users manually instead of routing through the system, that reveals what the system fails at. | Actual vs. intended usage pattern + specific workaround description | MahaVISTAAR: tracked queries per active user. High total + low per-user frequency = low trust, not high adoption. |
| Operating Model | What is the actual cost per interaction — and where did the projection go wrong? | Track: cost per minute, per completed interaction, per language, for failed calls. Surprises almost always in Indic tokenisation, agentic calls, or TTS premium. | Cost per interaction by component: actual vs. projected + variance | Voice AI: Indic tokenisation overhead surprises every adopter who modelled on English benchmarks. |

### Scale — Expanding to population. Can the institution own this without the founding team?

| Dimension | Core question | What you're listening for | Insight form | Corpus example |
|---|---|---|---|---|
| Problem & Foundation | Are new user segments arriving that the pilot wasn't designed for? | Scale reveals "the user" was multiple users. Feature phone vs. smartphone. Dialect A vs. B. Each may need different design. | User segment expansion map + design change required per segment | Voice AI: multilingual demand discovered post-launch. Retrofitting is significantly harder than designing for it from the start. Preventable. |
| Architecture | Which components are you now unbundling — and what triggered the decision? | Cost and control arguments become concrete numbers at scale. TTS cost per million calls ≠ TTS cost per thousand. | Unbundling decision: component × trigger condition × expected gain | Voice AI: stack unbundling and offline voice models became essential for low-connectivity populations — and can't be retrofitted without a rebuild. |
| Data | Which data sources are breaking under scale — and do formal SLAs exist? | What held at 1,000 queries/month may not hold at 100,000. Accountability needs formalising. | Data SLA map: source × update cadence × escalation owner at scale | Bharat-VISTAAR: required formal data SLAs with 12 state agriculture departments. Each became an accountable node. |
| Institution | Has the institution absorbed this — or is it still the project team's problem? | Absorption: in the budget, named owner, failures reviewed in regular management processes. | Absorption indicators: budget line + named owner + review cadence | Voice AI: the shift from "project" to "service" is the signal. Departmental adoption requires owning voice as a service. |
| Ecosystem | What from your deployment could the next adopter reuse — with what conditions? | Not "we did X." "X works when Y is true, fails when Z is true." The condition tag is the most important part. | Transferable unit + condition tag (applies when / fails when) | MahaVISTAAR → Ethiopia ATI: architecture and trust-framing transferred. Specific data partnerships didn't — condition: government credibility as the trust mechanism. |
| Workforce | Does the system leave people more capable — or more dependent? | The test: a farmer who calls every time it rains is dependent. A farmer who internalises the logic and calls for confirmation is more capable. | Agency outcome: evidence of capability growth vs. dependency pattern | MahaVISTAAR: query specificity increased over 18 months — interpreted as growing agricultural knowledge, not just bot usage. |
| Operating Model | Who retrains, updates, and manages vendors — and are they hired? | The operating model question at scale is staffing, not just funding. A deployment dies when the founding team moves on if no one else knows how to run it. | Operational roles map: function × current owner × successor plan | Voice AI: "if the funding model is unclear, the project is already dead" applies equally to the staffing model. |

## The five unit types

The unit is the atomic element of captured knowledge — what gets tagged, stored, and retrieved when a pathway is extracted from a deployer. A summary is never a substitute for a unit.

| Type | Definition | What makes it reusable |
|---|---|---|
| **Strategic micro-innovation** | A framing, governance, or design decision that shaped what got built — usually invisible in the final product. | The condition tag: when does this apply, and when does it not? |
| **Tactical micro-innovation** | A stack, sequence, cost, or implementation decision specific enough to reuse. | A before→after: what changed because of this decision? |
| **Failure unit** | Something that broke, plus what the fix revealed about the system. | The fix, not just the failure — the fix is what reveals the structural insight. |
| **Playbook** | A sequence of decisions or actions for a recurring deployment situation. | Actionable process knowledge: "if X, do Y before Z." Sequence matters. |
| **Toolkit asset** | A reusable technical component, template, or governance artefact. | Another adopter can lift and adapt it without rebuilding from scratch. |

## The pathway document structure

A pathway document is not a case study. A case study documents what was built. A pathway document is written for the next adopter — what they would need to decide, the alternatives they would consider, and the conditions under which different choices are correct.

Physical analogy: a pathway is not the route the pioneer took. It is the marked trail they left for the next traveller.

Every pathway follows the same seven-section structure:

| Section | Name | Purpose | Contents |
|---|---|---|---|
| 0 | Reading guide | Orients the adopter | What a pathway is. How retrieval works. Where reusable value concentrates. How to navigate by stage. |
| 1 | Pathway identity | Names the deployment for retrieval | Deployment name, sector, geography, population served, stage reached, contributing organisation, key dates, 2-sentence summary. |
| 2 | The 4×7 grid | Shows where knowledge is dense and where gaps remain | Coverage map: darker cells = more captured units; empty = known gaps. Readers navigate to their stage. |
| 3 | Micro-innovations | The core reusable content | 30–40 tagged units organised by dimension. Each: decision, alternative considered, condition tag (applies when / fails when), before→after outcome. |
| 4 | Toolkits and playbooks | Reusable artefacts and process knowledge | Technical templates, governance frameworks, testing protocols, prompt patterns, vendor criteria — each tagged with conditions for reuse. |
| 5 | Problem→solution patterns | Maps recurring problems to known fixes | Problem → root cause → solution → result → condition. Cross-deployment patterns (dead silence, vendor lock-in, data ownership failure) gathered across deployments. |
| 6 | Retrieval guide | Helps the next adopter find what's relevant fast | Organised by innovation intent (e.g. "I need to avoid vendor lock-in at Define stage") → points to relevant units and toolkit assets. |

## How the parts fit together

The seven dimensions are the capture lens — they ensure that when knowledge is extracted from a deployer, nothing important is missed. The four stages locate where in the journey that knowledge applies — the same dimension raises different questions at Explore than it does at Scale. The question bank is where the two intersect: it is the concrete, askable version of "dimension × stage," and it's what a data collector or a guided conversation actually works from. The five unit types are the shape that knowledge takes once captured — never a narrative summary, always a decision, a condition, and an outcome. The pathway document structure is how a complete set of those units is assembled and published for the next adopter to navigate.

Together: a pathway is a set of tagged units, each belonging to one of seven dimensions and one of four stages, of one of five types, assembled into the seven-section pathway document. The 4×7 grid is the coverage map at the centre of it — darker cells mean more has been captured for that stage-dimension pair; empty cells are known gaps, and are as important to flag as the cells that are filled in.

The framework is evolving.
