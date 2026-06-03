# Amul Sarlaben — Pathway

**Deployment:** Amul Sarlaben — Cooperative AI Advisory for Dairy Producers
**Contributor:** Amul (Gujarat Cooperative Milk Marketing Federation); EkStep Foundation; OpenAgriNet
**Sector:** Agriculture (dairy / cooperative)
**Geography:** India — Gujarat, 18,500+ villages
**Actor type:** Cooperative
**Journey stage:** Scaling
**Dimensions covered:** A, B, C, D, E, F
**Horizontal or vertical:** Vertical (sector-specific — dairy cooperative)
**Deployment status:** Active
**Last updated:** 2026-06-02
**Contact for peer connection:** Amul — amul.com; EkStep Foundation — ekstep.org

## Summary

Amul Sarlaben is an AI advisory system built for Amul's 3.6 million milk producers — predominantly women — across 18,500+ villages in Gujarat. It places the intelligence locked in Amul's 50 years of cooperative data (2 billion milk procurement transactions, records on 30 million cattle) directly in the hands of the farmer through a voice call in Gujarati on any phone. It was deployed in three weeks — by far the fastest deployment yet documented on the OAN pathway — because the architecture, governance frameworks, and deployment playbooks had already been built by MahaVistaar and did not need to be rebuilt. Referenced by Prime Minister Modi at the India AI Impact Summit 2026.

---

## A — Problem Orientation

*What you build on.*

**Who were you trying to serve, and what specific problem were you solving for them?**
Amul serves 3.6 million milk producers, predominantly women, across 18,500+ villages in Gujarat. The specific problem was a data access paradox: Amul held 50 years of cooperative data — 2 billion milk procurement transactions, records on 30 million cattle each with a unique ID tracking feed, health, treatment, and milking history, 1,200+ veterinary doctors' records annually — but this data had never spoken back to the farmer who generated it. The farmer's own animal's history was inaccessible to her. The cooperative had 1,400 veterinary doctors serving 3.6 million farmers and 22 million cattle — a ratio that makes individual advisory impossible without AI.

**Who defined the problem — the deployer, the institution, or the user — and how do you know the user agrees?**
The Amul cooperative leadership defined the problem after seeing the MahaVistaar demonstration and recognising that the same approach applied to their cooperative data. The Six Shifts framework documents the CEO's conversion: from "data is the new oil, I don't understand what that means" to "after I saw data coming together, I started seeing the magic" — after seeing AI working on Amul's own data. The user confirmation came through usage: 1 million+ app downloads and 3.6 million farmers reached at launch.

**How did you define your success metrics — are they usage based or outcome based?**
At launch: 3.6 million farmers reached, 1 million+ app downloads, voice access in Gujarati for feature phone and landline users. Personalised advisory based on each animal's individual history was the key quality metric. Full agronomic outcome metrics (milk yield improvement, animal health outcomes) are not documented in available sources at this stage.

**Did you discover something in the field that you hadn't anticipated when defining the problem or designing the solution?**
The Six Shifts framework documents the agency test surfaced by the Amul deployment: younger family members who lack thirty years of dairy experience can now access expert knowledge through Sarlaben — "informed, therefore powerful to make choices; freedom comes from knowing, and nobody can fool me." This equaliser effect — AI giving the less-experienced person access to what the expert knows while preserving their autonomy — was a field discovery, not a designed-in outcome. The companion finding was also noted: information alone is not the point; there is skill in the hand that counts for more than information in the head.

**Was there data already available to start with, or did you have to build or collect it first?**
Amul had the richest data foundation of any documented deployment: 2 billion milk procurement transactions, records on 30 million cattle with unique IDs, 1,200+ veterinary doctors' records, and 50 years of cooperative history. The data existed; the AI layer to surface it to the farmer did not. The Six Shifts framework cites this as the example of maximum asset readiness — a contrast with deployments that had to build data infrastructure first.

**Why did this problem need AI — what would a non-AI solution have missed?**
At 1,400 veterinary doctors for 3.6 million farmers and 22 million cattle, individual advisory is structurally impossible at the veterinarian-to-farmer ratio. AI enables personalised advisory at the animal level — drawing from each animal's unique history — which would require an enormous veterinary workforce if done by humans. The cross-institutional synthesis aspect is less central here (Amul holds most of its own data) but the personalisation-at-scale argument is decisive.

**What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?**
Amul's producers — predominantly rural women in Gujarat — have lower digital literacy and predominantly use basic feature phones. Voice access in Gujarati was the design response. The name "Sarlaben" was chosen deliberately to signal that this is a system built for the woman producer, in her language, on her terms. Sarlaben is reachable at 08035453545.

**Did you design the system to wait for users to come to it, or did it reach out to them too?**
The primary documented mode is inbound — farmers call Sarlaben with questions about their animals. The cooperative's data infrastructure enables proactive outbound as well: vaccination reminders specific to individual animals are documented as an active use case. Full proactive push capability mirroring MahaVistaar's 17-lakh-daily-alert model is planned for expansion.

---

## B — Architecture

*What you build with.*

**Did you need data sources that were controlled by other departments or organisations?**
Amul's primary data sources are internal to the cooperative — milk procurement records, cattle health records, veterinary records. This is a key structural difference from state government deployments, which required inter-institutional data access negotiations. Amul controlled its own data foundation. Government scheme data and veterinary advisory content (Standard Veterinary Treatment Manuals, NDDB materials) were accessed from external sources.

**Did you bring data together into one place or connect to it where it lived — and why?**
Connected to data where it lives. The same OAN principle applies: the AI connects to Amul's cooperative data infrastructure at the moment of query. Raw cooperative data stays in Amul's systems. The specific data architecture within Amul's cooperative infrastructure is not documented in detail in available sources.

**For each major component of your system — did you build it, buy it, or reuse something that existed?**
Sarlaben reused the OpenAgriNet DPG architecture and the MahaVistaar deployment playbook. The three-week deployment was possible because the architecture, governance frameworks, and deployment assets were already built. Amul adapted them to its cooperative context and data foundation — it did not rebuild them. The cooperative's own data infrastructure (50 years of records) was the unique asset Amul contributed.

**Did any data source or system integration turn out to be harder than expected?**
Not documented. The cooperative data foundation was well-structured, which likely reduced integration complexity compared to government deployments.

**Did vendor lock-in become a real constraint?**
Not documented. The OAN architecture applies — open source, open protocols, no single-vendor dependency.

**What was your design policy for handling peak load?**
Not documented for Sarlaben specifically. The OAN architecture's approach (capped concurrent connections with fallback) applies by inheritance.

**Did the AI produce wrong or harmful outputs that reached users?**
Not documented for Sarlaben specifically. The independent moderation layer architecture applies by inheritance from the OAN DPGs.

**Did data residency, sovereignty, or government policy on technology vendors constrain your architecture?**
Amul's cooperative data is privately held — different governance from state government data. Cooperative data ownership principles mean Amul members own their data. The privacy and consent architecture was adapted from the OAN framework to the cooperative context.

**If you used voice — did you face any problems such as latency, pronunciation, turn-taking and timing?**
Voice in Gujarati is the primary channel. Specific voice pipeline challenges for Gujarati are not documented. The general OAN voice infrastructure challenges (ASR accuracy, turn detection, latency) apply. Planned expansion to 20 Indian languages via Bhashini is documented.

**How frequently did the underlying data change, and how did you keep the AI current?**
Milk procurement records update with each collection cycle (typically twice daily). Cattle health and treatment records update when veterinary events occur. The real-time connection architecture means data currency is maintained without periodic model retraining.

**Did you hit any infrastructure constraint at scale that you didn't anticipate?**
Not documented. Three weeks from commitment to deployment of a system serving 3.6 million farmers at launch suggests infrastructure readiness was not a major constraint, given Amul's existing cooperative technology infrastructure.

### Additional Insights

The Amul deployment is the definitive proof of the "plus-one" velocity pattern documented in the Six Shifts framework. The sequence: start with Sarlaben advisory → add AI-based booking for artificial insemination (a plus-one on what already exists) → microcredit via the cooperative bank → Bharat Taxi via open network protocols. Each step builds on existing readiness. Never plus-ten. This pattern is transferable to any cooperative or institutional deployer with an existing member relationship and data foundation.

---

## C — Institution

*Who owns solving of the problem.*

**Was this deployment treated as a one-time project or as a long-term transformation initiative?**
Amul treated it as a long-term capability extension of the cooperative — not a standalone technology project. The reachability target (20 Indian languages via Bhashini, 20,000+ villages across 20 states) and the planned service extensions (AI booking for artificial insemination, microcredit, Bharat Taxi) indicate a transformation trajectory, not a one-time deployment.

**How did you get the deployment approved and funded?**
Amul is a private cooperative, not a government department — approval came through cooperative leadership rather than government procurement or budget allocation. The CEO's personal conviction (documented in the Six Shifts framework as experiential proof from seeing Amul's own data assembled by AI) was the key enabling factor.

**If the one or two people driving this deployment had moved to different roles mid-way, what would have happened?**
Not documented. The cooperative governance structure (board-level oversight, member ownership) provides different continuity mechanisms from government deployments.

**Which departments had to cooperate for this to work?**
Primarily internal cooperative functions: procurement, veterinary services, member relations, technology. External coordination with Bhashini (for language support) and OpenAgriNet (for DPG deployment). The simpler cooperation requirements — compared to state government deployments requiring 25+ external organisations — were a key enabler of the three-week deployment.

**Did procurement rules become a barrier?**
Not documented. Cooperative procurement processes are typically more agile than government procurement.

**Were there decisions that needed political support from above?**
The deployment was referenced by Prime Minister Modi at the India AI Impact Summit 2026. National-level political visibility was achieved, though it was not a prerequisite for the deployment itself.

**When something went wrong, who was accountable — and was that clear from the start?**
Not documented.

**Which institution did the AI speak on behalf of — and did that institution have credibility with your end users?**
Sarlaben speaks as Amul. The cooperative relationship — 50 years of daily milk procurement, built on mutual trust between Amul and its members — provides strong institutional credibility. The system name "Sarlaben" (a Gujarati woman's name, signalling a system built for women producers) adds a personalised trust dimension beyond the institutional brand.

---

## D — Ecosystem

*Who executes.*

**How many organisations had to work together for this to function?**
Significantly fewer than MahaVistaar's 54 enablers. Amul's cooperative data infrastructure is largely self-contained. Key external partners: OpenAgriNet/EkStep (DPG deployment), Bhashini (language support for Gujarati and planned expansion), Amul's existing veterinary partner network (1,200+ vets whose records feed the system). The overall ecosystem is smaller because Amul itself holds institutional, data, and member-relationship roles that required multiple separate organisations in state government deployments.

**Who was specifically responsible for keeping all partners aligned?**
Amul's cooperative management held the network operator role — "this runs in my name" was held by the Amul institution itself. EkStep Foundation provided technical deployment support.

**Were there partners whose commitment weakened over time?**
Not documented.

**Where did partners have conflicting priorities or mandates?**
Not documented.

---

## E — Workforce

*Who absorbs AI.*

**Were there people — field workers, extension officers, call centre staff — whose job changed?**
Amul's veterinary field network (1,400 doctors serving 3.6 million farmers) is the primary workforce affected. Sarlaben does not replace veterinary visits — it handles the first-line advisory queries that would otherwise require a veterinary contact or go unanswered. The vet's job shifts toward higher-complexity cases that AI cannot resolve.

**When the AI gave an answer or recommendation to a user, what was the last-mile human expected to do with it?**
Women producers are expected to act on feeding guidance, vaccination reminders, and early animal health assessments directly. For health questions, the expected escalation path is: Sarlaben advisory → if unresolved, contact the cooperative veterinary network. The system was designed to handle first-line advisory, not to replace veterinary judgment on complex cases.

**How and when were they brought in, and what did they need to learn?**
Not documented for the veterinary workforce specifically. Producers were not trained before access — the OAN pattern applies: use is training, beginning with simple queries and progressing to more complex interactions.

**Did you face resistance from staff?**
Not documented. The Six Shifts framework's observation that AI is particularly threatening to workers whose authority comes from discretion (extension officers in government contexts) applies less strongly to cooperative dairy producers, who are beneficiaries rather than gatekeepers.

**Did frontline staff become dependent on the system in a way that reduced their own capability?**
The Six Shifts framework documents both sides of this risk from the Amul deployment specifically. Younger family members gaining access to expert knowledge through Sarlaben is cited as the positive outcome (equaliser effect). The watchword from the same field: information alone is not the point; there is skill in the hand that counts for more than information in the head. AI should make the farmer's skill more precise, not replace it.

**How did problems or insights from the field reach the people improving the system?**
Not documented for Sarlaben specifically. The cooperative's direct relationship with 3.6 million members — through daily milk procurement interactions — provides a dense feedback channel that most government deployments lack.

---

## F — Operating Model

*What makes it last.*

**Who took ownership of steady state operations after the pilot?**
Amul holds the steady-state operation — this is not a pilot but a capability extension of an existing cooperative infrastructure. EkStep Foundation and the OpenAgriNet ecosystem provide ongoing technical support.

**What did it cost to build, and what does it cost to run annually?**
Three weeks of deployment time from an architecture that was already built. The marginal build cost for Amul — adapting an existing DPG to its cooperative context and data — was substantially lower than MahaVistaar's pioneer costs. Annual operating costs are not documented in available sources. The cooperative's existing technology infrastructure absorbs some of the running costs.

**Were there compliance, audit, or regulatory requirements that shaped how you ran operations?**
Cooperative data governance rules apply. India's DPDP Act applies to member data. Specific regulatory constraints not documented beyond the general OAN data sovereignty framework.

**How long did the deployment actually take versus what you planned?**
Three weeks from commitment to deployment — the fastest documented on the OAN pathway as of March 2026. The compression was possible because the architecture, governance frameworks, and deployment playbooks had already been built by MahaVistaar.

**Was there a point where the whole thing nearly stalled — and what got it through?**
Not documented. The three-week timeline suggests no major stall.

**What did you measure to know the solution was working?**
At launch: 3.6 million farmers reached; 1 million+ app downloads; voice access in Gujarati for feature phone and landline users; personalised animal-specific advisory operational. Specific quality or outcome metrics beyond these are not documented in available sources.

**Did you do a big launch or sequence through small pilots?**
Launched at full cooperative scale (3.6 million members) rather than through a geographic pilot — enabled by the three-week setup on an already-proven architecture and the cooperative's existing member relationships. The subsequent service expansions (AI booking for insemination, microcredit, Bharat Taxi) follow the plus-one sequencing pattern.

---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| Plus-one service extension sequence | Deployment pattern | How to grow a cooperative AI deployment beyond advisory — each step a single addition to what already exists | Documented in Six Shifts framework (F1 velocity) |
| Cooperative data architecture pattern | Architecture template | How to connect 50 years of transaction data to AI advisory without centralising or exposing raw records | Via EkStep Foundation / OpenAgriNet |
| "Sarlaben" naming and trust design | Brand/trust pattern | How to signal institutional identity and user-centricity through naming and voice persona | Not formally documented; contact EkStep Foundation |
| OpenAgriNet DPGs adapted for cooperative context | Code / DPG | Three-week deployment foundation for cooperatives with existing data infrastructure | openagri.net |

---

## Related Pathways

- [MahaVistaar](mahavistaar.md) — source of the architecture, governance frameworks, and deployment playbook reused by Amul
- [Bharat-VISTAAR](bharat-vistaar.md) — national layer to which Amul Sarlaben connects as a node
- [Bihar Krishi](bihar-krishi.md) — parallel state deployment; different institutional type, same framework
- [Ethiopia ATI](ethiopia-ati.md) — international deployment that also drew on these assets

## Related Entities

- [Amul](../entities/amul.md)
- [EkStep Foundation](../entities/ekstep-foundation.md)
- [OpenAgriNet](../entities/openagri-net.md)

## Lineage

Built on [MahaVistaar](mahavistaar.md) — architecture, governance frameworks, language pipeline methodology, data connector approach, model evaluation benchmarks, and failure mode library all inherited. Amul contributed the cooperative data foundation and adapted the deployment to a cooperative institutional context in three weeks.
