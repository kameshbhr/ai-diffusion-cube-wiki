# Amul Sarlaben — Pathway

**Deployment:** Amul Sarlaben Dairy Advisory System
**Contributor:** GCMMF (Amul) / EkStep Foundation
**Sector:** Agriculture (Dairy)
**Geography:** Gujarat, India
**Actor type:** Cooperative
**Journey stage:** Scaling
**Dimensions covered:** A, B, C, D
**Horizontal or vertical:** Vertical (sector-specific)
**Deployment status:** Active
**Last updated:** 2026-05-28
**Contact for peer connection:** EkStep Foundation — via OpenAgriNet

## Summary

Sarlaben is an AI-powered dairy advisory system deployed by GCMMF (Amul), India's largest dairy cooperative, serving Gujarat's dairy farmers through a voice channel (08035453545) in Gujarati. Built on the OAN DPG layer originally developed for MahaVistaar, Sarlaben was deployed in three weeks — demonstrating how subsequent deployments can reuse the foundational architecture rather than rebuilding it. For a next adopter, this pathway shows how the OAN DPG layer compresses deployment timelines, and what changes when the deployer is a cooperative rather than a government department.

---

## A — Problem Orientation

*What you build on.*

**Who were you trying to serve, and what specific problem were you solving for them?**
Gujarat's dairy farmers — members of the Amul cooperative network — who need timely advice on animal health, feed management, milk yield optimisation, and Amul scheme access. The cooperative relationship (farmer as member-owner) creates a different trust dynamic than a government advisory line: farmers already have a pre-existing relationship with Amul and trust Amul communications.

**What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?**
Gujarati language, voice-first telephony interface. The same access rationale as MahaVistaar: voice over basic telephony reaches farmers regardless of smartphone or data plan access.

**Was there data already available to start with, or did you have to build or collect it first?**
Amul holds substantial data on its member farmers — milk procurement records, animal health visits, scheme participation. Whether this data was integrated into the advisory system at launch is not documented. The OAN federated architecture allows connection to Amul's existing data infrastructure without migration.

**Why did this problem need AI — what would a non-AI solution have missed?**
The cooperative's veterinary and advisory extension network cannot deliver personalised advice to every farmer at the cadence dairy farming requires — animal health issues can move fast. AI enables 24/7 advisory at scale without proportionally scaling the human workforce.

**Did your understanding of the problem change after you started — and if so, how?**
Not documented.

**Is there anything about your users you assumed early on that turned out to be wrong?**
Not documented.

---

## B — Architecture

*What you build with.*

**Did users interact through voice, an app, or something else — and what drove that choice?**
Voice telephony, short number 08035453545, Gujarati. Same rationale as MahaVistaar: voice-first for access reach.

**Did you bring data together into one place or connect to it where it lived — and why?**
Federated architecture inherited from the OAN DPG layer. Data connects at query time rather than migrating to a central store.

**What did you build yourself versus use something that already existed?**
The OAN DPG layer was reused wholesale from MahaVistaar — this is what enabled the 3-week deployment. What was built new: the Gujarati language configuration, dairy domain knowledge and advisory content (cattle breeds, feed regimes, milk yield, animal health), and Amul-specific scheme and product information. The 3-week timeline demonstrates that the DPG layer covers the majority of build effort, and new deployments need only configure the deployment-specific layer.

**How did you avoid being locked into a single vendor?**
Inherited OAN vendor-independence architecture — DPG layer separated from instance configuration, Beckn protocol for ecosystem interoperability.

**Did any data source or system integration turn out to be harder than expected?**
Not documented.

**Did the AI ever give a wrong or harmful answer to a user — and how did you catch and handle it?**
Not documented.

**What did you put in place to prevent the AI from causing harm — and was it ever tested?**
Inherited safeguard model architecture from the OAN DPG layer (independent GPT-OSS Safeguard 20B moderation). Deployment-specific testing is not documented.

---

## C — Institution

*Who deploys AI.*

**How did you get the deployment approved and funded — and did you position it as a one-time project or a long-term transformation initiative?**
GCMMF (Amul) as a cooperative is the deployer. The cooperative structure provides an institutional advantage over government deployment: procurement, approval, and funding cycles are compressed because Amul is not subject to government procurement rules. The deployment is positioned as a member service enhancement rather than a time-bound project.

**Was there internal resistance — and if so, what actually changed minds?**
Not documented.

**Did you need multiple departments or agencies to cooperate — and where did that get difficult?**
The cooperative model simplifies this significantly — Amul owns the member relationship, the data, and the delivery channel. The cross-departmental coordination required in government deployments is largely absent.

**Did procurement rules create a barrier — and if so how did you get through them?**
Not applicable — cooperative procurement is faster than government procurement. The absence of government procurement rules is documented as a structural advantage of the cooperative deployer model.

**When something went wrong, who was accountable — and was that clear from the start?**
Not documented.

**What happens to this deployment if the key person driving it moves to a different role?**
Not documented.

**Was there a leadership or political change during the deployment, and how did it affect things?**
Not applicable for a cooperative.

---

## D — Ecosystem

*Who executes.*

**How many organisations had to work together for this to function?**
The ecosystem is smaller than MahaVistaar because Amul controls end-to-end: cooperative network, farmer relationships, data, and funding channel. The OAN technology ecosystem (EkStep Foundation, Bhashini/AI4Bharat, vLLM serving) provides the technology layer.

**Who was ultimately responsible for keeping all of them aligned — and what did that role actually involve?**
EkStep Foundation as OAN network orchestrator for the technology layer; Amul/GCMMF for the cooperative-facing elements.

**Did any partner relationship not work out as expected — what happened and how did you handle it?**
Not documented.

**How was trust maintained across partners — especially when something went wrong?**
Not documented.

---

## E — Workforce

*Who absorbs AI.*

**Were there people — field workers, extension officers, call centre staff — whose job changed because of this deployment?**
Not documented.

**How and when were they brought in, and what did they need to learn?**
Not documented.

**Was there resistance from staff — and if so what worked to address it?**
Not documented.

**After the deployment, could staff still do their job if the system was unavailable — or had they become dependent on it?**
Not documented.

---

## F — Operating Model

*What makes it last.*

**What did this cost to build, and what does it cost to run annually?**
Build cost was dramatically compressed by OAN DPG reuse — the 3-week deployment is the headline evidence for this. Ongoing running cost is not documented separately from OAN infrastructure costs.

**What did you measure to know it was working — and what did the numbers actually show?**
Not documented.

**Who owned operations after the pilot ended, and how was that handover structured?**
Not documented.

**Was there an outcome or a problem that showed up later that you wished you had been measuring from the start?**
Not documented.

**Was there a point where the whole thing nearly stalled — and what got it through?**
Not documented.

**Were there compliance, audit, or regulatory requirements that shaped how you ran operations?**
Not documented.

---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| OAN DPG layer (reused) | Open-source codebase | See [MahaVistaar](mahavistaar.md) for full description | Via EkStep Foundation |
| Dairy domain configuration | Knowledge configuration | Gujarati dairy advisory content; starting template for dairy deployments in other geographies | Via EkStep Foundation / Amul |

---

## Related Pathways

- [MahaVistaar](mahavistaar.md) — Source deployment; OAN DPG layer originated here
- [Bharat-VISTAAR](bharat-vistaar.md) — National layer; different deployer type (government research institution)
- [Ethiopia ATI](ethiopia-ati.md) — International OAN deployment; similar rapid deployment using DPG reuse

## Related Entities

- [Amul (GCMMF)](../entities/amul.md)
- [EkStep Foundation](../entities/ekstep-foundation.md)
- [OpenAgriNet](../entities/openagri-net.md)

## Lineage

Built on [MahaVistaar](mahavistaar.md) — OAN DPG layer reused in full; dairy domain knowledge and Gujarati language configuration added; deployed in 3 weeks versus the original MahaVistaar build timeline.
