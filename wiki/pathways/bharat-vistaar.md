# Bharat-VISTAAR — Pathway

**Deployment:** Bharat-VISTAAR — National Agriculture Digital Public Infrastructure
**Contributor:** Ministry of Agriculture and Farmers Welfare, Government of India; EkStep Foundation; OpenAgriNet
**Sector:** Agriculture
**Geography:** India — national
**Actor type:** Government
**Journey stage:** Scaling
**Dimensions covered:** A, B, C, D, F
**Horizontal or vertical:** Horizontal (cross-sector function — national DPI layer for agriculture)
**Deployment status:** Active
**Last updated:** 2026-06-02
**Contact for peer connection:** Ministry of Agriculture and Farmers Welfare, Government of India

## Summary

Bharat-VISTAAR is India's national digital public infrastructure for agriculture — what UPI is for payments, extended to agricultural information and services. Announced in the Union Budget 2026-27 with an allocation of Rs. 150 crore, launched in February 2026, it provides the common rail on which state and cooperative platforms (MahaVistaar, Amul Sarlaben, Bihar Krishi) connect as nodes — each retaining local specificity while drawing on national scheme data, ICAR advisory corpus, and AgriStack integration. It is the architecture that makes the OAN pathway nationally scalable.

---

## A — Problem Orientation

*What you build on.*

**Who were you trying to serve, and what specific problem were you solving for them?**
India has 120 million farmers across dozens of states, languages, crops, and agricultural systems. No single state platform can reach them. The problem Bharat-VISTAAR addresses is the absence of a national common rail: without it, each state or cooperative must build its own knowledge base, scheme connectivity, and data integration from scratch — duplicating infrastructure and preventing national coherence. Bharat-VISTAAR is designed so that Maharashtra does not bear the full cost of the national knowledge base, AgriStack, or ICAR integration — those sit at the national level, amortised across all state nodes.

**Who defined the problem — the deployer, the institution, or the user — and how do you know the user agrees?**
The Ministry of Agriculture and Farmers Welfare defined the national architecture problem. The early evidence from the Saagu Baagu pilot in Telangana — on which the Bharat-VISTAAR design drew — showed a 21% increase in yield per acre and 9% reduction in pesticide use for cotton farmers, indicating that the problem framing (access to integrated advisory) was confirmed by field outcomes.

**How did you define your success metrics — are they usage based or outcome based?**
At Phase 1 launch, metrics were primarily architectural (number of schemes integrated, states connected, data sources live). Longer-term targets include full central scheme integration by May 2026 and ongoing state-level onboarding. The Saagu Baagu pilot provides the outcome benchmark — 21% yield increase, 9% pesticide reduction — that the national platform aspires to replicate at scale.

**Did you discover something in the field that you hadn't anticipated when defining the problem or designing the solution?**
Not documented for Bharat-VISTAAR specifically. The deployment drew on MahaVistaar's nine months of operational learning, including dialect variation and API instability, which were factored into the national architecture.

**Was there data already available to start with, or did you have to build or collect it first?**
India had AgriStack (farmer and farm registries), ICAR (research corpus), IMD (weather), NPSSe (pest surveillance), and PM-KISAN/PMFBY/other scheme systems — all pre-existing. The national layer did not build new data; it connected what existed. Phase-1 integration included PM-KISAN, PMFBY, Soil Health Card, Kisan Credit Card, and 6 other major central schemes.

**Why did this problem need AI — what would a non-AI solution have missed?**
The national architecture requires a system that can synthesise across dozens of institutional data sources simultaneously, in the farmer's language, at the moment of query. A human extension system cannot achieve this at 120 million farmer scale. AI also enables the national layer to serve as a coordination substrate — states connecting their own knowledge while drawing on national resources — without requiring centralised control.

**What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?**
Feature phone access in Hindi and English is provided via short code 155261. The architecture explicitly addresses the inclusion problem: Bharat-VISTAAR is reachable by farmers without smartphones or broadband, through a voice call on any phone. State nodes handle their own language specificity (Marathi via MahaVistaar, Gujarati via Sarlaben, etc.).

**Did you design the system to wait for users to come to it, or did it reach out to them too?**
Both inbound (farmers call 155261) and outbound (proactive push via connected state nodes such as MahaVistaar's daily alerts to 17 lakh farmers) are supported. The national layer amplifies outbound capability across all connected state nodes.

---

## B — Architecture

*What you build with.*

**Did you need data sources that were controlled by other departments or organisations — if so, what did it actually take to get access?**
Bharat-VISTAAR required integration across the Ministry of Agriculture (scheme data), ICAR (advisory corpus), IMD (weather), AgriStack (farmer registries), and multiple state systems. The launch involved PM-KISAN, PMFBY, Soil Health Card, Kisan Credit Card, and 6 other central schemes at Phase 1. Specific negotiation timelines are not documented.

**Did you bring data together into one place or connect to it where it lived — and why?**
Connected to data where it lives, consistent with the OAN architectural principle. The national layer does not replicate state data — it provides the shared knowledge base, scheme connectivity, and AgriStack integration that no single state could build alone. State nodes retain their data and their institutional identity; the national layer adds the common connectivity layer.

**For each major component of your system — did you build it, buy it, or reuse something that existed?**
Bharat-VISTAAR was built on the OpenAgriNet open-source DPGs and the architecture established by MahaVistaar. The national layer reused the same 7-layer architecture, governance frameworks, and data connector approach — adapting them to a national federation model rather than rebuilding them. The six-month compression (Maharashtra: 9 months; Bharat-VISTAAR built on established architecture) was possible because of this reuse.

**Did any data source or system integration turn out to be harder than expected?**
Not documented for Bharat-VISTAAR specifically.

**Did vendor lock-in become a real constraint — what were your options and how did you resolve it?**
The Bharat-VISTAAR architecture follows the same vendor-independence principles as MahaVistaar: open source, open protocols (Beckn), open standards. The national layer uses the Bharat-VISTAAR DPI, which is designed so that each layer can evolve independently. State nodes are not locked to a single model or provider.

**What was your design policy for handling peak load?**
Not documented for Bharat-VISTAAR specifically. The connected state node architecture distributes load across multiple independent deployments.

**Did the AI produce wrong or harmful outputs that reached users — how did you detect it and what did you put in place to prevent recurrence?**
Not documented. The independent moderation layer architecture from MahaVistaar applies across the OAN ecosystem.

**Did data residency, sovereignty, or government policy on technology vendors constrain your architecture — did that come up early or late?**
The national DPI architecture is designed around data residency with institutions. The Rs. 150 crore national allocation was structured to build shared infrastructure that amortises costs rather than creating centralised data stores.

**If you used voice — did you face any problems such as latency, pronunciation, turn-taking and timing?**
Feature phone access via 155261 in Hindi and English is operational. Specific voice pipeline challenges at the national layer are not documented.

**How frequently did the underlying data change, and how did you keep the AI current with those changes?**
Central scheme data (PM-KISAN, PMFBY etc.) changes when policy changes — updates are managed through the national layer. ICAR advisory corpus is relatively stable. Real-time data (weather, prices) is accessed through state node connections to live feeds.

**Did you hit any infrastructure constraint at scale that you didn't anticipate, and how did you resolve it?**
Not documented. Phase-1 launch was in February 2026; full central scheme integration was targeted for May 2026.

---

## C — Institution

*Who owns solving of the problem.*

**Was this deployment treated as a one-time project or as a long-term transformation initiative?**
Bharat-VISTAAR was announced in the Union Budget 2026-27, championed by the Agriculture Minister and the Prime Minister at the India AI Impact Summit, and allocated Rs. 150 crore. The framing is explicitly national digital public infrastructure — the analogy used consistently is UPI for agriculture. This is an infrastructure investment, not a project.

**How did you get the deployment approved and funded?**
Union Budget 2026-27 allocation of Rs. 150 crore. Formally launched by Agriculture Minister Shivraj Singh Chouhan in Jaipur on 17 February 2026. Championed by Prime Minister Modi at the India AI Impact Summit.

**If the one or two people driving this deployment had moved to different roles mid-way, what would have happened?**
Not documented. The Union Budget commitment and national infrastructure framing provide institutional continuity beyond individual champions.

**Which departments had to cooperate for this to work — where did that cooperation break down or get difficult?**
Integration required cooperation across the Ministry of Agriculture, ICAR, IMD, and multiple state agricultural departments. The hub-and-spoke federation model — where states retain their own deployments and connect to the national layer — reduces the coordination burden compared to a centralised model. Specific friction points are not documented.

**Did procurement rules become a barrier?**
Not documented. The national DPI framing, with a Union Budget allocation, may have navigated procurement differently from a project-based deployment.

**Were there decisions that needed political support from above — did you have it when you needed it?**
Yes — and the deployment had it explicitly. Union Budget announcement, Agriculture Minister launch event, Prime Minister endorsement at India AI Impact Summit.

**When something went wrong, who was accountable — and was that clear from the start?**
Not documented.

**Which institution did the AI speak on behalf of — and did that institution have credibility with your end users?**
Bharat-VISTAAR speaks as the Ministry of Agriculture and Farmers Welfare, Government of India, with ICAR providing the advisory authority. Feature phone short code 155261 is associated with the national ministry. State nodes speak with their own institutional authority (Department of Agriculture Maharashtra, Amul cooperative, etc.).

---

## D — Ecosystem

*Who executes.*

**How many organisations had to work together for this to function?**
The national layer connects the same 54-enabler OAN ecosystem as MahaVistaar, plus multiple state government nodes (Maharashtra, Gujarat, Bihar at minimum). The hub-and-spoke model — MahaVistaar, Amul Sarlaben, Bihar Krishi as nodes — means national coordination extends to state-level orchestration teams.

**Who was specifically responsible for keeping all partners aligned?**
The Ministry of Agriculture and Farmers Welfare holds the institutional anchor. EkStep Foundation and the OpenAgriNet ecosystem provide technical orchestration. The network operator role is played by the national ministry.

**Were there partners whose commitment weakened over time?**
Not documented. The national platform is in early operation as of the data available (February 2026 launch).

**Where did partners have conflicting priorities or mandates?**
Not documented.

---

## E — Workforce

*Who absorbs AI.*

**Were there people — field workers, extension officers, call centre staff — whose job changed?**
The national layer's primary workforce impact is mediated through state nodes. Extension officers in connected states (Maharashtra, Bihar, Gujarat) experience the job change at the state deployment level, not the national level directly.

**When the AI gave an answer or recommendation to a user, what was the last-mile human expected to do with it?**
Same as MahaVistaar and connected state deployments — farmers act on advisories directly. Extension officers use AI-supplied information as a reference layer.

**How and when were they brought in, and what did they need to learn?**
Not documented for the national layer specifically.

**Did you face resistance from staff?**
Not documented.

**Did frontline staff become dependent on the system?**
Not documented.

**How did problems or insights from the field reach the people improving the system?**
The national layer inherits MahaVistaar's feedback architecture: queries create a visible demand signal for knowledge gaps. National-layer queries in Hindi and English add to the signal. Governance mechanisms for translating field signals into policy improvements are not documented.

---

## F — Operating Model

*What makes it last.*

**Who took ownership of steady state operations after the pilot?**
The Ministry of Agriculture and Farmers Welfare holds long-term institutional ownership. EkStep Foundation and the OpenAgriNet partner ecosystem provide ongoing technical operation. The Union Budget allocation provides the financial basis for steady state.

**What did it cost to build, and what does it cost to run annually?**
Rs. 150 crore Union Budget allocation for the national layer. The economic logic documented in the Six Shifts framework applies: national-layer amortisation means Maharashtra does not bear the full cost of the knowledge base, AgriStack, or ICAR integration — those sit at the national level. Build-once-deploy-many economics. Per-state and per-cooperative marginal costs decline with each node added.

**Were there compliance, audit, or regulatory requirements that shaped how you ran operations?**
India's Digital Personal Data Protection Act (DPDP) applies. The national DPI design follows the same consent-at-point-of-data-creation architecture as MahaVistaar.

**How long did the deployment actually take versus what you planned?**
Bharat-VISTAAR Phase-1 launched in February 2026, building on MahaVistaar's nine-month pioneer work. The national architecture, governance frameworks, and deployment playbooks were already established. Full central scheme integration was targeted for May 2026.

**Was there a point where the whole thing nearly stalled — and what got it through?**
Not documented.

**What did you measure to know the solution was working?**
Phase-1 launch metrics: 10 major central schemes integrated; ICAR crop and livestock guidance live; real-time IMD weather and NPSS pest alerts operational; feature phone access via 155261 in Hindi and English. The Saagu Baagu pilot (Telangana, precursor design) showed 21% yield increase and 9% pesticide reduction for cotton farmers. Full outcome measurement across the national platform is ongoing.

**Did you do a big launch or sequence through small pilots?**
The national platform launched formally in February 2026, but it was built on years of state-level piloting (MahaVistaar nine months, Bihar Krishi, Amul Sarlaben). The launch was a milestone on a sequenced pathway, not a cold start.

---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| Hub-and-spoke federation model | Architecture pattern | Building a national layer that amplifies state/cooperative nodes without replacing them | OAN Diffusion Pathway document |
| ICAR advisory corpus integration | Knowledge base | National-level crop and livestock advisory accessible to any connected state node | Via Ministry of Agriculture / OpenAgriNet |
| AgriStack integration layer | DPI connector | Farmer identity and farm registry access for personalised advisory | Via Ministry of Agriculture / AgriStack |
| PM-KISAN, PMFBY, Soil Health Card, Kisan Credit Card integration | Scheme connectivity | Central scheme status and eligibility accessible via any OAN node | Via Ministry of Agriculture |
| Short code 155261 (Hindi and English feature phone access) | Reach infrastructure | National voice entry point for feature phone farmers | Operational |

---

## Related Pathways

- [MahaVistaar](mahavistaar.md) — pioneer state deployment; architecture Bharat-VISTAAR was built on
- [Amul Sarlaben](amul-sarlaben.md) — cooperative node connected to the national layer
- [Bihar Krishi](bihar-krishi.md) — state node that connected to Bharat-VISTAAR

## Related Entities

- [EkStep Foundation](../entities/ekstep-foundation.md)
- [OpenAgriNet](../entities/openagri-net.md)

## Lineage

Built on [MahaVistaar](mahavistaar.md) — architecture, governance frameworks, data connector approach, and failure mode library all inherited. Bharat-VISTAAR is the national amplification of the Maharashtra pioneer deployment.
