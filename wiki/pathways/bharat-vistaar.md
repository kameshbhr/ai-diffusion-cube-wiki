# Bharat-VISTAAR — Pathway

**Deployment:** Bharat-VISTAAR National Agricultural Advisory System
**Contributor:** ICAR (Indian Council of Agricultural Research) / EkStep Foundation
**Sector:** Agriculture
**Geography:** India (national)
**Actor type:** Government
**Journey stage:** Pilot
**Dimensions covered:** A, B, C, D
**Horizontal or vertical:** Vertical (sector-specific)
**Deployment status:** Active
**Last updated:** 2026-05-28
**Contact for peer connection:** EkStep Foundation — via OpenAgriNet

## Summary

Bharat-VISTAAR is the national-layer agricultural advisory system, deployed by ICAR (Indian Council of Agricultural Research) under the Government of India, serving farmers across India through a toll-free voice channel (short code 155261) in Hindi and English. Built on the OAN DPG layer developed for MahaVistaar, it scales the OAN model from state to national level. For a next adopter, this pathway demonstrates how a national-level government research institution can become an AI advisory deployer and how national knowledge repositories (ICAR's research data) can be integrated into a conversational AI system.

---

## A — Problem Orientation

*What you build on.*

**Who were you trying to serve, and what specific problem were you solving for them?**
Farmers across India who need access to agricultural advisory grounded in ICAR's research and extension knowledge. ICAR is India's apex agricultural research body, holding extensive crop, pest, and soil knowledge that has historically been difficult for farmers to access in a form relevant to their specific situation.

**What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?**
Hindi and English voice interface via telephony (short code 155261). A national deployment must eventually cover multiple Indian languages; the initial launch covers Hindi and English, with additional languages expected as the OAN language configuration model scales across states and languages.

**Was there data already available to start with, or did you have to build or collect it first?**
ICAR holds India's most comprehensive agricultural research data — crop variety information, pest identification keys, soil health data, and climate-crop interaction models. This is the primary knowledge asset that distinguishes Bharat-VISTAAR from state deployments; state systems typically have state-specific data but less depth in research knowledge.

**Why did this problem need AI — what would a non-AI solution have missed?**
ICAR's knowledge has historically been locked in research publications and extension manuals that farmers cannot easily access or apply to their specific situation. AI makes that knowledge conversational — farmers can ask questions about their specific crop, location, and problem and receive responses grounded in ICAR research.

**Did your understanding of the problem change after you started — and if so, how?**
Not documented.

**Is there anything about your users you assumed early on that turned out to be wrong?**
Not documented.

---

## B — Architecture

*What you build with.*

**Did users interact through voice, an app, or something else — and what drove that choice?**
Voice telephony via short code 155261, Hindi and English. Same access rationale as MahaVistaar.

**Did you bring data together into one place or connect to it where it lived — and why?**
Federated architecture from the OAN DPG layer. ICAR's data infrastructure remains under ICAR's control.

**What did you build yourself versus use something that already existed?**
OAN DPG layer reused from MahaVistaar. What was added: Hindi and English language configuration, ICAR knowledge integration (crop research, pest databases, soil data), national scheme information, and ICAR-specific advisory guardrails.

**How did you avoid being locked into a single vendor?**
Inherited OAN vendor-independence architecture.

**Did any data source or system integration turn out to be harder than expected?**
Not documented.

**Did the AI ever give a wrong or harmful answer to a user — and how did you catch and handle it?**
Not documented.

**What did you put in place to prevent the AI from causing harm — and was it ever tested?**
Inherited safeguard architecture from the OAN DPG layer.

---

## C — Institution

*Who deploys AI.*

**How did you get the deployment approved and funded — and did you position it as a one-time project or a long-term transformation initiative?**
ICAR as the deploying institution brings national government authority and the credibility of India's apex agricultural research institution. Funding and approval specifics are not documented.

**Was there internal resistance — and if so, what actually changed minds?**
Not documented.

**Did you need multiple departments or agencies to cooperate — and where did that get difficult?**
A national deployment requires coordination with state agriculture departments for last-mile delivery and with ICAR's own research divisions for knowledge access. The intersection between national-level ICAR knowledge and state-specific conditions (which vary significantly across India's 28 states) is a coordination challenge that is not yet documented in available sources.

**Did procurement rules create a barrier — and if so how did you get through them?**
Not documented.

**When something went wrong, who was accountable — and was that clear from the start?**
Not documented.

**What happens to this deployment if the key person driving it moves to a different role?**
Not documented.

**Was there a leadership or political change during the deployment, and how did it affect things?**
Not documented.

---

## D — Ecosystem

*Who executes.*

**How many organisations had to work together for this to function?**
ICAR, EkStep Foundation, Bhashini/AI4Bharat for language services, and state agriculture departments for contextualisation. The national scope means the ecosystem is broader than a state deployment, but the OAN DPG layer reduces the technology coordination burden.

**Who was ultimately responsible for keeping all of them aligned — and what did that role actually involve?**
EkStep Foundation as OAN network orchestrator for the technology layer; ICAR for knowledge governance and national institutional relationships.

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
Not documented separately from OAN infrastructure costs.

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
| ICAR knowledge integration | Knowledge configuration | Access to India's apex agricultural research within an advisory system; template for national research institution integration | Via ICAR |

---

## Related Pathways

- [MahaVistaar](mahavistaar.md) — State-level anchor deployment; OAN DPG layer source
- [Bihar Krishi](bihar-krishi.md) — Parallel state deployment; independent (non-OAN) comparison case
- [Ethiopia ATI](ethiopia-ati.md) — International OAN extension

## Related Entities

- [EkStep Foundation](../entities/ekstep-foundation.md)
- [OpenAgriNet](../entities/openagri-net.md)

## Lineage

Built on [MahaVistaar](mahavistaar.md) — OAN DPG layer reused; ICAR knowledge integration and national-scale language configuration added.
