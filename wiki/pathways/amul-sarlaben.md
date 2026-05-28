# Amul Sarlaben — Pathway

**Deployment:** Amul Sarlaben (AI-powered veterinary and dairy advisory for milk producers)
**Contributor:** Amul (Gujarat Cooperative Milk Marketing Federation)
**Sector:** Livelihoods / Agriculture
**Geography:** India — Gujarat state, 18,500+ villages
**Actor type:** Cooperative
**Journey stage:** Scaling
**Dimensions covered:** A, B, D, E, F
**Horizontal or vertical:** Vertical (dairy cooperative sector)
**Deployment status:** Active
**Last updated:** 2026-05-28

## Summary

Amul Sarlaben is an AI-powered voice and app advisory system serving 3.6 million milk producers across 18,500+ villages in Gujarat — the majority of them women. It addresses the fundamental structural gap in veterinary access: 1,400 vets for 3.6 million farmers and 22 million cattle. By providing 24/7 voice-based advisory at scale, it effectively extends veterinary reach without requiring new vet hiring. With 1 million+ app downloads and grounding in 2 billion transactions and 30 million cattle health records, it is the best-evidenced example in this wiki of a cooperative-sector AI deployment.

---

## A — Problem Orientation

*What you build on.*

The problem being solved is veterinary access scarcity in a large-scale dairy cooperative. 🟡 Amul's Gujarat network spans 3.6 million milk producers across 18,500+ villages, but the veterinary infrastructure serving them was 1,400 vets — a ratio of approximately 1 vet per 2,571 farmers, and 1 vet per 15,714 cattle. When a cow falls ill, a farmer who cannot reach a vet quickly loses income directly; for the roughly 3.5 crore litres of milk processed daily through the Amul system, delayed veterinary response has supply-chain consequences. 🟡

The users are predominantly women milk producers — smallholders for whom the primary barrier is not willingness to engage with technology but availability of a channel that works in their language, at any hour, without requiring literacy or smartphone navigation. 🟡 The voice short code 08035453545 reflects this constraint: the entry point must work on a basic mobile phone. The app (1 million+ downloads) serves users who are more digitally comfortable.

The data advantage at deployment was substantial. 🟡 Amul holds 2 billion transactions and 30 million cattle records — a cattle health dataset of exceptional depth. This meant that the AI system could be grounded in actual Amul cattle data rather than generic veterinary knowledge, which is likely a significant driver of both accuracy and farmer trust. Whether this data had to be restructured or cleaned before it could serve as an AI knowledge base is not documented.

Why this problem needed AI rather than a non-AI solution: the ratio problem is structural and cannot be solved by hiring alone. Amul's geography (18,500+ villages across Gujarat) makes physical veterinary coverage economically impossible at current margins. 🟡 AI-enabled triage and advice can handle the large volume of routine queries (nutrition, common illness symptoms, reproductive management) and reserve the physical vet for cases requiring hands-on intervention.

Whether the deployment team's understanding of the problem changed after launch, and whether any early assumptions about users proved wrong, is not documented.

---

## B — Architecture

*What you build with.*

The deployment uses a dual-channel architecture: a voice short code (08035453545) and a dedicated app. 🟡 The underlying AI system is grounded in Amul's 2 billion transaction records and 30 million cattle health records — making the knowledge base cooperative-owned rather than externally sourced. This is a significant architecture decision: the AI is answering from Amul's own longitudinal cattle data, not from generic veterinary literature, which provides both accuracy and institutional trust grounding. 🟡

The specific AI model(s) used, whether the system is hosted on Amul's own infrastructure or a cloud provider, whether there is a moderation layer, and how the system handles queries outside its competence (escalation to a human vet) are not documented in available sources.

Whether the system experienced a harmful or incorrect answer reaching a farmer, and how that was caught and handled, is not documented.

How vendor independence was maintained — whether Amul is locked into a specific AI provider — is not documented.

---

## C — Institution

*Who deploys AI.*

Amul is the deploying institution — a cooperative structure in which the 3.6 million milk producers are nominally the owners. This cooperative structure has implications for accountability and sustainability that differ from both government deployments and market deployments: Amul is accountable to its producer-members, has a long track record of institutional continuity, and has economic alignment between the platform's success (healthier cattle, higher milk yield) and its financial sustainability. 🟡

How the deployment was approved and funded within Amul's governance structure — whether it required board approval, what the investment case was — is not documented.

Whether there was resistance within Amul's veterinary or extension staff who saw the AI as a threat to their role is not documented.

---

## D — Ecosystem

*Who executes.*

The core execution ecosystem is Amul's own cooperative structure — the 18,500+ village-level societies, the district unions, and the central federation. 🟡 Amul's existing infrastructure (milk collection routes, village society networks, the physical points of contact between Amul staff and farmers) provides a distribution channel that most deployments have to build or borrow.

Who the technology partner was for the AI system — who built the voice AI and the app — is not documented. Whether external AI specialists, telecom partners for the short code, or content developers for veterinary knowledge were involved, and how those relationships are structured, is not documented.

---

## E — Workforce

*Who absorbs AI.*

The workforce most affected by this deployment is Amul's network of field veterinarians and the village-level society staff who have regular contact with milk producers. 🟡 The deployment effectively changes the nature of the vet's role: instead of handling every query directly, vets handle cases that the AI triage layer has identified as requiring physical intervention. Whether this role change was addressed as part of the deployment — whether vets were trained on how to work alongside the system rather than being bypassed by it — is not documented.

The end users (milk producers, predominantly women) are the other workforce absorbing this deployment. Their adoption is evidenced by 1 million+ app downloads and the use of the voice short code. Whether there was a structured onboarding or training program for producers, or whether they adopted through peer demonstration and word of mouth, is not documented.

Whether field staff can still do their job if the system goes down — whether dependency has been created — is not documented.

---

## F — Operating Model

*What makes it last.*

The economic sustainability of Amul Sarlaben has an inherent logic that distinguishes it from government deployments: if the AI improves cattle health and milk yield, it directly improves Amul's supply and producer income, creating a financial case for continued investment without requiring external grant funding. 🟡 The actual cost to build and the annual operating cost are not documented.

What Amul measures to know the deployment is working — whether there are outcome metrics on cattle health improvement, mortality reduction, or producer income change — is not documented. The deployment metrics cited (1 million+ app downloads, 2 billion transactions as grounding data) are inputs and reach metrics, not outcome metrics.

Who owns operations, how governance is structured, and what the handover from initial deployment to steady-state operations looked like is not documented.

Whether there was a near-stall moment in the deployment, and what got it through, is not documented.

---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| Voice short-code advisory pattern | Architecture pattern | Designing 24/7 advisory for low-literacy, voice-first users at cooperative scale | Documented in OAN-DiffusionPathway.pdf (raw/) |
| Cooperative-owned longitudinal data as AI knowledge base | Architecture decision | Grounding AI in institution's own records rather than external sources — improves accuracy and trust | Documented in OAN-DiffusionPathway.pdf (raw/) |

---

## Related Pathways

- [MahaVistaar](mahavistaar.md) — government-sector parallel: voice-first agricultural AI, different institutional structure
- [Bihar Krishi](bihar-krishi.md) — comparable rural advisory deployment, state government actor

## Related Entities

- [Amul](../entities/amul.md) — deploying institution and data custodian

## Lineage

Not documented.
