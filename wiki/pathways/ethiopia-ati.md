# Ethiopia ATI — Pathway

**Deployment:** Ethiopia ATI Agricultural Advisory System
**Contributor:** Agricultural Transformation Institute (ATI), Ethiopia / EkStep Foundation
**Sector:** Agriculture
**Geography:** Ethiopia
**Actor type:** Government
**Journey stage:** Pilot
**Dimensions covered:** A, B, C, D
**Horizontal or vertical:** Vertical (sector-specific)
**Deployment status:** Active
**Last updated:** 2026-05-28
**Contact for peer connection:** EkStep Foundation — via OpenAgriNet

## Summary

The Ethiopia ATI deployment is the first international extension of the OpenAgriNet (OAN) DPG architecture outside India, deployed by Ethiopia's Agricultural Transformation Institute in Amharic. It integrates with Fayda, Ethiopia's national digital identity system, and demonstrates that the OAN DPG layer can be localised for a new language, country-specific crops, and a different national DPI foundation. For a next adopter working in Africa or in a context with a national digital ID system, this pathway documents what cross-border DPG portability looks like in practice and what configuration work is required.

---

## A — Problem Orientation

*What you build on.*

**Who were you trying to serve, and what specific problem were you solving for them?**
Ethiopian smallholder farmers, served through Ethiopia's ATI extension network. The problem framing parallels India: farmers need personalised advisory on crops, pests, weather, and market prices at a cadence and scale the human extension network cannot deliver alone.

**What were the access constraints of your users — language, literacy, connectivity — and how did that shape what you built?**
Amharic language, voice-first interface. Ethiopia's rural connectivity context — lower smartphone penetration than urban India — reinforces the voice-telephony-first access approach. The Amharic language configuration required sourcing or building Amharic ASR/TTS capability; whether through Bhashini's multilingual models or Ethiopia-specific development is not documented.

**Was there data already available to start with, or did you have to build or collect it first?**
ATI holds Ethiopian agricultural research data. Integration with Fayda (national digital ID) suggests that farmer identity and potentially land or crop registration data could be linked to advisory sessions. The extent of data integration at launch is not documented.

**Why did this problem need AI — what would a non-AI solution have missed?**
Same rationale as the Indian deployments: extension network capacity cannot match 24/7 personalised advisory demand. AI enables scale without proportionally scaling the human workforce.

**Did your understanding of the problem change after you started — and if so, how?**
Not documented.

**Is there anything about your users you assumed early on that turned out to be wrong?**
Not documented.

---

## B — Architecture

*What you build with.*

**Did users interact through voice, an app, or something else — and what drove that choice?**
Voice interface in Amharic, delivered via telephony. Consistent with OAN's voice-first design for low-connectivity, low-literacy users.

**Did you bring data together into one place or connect to it where it lived — and why?**
Federated architecture inherited from the OAN DPG layer. Integration with Fayda (national digital ID) represents a new data integration point not present in India deployments — farmer identity verified through national ID rather than cooperative membership or state land records.

**What did you build yourself versus use something that already existed?**
OAN DPG layer reused. What was built new: Amharic language configuration, Ethiopian crop and climate knowledge base, Fayda digital ID integration, and alignment with Ethiopia's national DPI foundation rather than India's (India-specific components such as Beckn and Bhashini have Ethiopia equivalents or require replacement). The cross-border portability test is whether the DPG layer separates cleanly from the DPI foundation layer beneath it — the Ethiopia deployment is evidence that it does.

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
The Agricultural Transformation Institute is Ethiopia's designated government body for agricultural modernisation, giving the deployment a direct institutional mandate. Funding sources are not documented.

**Was there internal resistance — and if so, what actually changed minds?**
Not documented.

**Did you need multiple departments or agencies to cooperate — and where did that get difficult?**
The Fayda digital ID integration requires cooperation with Ethiopia's national ID authority, not just the agriculture ministry. This cross-ministry coordination is required for the identity integration but details are not documented.

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
ATI, EkStep Foundation (OAN DPG layer), Fayda national ID authority, Amharic language technology partners, and Ethiopian agricultural knowledge institutions. The international deployment adds a cross-border coordination layer between EkStep (India-based OAN orchestrator) and Ethiopian institutional partners.

**Who was ultimately responsible for keeping all of them aligned — and what did that role actually involve?**
EkStep Foundation for the OAN technology layer; ATI for Ethiopian institutional coordination.

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
Not documented.

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
| Fayda integration pattern | Architecture pattern | Integrating a national digital ID system into agricultural advisory; applicable to any African deployment with a national ID infrastructure | Via EkStep Foundation / Ethiopian ATI |

---

## Related Pathways

- [MahaVistaar](mahavistaar.md) — Source deployment; OAN DPG layer and architecture origin
- [Amul Sarlaben](amul-sarlaben.md) — Similar rapid deployment using OAN DPG reuse

## Related Entities

- [Ethiopian ATI](../entities/ethiopian-ati.md)
- [EkStep Foundation](../entities/ekstep-foundation.md)
- [OpenAgriNet](../entities/openagri-net.md)

## Lineage

Built on [MahaVistaar](mahavistaar.md) — OAN DPG layer reused; Amharic language, Ethiopian crop and climate knowledge, and Fayda digital ID integration added. First international OAN deployment.
