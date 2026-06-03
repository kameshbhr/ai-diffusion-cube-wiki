# Problem Surfacing — What Adopters Get Stuck On

**Type:** Framework
**Last updated:** 2026-06-03

---

## Purpose

Most AI deployments fail not because of technology but because of problems the adopter either got stuck on or was never aware of. This page defines those problems across two levels — pathway execution and use case/solution — and provides the questions used to surface them from pathway contributors.

The problems at execution level are universal — they occur regardless of what is being built. The problems at use case level are specific to the nature of what is being built and who is being served.

As the knowledge base grows, each problem will be linked to pathway evidence showing how it manifested and what worked to address it.

---

## Level 1 — Pathway Execution Problems

Problems that any adopter will likely face during deployment, regardless of the use case. Organised by the six dimensions framework.

### A — Problem Orientation

- Problem framed too broadly to be deployable
- Problem defined by deployer, not validated with the actual user
- Solution designed around deployer's mental model, not user's mental model
- Use case scope too wide — tries to serve too many needs, serves none well
- Users have a workaround that works well enough — switching cost is real even if informal
- Metrics measuring system activity rather than user outcomes
- Inbound-only design when the use case requires proactive outreach
- Field conditions different from what was designed for

### B — Architecture

- Waiting for clean data before deploying — deployment never starts
- Data exists but access blocked by inter-departmental silos
- Build vs buy vs borrow decision not made consciously — defaulted to rather than designed
- Integrating with existing systems — legacy infrastructure, data formats, workflows, and institutional owners of those systems create unexpected friction
- Vendor lock-in realised too late
- Hallucinations or wrong outputs reaching end users with no detection or correction mechanism
- Data/Tech sovereignty constraints not anticipated — hits mid-deployment or at scale
- Infrastructure constraint hits at scale that was not anticipated

### C — Institution

- Positioned as project with an end date, not a capability being built permanently
- Key person dependency — deployment collapses when driver moves roles
- Institutional memory not captured — knowledge lives in people's heads
- Multi-department cooperation required but no one has authority over all departments
- Procurement rules create a barrier that stalls the deployment
- No political cover for decisions that actually matter

### D — Ecosystem

- No one assigned to keep all partners aligned — coordination assumed but not owned
- Partner commitment erodes over time because sustained incentive wasn't designed
- Competing mandates between partners not surfaced or resolved early
- No clear accountability when something goes wrong

### E — Workforce

- Training happens after deployment rather than as part of it
- Frontline staff become dependent on the system — capability atrophies
- Staff resistance because authority or relevance feels threatened
- Last-mile human's incentives not aligned with adoption — they see AI as reducing their relevance
- Last-mile human not equipped to handle what the AI surfaces
- No feedback loop from frontline to product team

### F — Operating Model

- Pilot succeeds but can't transition to steady state
- Funding model unclear — deployment is already dead even if it looks alive
- Estimated cost shooting up during implementation or at scale
- Pilot worked but adoption at scale is not happening
- Timeline assumptions wrong — what was planned takes much longer
- Governance adds overhead instead of enabling speed
- Course corrections too late because signals weren't acted on
- Measuring outputs not outcomes
- Big launch mentality instead of small pilots

---

## Level 2 — Use Case / Solution Problems

Problems specific to the nature of what is being built and who is being served. These are not about how the deployment is run — they are about whether the solution is designed to work for the specific user in the specific context.

### Specific to low-literacy / low-connectivity use cases

- Users not digitally literate — solution assumes smartphone and text literacy they don't have
- Low or no connectivity — solution assumes network availability that doesn't exist in the field
- Language and dialect gaps — solution works in the standard language, not in how users actually speak
- Voice recognition fails on local dialects, accents, or domain-specific terminology

### Specific to advisory use cases

- Users don't trust the source — the institution the AI speaks on behalf of has no credibility with this user
- Safety-critical outputs without adequate guardrails — wrong dosage advice, misread conditions, outdated eligibility

### Specific to use cases requiring proactive outreach

- Inbound-only design when the use case requires the system to reach out to users, not wait for them

---

## Extraction Questions — For Pathway Contributors

These questions are used when extracting lived experience from a pathway contributor. They are designed to surface whether and how each problem above occurred, and what was done about it. Ask one question at a time. Do not present all questions at once.

### A — Problem Orientation

1. Who were you trying to serve, and what specific problem were you solving for them?
2. Who defined the problem — the deployer, the institution, or the user — and how do you know the user agrees?
3. How did you define your success metrics — are they usage based or outcome based?
4. Did you discover something in the field that you hadn't anticipated when defining the problem or designing the solution?
5. Was there data already available to start with, or did you have to build or collect it first?
6. Why did this problem need AI — what would a non-AI solution have missed?
7. What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?
8. Did users interact through voice, an app, or something else — and what drove that choice?
9. Did you design the system to wait for users to come to it, or did it reach out to them too?

### B — Architecture

1. Did you need data sources that were controlled by other departments or organisations — if so, what did it actually take to get access?
2. Did you bring data together into one place or connect to it where it lived — and why?
3. For each major component of your system — did you build it, buy it, or reuse something that existed? Would you make the same choices again?
4. Did any data source or system integration turn out to be harder than expected?
5. Did vendor lock-in become a real constraint — what were your options and how did you resolve it?
6. What was your design policy for handling peak load?
7. Did the AI produce wrong or harmful outputs that reached users — how did you detect it and what did you put in place to prevent recurrence?
8. Did data residency, sovereignty, or government policy on technology vendors constrain your architecture — did that come up early or late?
9. If you used voice — did you face any problems such as latency, pronunciation, turn-taking and timing? What did you do to address it?
10. How frequently did the underlying data change, and how did you keep the AI current with those changes?

### C — Institution

1. Was this deployment treated as a one-time project or as a long-term transformation initiative — did that framing create problems?
2. How did you get the deployment approved and funded?
3. If the one or two people driving this deployment had moved to different roles mid-way, what would have happened?
4. Which departments had to cooperate for this to work — where did that cooperation break down or get difficult, and how was it resolved?
5. Did procurement rules become a barrier — and if so how did you navigate through?
6. Were there decisions that needed political support from above — did you have it when you needed it?
7. When something went wrong, who was accountable — and was that clear from the start?
8. Which institution did the AI speak on behalf of — and did that institution have credibility with your end users? If not, how did you address it?

### D — Ecosystem

1. How many organisations had to work together for this to function?
2. Who was specifically responsible for keeping all partners aligned — was that role clearly assigned and resourced?
3. Were there partners whose commitment weakened over time — what drove that and how did you handle it?
4. Where did partners have conflicting priorities or mandates — how were those conflicts resolved?

### E — Workforce

1. Were there people — field workers, extension officers, call centre staff — whose job changed because of this deployment?
2. When the AI gave an answer or recommendation to a user, what was the last-mile human expected to do with it — and were they actually capable of doing that?
3. How and when were they brought in, and what did they need to learn?
4. Did you face resistance from staff — what were the reasons and what worked?
5. Did frontline staff become dependent on the system in a way that reduced their own capability — how did you know?
6. How did problems or insights from the field reach the people improving the system — was there a structured feedback loop?

### F — Operating Model

1. Who took ownership of steady state operations after the pilot — how was that transition structured and when did it happen?
2. What did it cost to build, and what does it cost to run annually — how did those compare to your original estimates? Which cost components surprised you most — at implementation stage or when you started to scale?
3. Did you hit any infrastructure constraint at scale that you didn't anticipate, and how did you resolve it?
4. Were there compliance, audit, or regulatory requirements that shaped how you ran operations?
5. How long did the deployment actually take versus what you planned — where did time get lost?
6. Was there a point where the whole thing nearly stalled — and what got it through?
7. What did you measure to know the solution was working — and what did the numbers actually show? Was there an outcome or a problem that showed up later that you wished you had been measuring from the start?
8. What decisions needed approval from a committee or senior leadership — did that slow you down, and how did you handle it?
9. Was there a point where usage dropped, complaints increased, or a key partner disengaged — how long did it take you to respond and what did you do?
10. Did you do a big launch or sequence through small pilots — and looking back was that the right call?

---

## How This Page Evolves

This page is a starting point, not a complete picture. As pathways are added to the knowledge base, each problem above will be linked to specific deployment evidence — how it manifested, what was tried, what worked. Problems that appear frequently across deployments will be promoted to synthesis pages. New problems that emerge from pathway evidence will be added here.

If you are a pathway contributor and your deployment surfaced a problem not listed here, flag it in the extraction conversation.
