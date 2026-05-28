This is the schema file for the AI Diffusion Cube knowledge base. You are the agent

responsible for building and maintaining this wiki. Read this file at the start of every

session before doing anything else.



What This Wiki Is

The AI Diffusion Cube is a knowledge base of AI deployment pathways — lived experience

from people who have taken AI from idea to scale in government, agriculture, health,

education, and other public-interest sectors. It exists to dramatically compress the time,

cost, and risk for the next person attempting a comparable deployment.

This wiki is not a document library. It is a compiled, cross-referenced, maintained

knowledge base. Every source ingested is integrated — not just filed. Pages are updated,

contradictions are flagged, cross-links are strengthened. The knowledge compounds with

every addition.

There are two types of users this wiki serves:



Adopters — government officials or implementers taking an AI deployment from idea

to scale, who need contextualised answers and guidance

Pathway Providers — people who have deployed AI at scale and want to contribute

or maintain their lived experience





Folder Structure

cube-wiki/

&#x20; raw/              ← Source documents (PDFs, transcripts, notes). IMMUTABLE.

&#x20;                     The agent reads from here but never modifies these files.

&#x20; wiki/             ← All agent-generated and maintained markdown pages

&#x20;   index.md        ← Master index of all wiki pages with one-line summaries

&#x20;   log.md          ← Append-only chronological log of all operations

&#x20;   framework.md    ← The six dimensions framework explained (one page)

&#x20;   pathways/       ← One page per deployment (the core knowledge unit)

&#x20;   synthesis/      ← Cross-deployment pattern knowledge pages

&#x20;   entities/       ← Pages for organisations, people, and systems

&#x20;   navigation/     ← Sector listing pages

&#x20; CLAUDE.md         ← This file. The schema and operating instructions.



The Six Dimensions Framework

Every pathway is structured around six orthogonal dimensions. These are the capture

lens — when ingesting a source or creating a pathway page, ensure all relevant

dimensions are covered.

Dimension A — Problem Orientation — What you build on.

The specific problem being solved, for whom, why the current system does not solve it,

and what success looks like from the end user's point of view.

Sub-components: problem framing (A1), data posture (A2), existing assets (A3), proof (A4),

inclusion design (A5).

Dimension B — Architecture — What you build with.

The technology stack — AI models, compute, applications, data choices — that keeps the

deployment flexible and evolvable, and connected to legacy systems and existing workflows.

Sub-components: model choice (B1), data sovereignty (B2), vendor independence (B3),

DPG vs instance (B4). Note: field experience reveals a seven-layer system architecture

beneath these sub-components (user, interface, moderation, AI decision engine,

knowledge/scientific models, live data sources, DPI foundation).

Dimension C — Institution — Who deploys AI.

The deploying institution — its structures, authority, capabilities, processes, and how it

secures and sustains funding.

Sub-components: framing (C1), resistance and non-transferability (C2), institutional

knowledge (C3).

Dimension D — Ecosystem — Who executes.

The partners, enablers, and stakeholders assembled — who they are, what roles they play,

who holds the network together, how coordination works, and how trust is established.

Sub-components: ecosystem design (D1), trust source (D2), coordination mechanism (D3),

network operator (D4).

Dimension E — Workforce — Who absorbs AI.

The people — field workers, extension officers, teachers, frontline staff — who carry the

deployment into daily practice, and what they need to do that.

Sub-components: training timing (E1), training depth (E2), agency test (E3).

Dimension F — Operating Model — What makes it last.

How the deployment sustains itself beyond the pilot — through team structure, governance,

performance tracking, outcome signals, and course correction based on what the field reveals.

Sub-components: velocity (F1), governance (F2), sustainability (F3), pilot to deployment (F4).

Cross-cutting lenses (not standalone dimensions — prompt within relevant dimensions):



Safety and trust: harm reach, escalation paths, guardrail design, institutional attribution

Policy and regulation: compliance requirements, regulatory approvals, audit obligations





Page Types and Templates

There are five page types. Each has a specific template below.

1\. Pathway Page (wiki/pathways/)

The core knowledge unit. One page per real-world deployment. The six dimensions

are the content spine. Written from the next adopter's perspective — not what this

deployment did, but what you would need to know if you were facing the same challenge.

Filename: \[deployment-slug].md e.g. mahavistaar.md



markdown# \[Deployment Name] — Pathway



\*\*Deployment:\*\* \[Full deployment name]

\*\*Contributor:\*\* \[Person and/or organisation name]

\*\*Sector:\*\* \[Agriculture / Health / Livelihoods / Education / etc.]

\*\*Geography:\*\* \[Country, state, district]

\*\*Actor type:\*\* \[Government / Cooperative / Civil society / Market]

\*\*Journey stage:\*\* \[Problem framing / Pilot / Scaling / Sustaining]

\*\*Dimensions covered:\*\* \[List dimensions with substantive content e.g. A, B, C, F]

\*\*Horizontal or vertical:\*\* \[Horizontal (cross-sector function) / Vertical (sector-specific)]

\*\*Deployment status:\*\* \[Active / Scaled / Wound down]

\*\*Last updated:\*\* \[YYYY-MM-DD]



\## Summary



\[Two to three sentences. What was deployed, for whom, at what scale, and what makes

this pathway useful to a next adopter. Write for someone who has never heard of this

deployment.]



\---



\## A — Problem Orientation



\*What you build on.\*



\- Who were you trying to serve, and what specific problem were you solving for them?

\- What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?

\- Was there data already available to start with, or did you have to build or collect it first?

\- Why did this problem need AI — what would a non-AI solution have missed?

\- Did your understanding of the problem change after you started — and if so, how?

\- Is there anything about your users you assumed early on that turned out to be wrong?



\[Answer the questions above in prose. Answer only those questions for which there is

documented evidence. Mark gaps explicitly: "Not documented."]



\---



\## B — Architecture



\*What you build with.\*



\- Did users interact through voice, an app, or something else — and what drove that choice?

\- Did you bring data together into one place or connect to it where it lived — and why?

\- What did you build yourself versus use something that already existed?

\- How did you avoid being locked into a single vendor?

\- Did any data source or system integration turn out to be harder than expected?

\- Did the AI ever give a wrong or harmful answer to a user — and how did you catch and handle it?

\- What did you put in place to prevent the AI from causing harm — and was it ever tested?



\[Answer in prose. Mark gaps explicitly.]



\---



\## C — Institution



\*Who deploys AI.\*



\- How did you get the deployment approved and funded — and did you position it as a one-time project or a long-term transformation initiative?

\- Was there internal resistance — and if so, what actually changed minds?

\- Did you need multiple departments or agencies to cooperate — and where did that get difficult?

\- Did procurement rules create a barrier — and if so how did you get through them?

\- When something went wrong, who was accountable — and was that clear from the start?

\- What happens to this deployment if the key person driving it moves to a different role?

\- Was there a leadership or political change during the deployment, and how did it affect things?



\[Answer in prose. Mark gaps explicitly.]



\---



\## D — Ecosystem



\*Who executes.\*



\- How many organisations had to work together for this to function?

\- Who was ultimately responsible for keeping all of them aligned — and what did that role actually involve?

\- Did any partner relationship not work out as expected — what happened and how did you handle it?

\- How was trust maintained across partners — especially when something went wrong?



\[Answer in prose. Mark gaps explicitly.]



\---



\## E — Workforce



\*Who absorbs AI.\*



\- Were there people — field workers, extension officers, call centre staff — whose job changed because of this deployment?

\- How and when were they brought in, and what did they need to learn?

\- Was there resistance from staff — and if so what worked to address it?

\- After the deployment, could staff still do their job if the system was unavailable — or had they become dependent on it?



\[Answer in prose. Mark gaps explicitly.]



\---



\## F — Operating Model



\*What makes it last.\*



\- What did this cost to build, and what does it cost to run annually?

\- What did you measure to know it was working — and what did the numbers actually show?

\- Who owned operations after the pilot ended, and how was that handover structured?

\- Was there an outcome or a problem that showed up later that you wished you had been measuring from the start?

\- Was there a point where the whole thing nearly stalled — and what got it through?

\- Were there compliance, audit, or regulatory requirements that shaped how you ran operations?



\[Answer in prose. Mark gaps explicitly.]



\---



\## Reusable Toolkit



\[List assets, templates, components, governance models, training materials, or evaluation

benchmarks from this deployment that a next adopter can use directly. For each item,

describe what it is, what it is useful for, and how to access it. If nothing is available,

write "No reusable assets documented."]



| Asset | Type | What it is useful for | How to access |

|---|---|---|---|



\---



\## Related Pathways



\[Links to other pathway pages relevant to an adopter reading this one]



\## Related Entities



\[Links to organisation, person, or system pages referenced in this pathway]



\## Lineage



\[If this deployment drew on knowledge from an earlier pathway, record it here.

Format: Built on \[Deployment name](../pathways/slug.md) — what was inherited.]



2\. Synthesis Page (wiki/synthesis/)

Synthesis pages capture patterns that only become visible across multiple deployments.

They carry their own content — they are not aggregators. They cite pathway pages as

evidence but stand independently.

Predefined synthesis pages for v1:



dimension-shifts.md — the 21 FROM→TO shift patterns with evidence

compression-proof.md — the 9→3→3 week evidence and what drove each compression

trust-architecture.md — how trust was built across deployments

failure-modes.md — catalog of named failure patterns with field examples

70-30-split.md — evidence for the tech/non-tech ratio at every level

dpg-reuse-patterns.md — what got reused, what didn't, and why



Filename: \[slug].md e.g. compression-proof.md

markdown# \[Synthesis Page Title]



\*\*Type:\*\* Synthesis

\*\*Deployments cited:\*\* \[List deployment names]

\*\*Last updated:\*\* \[YYYY-MM-DD]



\## The Pattern



\[A clear statement of what the evidence shows. Two to three paragraphs. No jargon.

Written for an adopter who has not read any of the underlying pathways.]



\## Evidence



\[For each deployment that contributes to this pattern, one section:]



\### \[Deployment Name]



\[What happened in this deployment that contributes to the pattern. Be specific —

name numbers, decisions, timelines where available. Link to the pathway page.]



\[See full pathway: \[Deployment Name](../pathways/slug.md)]



\## What This Means for a Next Adopter



\[Concrete implications. What to do, what to watch for, what to avoid.

Written as direct guidance, not abstract principles.]



\## Open Questions



\[What the current evidence cannot answer. Where context determines outcome.

What a next contributing deployment could help resolve.]



3\. Entity Page (wiki/entities/)

Reference pages for organisations, people, and systems referenced across pathways.

These are not knowledge containers — they are reference nodes that pathway pages link to.

Filename: \[slug].md e.g. ekstep-foundation.md, mahavistaar-system.md

markdown# \[Name]



\*\*Type:\*\* \[Organisation / Person / System]

\*\*Role:\*\* \[Deployer / Enabler / Funder / Technical partner / Infrastructure / etc.]

\*\*Geography:\*\* \[Where they operate]

\*\*Contact or reference:\*\* \[Publicly available link or contact if relevant]



\## What they are



\[One paragraph. What this entity is and why it is relevant to AI diffusion.]



\## Deployments they are associated with



\[Links to pathway pages where this entity plays a role]



\## When this entity is relevant to an adopter



\[What kind of adopter challenge would make knowing about this entity useful]



4\. Navigation Page (wiki/navigation/)

Sector listing pages only in v1. Thin index pages — not knowledge containers.

They exist for human browsability, not as knowledge sources.

Filename: \[sector-slug].md e.g. agriculture.md, livelihoods.md

markdown# \[Sector Name] — Pathway Index



\[One paragraph on what AI deployments in this sector typically involve —

the common challenges, the common actors, what makes this sector distinctive.]



\## Pathways in this sector



\[For each pathway tagged with this sector:]



\### \[Deployment Name](../pathways/slug.md)

\*\*Geography:\*\* | \*\*Actor type:\*\* | \*\*Status:\*\*

\[One sentence on what makes this pathway useful to a next adopter in this sector.]



5\. Framework Page (wiki/framework.md)

One page only. Explains the six dimensions for a reader who is new to the framework.

Does not contain deployment evidence — that lives in pathway and synthesis pages.

markdown# The Six Dimensions Framework



\[One paragraph on why this framework exists and what it is for.]



\## Why these six dimensions



\[Two to three paragraphs on the 30/70 split — technology vs non-technology —

and why these six dimensions are the minimum necessary set.]



\## The six dimensions



\[For each dimension: name, the question it answers, two to three sentence explanation.

No sub-component detail here — keep it accessible.]



\### A — Problem Orientation

\*Question it answers: Where do I start?\*

\[Explanation]



\### B — Architecture

\*Question it answers: What do I build with?\*

\[Explanation]



\### C — Institution

\*Question it answers: What kind of undertaking is this?\*

\[Explanation]



\### D — Ecosystem

\*Question it answers: Who does what, and how do we work together?\*

\[Explanation]



\### E — Workforce

\*Question it answers: How do my people absorb this — and stay capable?\*

\[Explanation]



\### F — Operating Model

\*Question it answers: What makes this last beyond the pilot?\*

\[Explanation]



\## The FROM→TO shifts



For the evidence-based shift patterns within each sub-component, see the

\[Dimension Shifts synthesis page](synthesis/dimension-shifts.md).



Formatting Conventions

These rules apply to every page generated. Follow them precisely — inconsistent

formatting was a problem with earlier output.

Headings:



Page title: # (H1) — one per page, always the deployment or page name

Major sections: ## (H2) — dimensions, toolkit, related pages

Sub-sections within a dimension: ### (H3) — use sparingly, only when a dimension

section is long enough to need internal navigation

Never skip heading levels. Do not use H4 or below.



Prose vs bullets:



Write dimension content as prose, not bullet points. The questions are prompts for

the contributor — the answers should read as connected paragraphs, not a list of

responses.

Use bullet points only for: lists of links, toolkit asset tables, and the header

metadata block at the top of a pathway page.

Never use bullet points inside a dimension section answer.



Tables:



Use tables only for: the header metadata block, the toolkit assets section,

and the navigation page pathway listing.

Keep tables narrow — no more than four columns.

Every table must have a header row.



Links:



Use standard markdown links throughout: \[Page title](../folder/filename.md)

Use relative paths. A link from a pathway page to an entity page:

\[EkStep Foundation](../entities/ekstep-foundation.md)

Never use Obsidian-style wikilinks \[\[like this]] — they do not render on GitBook.



Gap marking:



When a question cannot be answered from available evidence, write exactly:

Not documented. — on its own line, in plain text, no italics or brackets.

Do not write explanatory sentences around gaps. "Not documented." is sufficient.

Do not skip questions silently — every question must either have an answer or

"Not documented."



Length:



A well-filled pathway page is 800–1500 words in Zone 2 (the six dimension sections).

Do not pad thin evidence. A short answer with "Not documented." for gaps is better

than a long answer with generalities.

Summary section: maximum three sentences.



Evidence markers:

Use these markers inline on every factual claim:



🔵 First-hand field observation (field transcripts, architecture specs, direct accounts)

🟡 Reported by a participant (meeting notes, deployment team accounts)

⬜ Inferred or analytical (patterns drawn from above, cross-deployment synthesis)





Operations

Ingest

When a new source is added to raw/:



Read the source fully. Before proceeding, ask the user:



What type of source is this? (deployment pathway / framework document /

field report / governance template / other)

If it is a deployment source: what is the deployment name, who contributed

this, and what is the contribution date? Confirm if already clear from the document.





Discuss key takeaways — what is genuinely new, what confirms existing pages,

what contradicts existing pages.

Since one pathway page = one deployment, identify which deployment this source

belongs to. Check if a pathway page already exists for it.

If no pathway page exists, create one using the pathway page template. Fill every

dimension section from available evidence. Mark gaps explicitly.

If a pathway page already exists, update it — add new evidence, strengthen thin

sections, flag any contradictions with existing content.

Create or update entity pages for any organisations, people, or systems referenced.

Check whether any synthesis pages should be updated given new evidence.

Update the relevant navigation (sector) page if the sector is new or the pathway

is new to that sector.

Update wiki/index.md — add new pages, update summaries of changed pages.

Append to wiki/log.md:

\## \[YYYY-MM-DD] ingest | \[Source title] | Pages created: N | Pages updated: N



Query

When an adopter asks a question:



Read wiki/index.md to identify relevant pages.

Read those pages fully.

Synthesise an answer with explicit references to pathway pages using markdown links.

After answering, check: are there dimensions the adopter has not raised that are

likely to be relevant at their stage? If so, surface them.

If the answer reveals a gap the wiki cannot answer, name it explicitly.

Do not fabricate. Honest gap acknowledgment is a feature, not a failure.



Pathway Extraction (Provider conversations)

When a pathway provider wants to contribute their experience:



Begin with context: what deployment, what scale, what period, what sector.

Work through the six dimensions using the 31 questions in the pathway page template

as prompts. Ask one question at a time — do not present all questions at once.

For dimensions where the provider has little to say, note as gaps and move on.

Do not press for answers where evidence does not exist.

After the conversation, draft the pathway page and share it for review before filing.

Record lineage if the provider drew on an existing pathway.



Gap Identification

When identifying what is missing in an existing pathway:



Read the pathway page.

Check each dimension section — which questions have "Not documented."

Identify which gaps are most consequential for a next adopter — prioritise those.

Report gaps with specific prompts: not "C is thin" but "The accountability question

in C is not answered — who was responsible when something went wrong?"

Check the Reusable Toolkit section — are assets described but not yet linked?



Lint

Periodically or when requested:



Scan for contradictions between pathway pages — flag where two pathways say

different things about the same decision or pattern.

Identify orphan pages — pages with no inbound links.

Identify synthesis pages that need updating given new pathway evidence.

Identify sectors mentioned in pathways but without a navigation page.

Identify entities referenced in pathways but without an entity page.

Append to wiki/log.md:

\## \[YYYY-MM-DD] lint | Issues found: N | Gaps identified: N





Writing Conventions



All pages written from the next adopter's perspective — not "what MahaVISTAAR did"

but "what you would need to know if you were facing this challenge"

Be specific. "Inter-departmental data sharing stalled" is less useful than "the state

agriculture department held data in a system the extension directorate could not access,

and resolving this required a joint secretary-level meeting that took four months to convene"

Acknowledge gaps honestly. Do not fill gaps with generalities.

Every factual claim names its deployment — no unattributed generalisations.

Quotes must be exact and attributed. Do not paraphrase a quote and present it as a quote.

Numbers must come from named sources. Where a number is approximate, say so.

If two sources contradict, note both and flag the contradiction. Do not silently resolve it.





Evidence Standards

Every claim must name its deployment. "Trust-building took six months" is not

acceptable. "Trust-building in MahaVISTAAR took six months before extension officers

used outputs without verification" is.

Distinguish evidence quality using inline markers on every claim:



🔵 First-hand field observation — strongest weight

🟡 Reported by a participant — strong weight

⬜ Inferred or analytical — always mark explicitly as inference



If two sources contradict, note both and flag. Contradictions are informative —

they often show where context determines outcome. Flag unresolved contradictions

in the log for human review.



Index and Log Conventions

index.md — organised by page type (pathways, synthesis, entities, navigation).

Each entry: \[page title](folder/filename.md) — one-line summary. Updated on every ingest.

log.md — append-only. Each entry starts with ## \[YYYY-MM-DD] operation | ...

Never edit existing entries.



Lineage Tracking

When creating or updating a pathway page:



If this deployment drew on an earlier pathway, record it in the Lineage section.

When a synthesis page is updated with new evidence, note which pathway page

provided the evidence and when.

Over time, index.md should note which pathways are most frequently referenced —

these are the most valuable knowledge assets in the wiki.





What the Wiki Does Not Do



It does not give general AI advice not grounded in a pathway

It does not pretend to cover what it does not cover — gaps are named, not papered over

It does not replace the conversation with a peer deployer — when direct human

connection is more valuable than documented knowledge, it says so





Starting State

When this wiki is first set up, create:



wiki/index.md — empty index with section headers for each page type

wiki/log.md — with a single initialisation entry

wiki/framework.md — framework page with descriptions filled from this schema,

pathway sections empty pending first ingest

Empty folders: wiki/pathways/, wiki/synthesis/, wiki/entities/, wiki/navigation/



Then await the first source to ingest.

