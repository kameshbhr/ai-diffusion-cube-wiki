---
type: pathway
deployment: blue-dots-dharwad, blue-dots-ghaziabad
dimensions: [problem-orientation, architecture, ecosystem, operating-model]
sector: livelihoods
geography: India (Dharwad, Karnataka; Ghaziabad, Uttar Pradesh)
contributor: ai-diffusion-pathways
contributed: 2026-05-21
last-updated: 2026-05-21
times-referenced: 0
---

# Local Discovery Infrastructure

**One-line summary:** How to build shared digital rails that make a digitally dark district economy visible to itself — dissolving the paradox of proximity without waiting for new resources, skills, or investment.

**Deployment source:** [Blue Dots AI — Dharwad](../deployments/blue-dots-dharwad.md) (pioneer, 10 months) and [Blue Dots AI — Ghaziabad](../deployments/blue-dots-ghaziabad.md) (second district, 4 months)
**Contributor:** Tushar Bansal — [AI Diffusion Pathways / EkStep Foundation](../people-orgs/ai-diffusion-pathways.md)
**Contributed:** 2026-05-21
**Last updated:** 2026-05-21
**Times referenced:** 0

---

## Context

You are a district collector, CDO, state programme director, or funder looking at a district where the economy is underperforming. The instinct is to look for what is missing: not enough jobs, inadequate skills, too little investment. In many Indian districts — and by extension many districts in similar economies globally — this diagnosis is wrong.

The jobs are there. The talent is there. The services and schemes are there. What does not exist is a shared digital surface where they can find each other. Most district economic activity — SMBs, local talent, service providers, scheme-eligible citizens — is invisible on any digital map. National platforms were built for digitally fluent users; they do not reach the long tail. Physical mechanisms (job fairs, field surveys) cost ₹500+ per interaction and yield below 10% placement. 🟡

This is not a resource failure. It is a local discovery failure. And a local discovery failure is solved by discovery infrastructure — not by more training programmes or more investment.

The signal that this pathway is relevant to your context: you are looking at a district where SMB density is real (or growing), where skilling investment has not moved placement rates, and where the same population that "cannot find jobs" and the employers who "cannot find talent" are within 2–5 km of each other.

Dharwad (Karnataka, India) went from decision to self-sustaining ecosystem in 10 months. Ghaziabad (Uttar Pradesh, India) reached meaningful activation in 4 months, learning from Dharwad. Both are the reference implementations for this pathway. 🟡

---

## Shift map

| Shift | Summary | Documented? |
|---|---|---|
| A1 Problem framing | FROM: "jobs crisis / skills gap" requiring new investment. TO: local discovery failure requiring shared infrastructure. The district already has what it needs — it cannot see it. | ✓ 🟡 |
| A2 Data posture | The long tail of district participants has no prior digital presence; data is created fresh by participants via consent-based voice interaction, not drawn from existing institutional datasets. | Partial ⬜ |
| A3 Existing assets | Existing institutions (ITIs, MSME associations, NGOs) are the critical existing asset — not as data holders but as trust relationships with the long tail. The task is to find them, not build them. | ✓ 🟡 |
| A4 Proof mechanism | 10,000+ local job openings visible from <10% SMB coverage in under 60 days (Ghaziabad); placement conversion below 10% at job fairs → above 50% in targeted drives; self-sustaining ecosystem in 10 months (Dharwad). | ✓ 🟡 |
| B1 Model choice | Open-source voice AI assembled from AI Diffusion DPGs (7 building blocks: Knowledge Engine, Memory Layer, Trust Layer, Agent Core, Action Gateway, Reach Layer, Learning Layer). Unbundled — works with any speech recognition models and LLMs. | ✓ 🟡 |
| B2 Data sovereignty | Participant-owned: each person or organisation owns their Blue Dot. Can update, pause, or delete. State operator and district administration are data fiduciaries — accountable for lawful processing, not owners of the data. DPDP 2023 compliant by architecture. | ✓ 🟡 |
| B3 Vendor independence | Open-source DPGs; no lock-in to any speech model, LLM, or platform vendor. Any government department or startup can assemble and adapt. | ✓ 🟡 |
| B4 DPG vs instance | Four DPGs deployed: Signal DPG (manages Blue Dot signals, matching, connection flows), Aggregator DPG (mass onboarding and participant tracking), Facilitator DPG (district-level supply-demand monitoring), AI Diffusion DPGs (voice AI foundational layer). All open-source. | ✓ 🟡 |
| C1 Framing | Framed as discovery infrastructure problem, not a technology project. District Champion's first act: frame this as local discovery failure, not a government IT initiative. Without this reframe, the ecosystem has no spine. | ✓ 🟡 |
| C2 Resistance | Not documented in source. | ✗ |
| C3 Institutional knowledge | Not documented in source. | ✗ |
| D1 Ecosystem design | Four reinforcing actor groups: District Facilitation Team (6–8 people, rhythm keeper), Ecosystem Aggregators (ITIs, MSME associations, NGOs — mass onboarders), Innovators (staffing firms, assessment providers, skilling orgs, startups), Funder/Sponsor (funds cold start). All four are necessary; none is sufficient alone. | ✓ 🟡 |
| D2 Trust source | District Champion (DC/CDO) as the named individual whose endorsement makes the ecosystem credible to aggregators and participants. State sponsor provides political cover and budget. | ✓ 🟡 |
| D3 Coordination mechanism | Sequential activation: District Champion → State Sponsor → Funder → Facilitation Team → Aggregators → Participants → Innovators. Each actor's engagement unlocks the next. Sequence matters; simultaneous launch does not work. | ✓ 🟡 |
| D4 Network operator | District Champion says "this runs in my name" — naming test. District Facilitation Team maintains weekly rhythm. Both functions are necessary; neither substitutes for the other. | ✓ 🟡 |
| E1 Training timing | Not documented in source. | ✗ |
| E2 Training depth | Not documented in source. | ✗ |
| E3 Agency test | Not documented in source. | ✗ |
| F1 Velocity | DPG tech setup in 2 weeks once information collated. Full ecosystem: Dharwad 10 months (pioneer, built while learning); Ghaziabad 4 months (inheriting DPGs + playbook). Further compression expected for subsequent districts. | ✓ 🟡 |
| F2 Governance | District Facilitation Team structure described operationally (6–8 people; mix of government credibility, community trust, operational discipline). Decision-authority governance not documented. | Partial ⬜ |
| F3 Sustainability | Government funds 12-month cold start: facilitation team salaries, voice AI setup, aggregator mobilisation. Once density threshold reached and innovators active, ecosystem self-funds. In Dharwad and Ghaziabad, threshold reached within 3 months of aggregator mobilisation. | ✓ 🟡 |
| F4 Pilot to deployment | Not documented in source. Both Dharwad and Ghaziabad described as reaching meaningful activation, not as transitioning from pilot to deployment in the formal sense. | ✗ |

---

## Playbook

### What was done and why

The Blue Dots AI approach activates four reinforcing levers in a specific sequence. Each is necessary. None is sufficient alone. Remove any one and the system reverts to the discovery patterns it was designed to replace.

**Lever 1: Shared digital rails (voice AI)**

The first decision was architectural: build for the person with the least access. A 2–3 minute voice call on any phone in any language is enough to become a Blue Dot — a precise, location-anchored signal on a shared district map. No smartphone, no literacy, no English, no form required.

The AI does not just record the signal. It structures it (extracting skills, location, availability, requirements), anchors it to a district map, and keeps working: nudging seekers when a match appears nearby, prompting SMBs when relevant candidates surface, synthesising patterns into live intelligence for administrators and innovators.

The rails are open-source (built on AI Diffusion DPGs) and not controlled by any single actor. Any government department, NGO, or startup can deploy a use case — livelihoods, welfare, agriculture, tourism — without building separate systems.

**Lever 2: Ecosystem aggregators (mass onboarding)**

Building a two-sided marketplace person by person is too slow and never reaches the density at which matching becomes reliable. The second decision was to use existing institutions with long-tail relationships as mass onboarders.

One ITI with 500 enrolled students becomes 500 seeker-side Blue Dots in days. One MSME association with 300 member businesses becomes 300 employer-side Blue Dots in two weeks. The aggregator leverages existing trust; the task is not to build new relationships but to find institutions that already have them.

For livelihoods: minimum viable pairing is one seeker-side aggregator (ITI, college, NGO with youth population) and one provider-side aggregator (MSME association, employer network). These two alone are sufficient to establish density.

**Lever 3: District Facilitation Team (rhythm keeper)**

A live map requires a live rhythm. The District Facilitation Team — 6–8 people drawn from government, the social sector, and MSME associations — is not a technology team. It is a convening and coordination team.

It sets up the voice bot; identifies and onboards first aggregators; maintains weekly discovery rhythm; tracks which Blue Dots are going cold and prompts intervention; monitors supply-demand gaps and brings new use cases or aggregators in as needed.

Without this function, Blue Dots go stale. Both sides lose confidence. The map becomes a dormant database. The institutional anchor for this team is the district administration; the state-level sponsor provides political cover and makes it real to other actors.

**Lever 4: Innovators on the shared rails**

Once density is sufficient, private actors — staffing firms, assessment providers, skilling organisations, startups — plug into the shared map because it makes their own operations more efficient. District-level blue/grey collar markets have historically not attracted private investment because finding and qualifying candidates was too expensive and conversion too unpredictable.

Blue Dots AI changes the unit economics: shared rails carry the cost of discovery; private players face near-zero acquisition costs and compete on service quality instead. When this happens, the ecosystem becomes self-sustaining — private activity generates economic value that no longer requires philanthropic or government subsidy to sustain.

### Key decisions

| Decision | Options considered | What was chosen | Why |
|---|---|---|---|
| Access channel | App, website, form, field worker, voice call | Voice call on any phone | Only channel that reaches the full population — no literacy, no smartphone, no English required. Every other channel excludes the majority of district residents. |
| Data architecture | Government-owned centralised registry; federated to existing institutions; participant-owned distributed map | Participant-owned, consent-governed, distributed | Trust is the foundation. Every Blue Dot exists because the person chose to be there. Consent at point of creation is not a compliance add-on — it is the mechanism that makes participation voluntary and sustainable. Also DPDP 2023 compliant by design. |
| Technology infrastructure | Custom-built proprietary system; licensed platform; open-source DPGs | Open-source DPGs (Signal, Aggregator, Facilitator, AI Diffusion) | New district does not build from scratch. DPGs can be configured and activated in 2 weeks once information is collated. No vendor lock-in. Any actor can deploy and adapt. |
| Onboarding strategy | Individual direct recruitment; bulk institutional onboarding | Aggregator-led mass onboarding | Person-by-person recruitment never reaches density. One MSME association brings 300+ employers in 2 weeks — more value than 6 months of field mobilisation. |
| Anchor adopter | Committee-based governance; project team as anchor | Single named District Champion (DC/CDO) who says "this runs in my name" | Ecosystems without a named champion have no spine. The first serious conflict between actors — data access, vendor claims, funder pressure — has no one to resolve it. The champion convenes aggregators and makes the ecosystem credible before it has proved itself. |
| Funding model | Seek revenue from day one; full philanthropic subsidy; time-bound government cold start | Government or philanthropic cold start for 12 months; private actor self-sustainability thereafter | Private actors cannot profitably engage before density is established. Government funds the cold start precisely so they don't have to — and so the ecosystem does not depend on continuous subsidy once the threshold is crossed. |
| Sequencing | Multi-district simultaneous launch; single district pilot | Single district first; do not scale before self-sustaining | Dharwad went first. Ghaziabad came second. "Do not try to run multiple districts simultaneously before the first one is self-sustaining." Each subsequent district starts where the prior one ended. |

### What worked

🟡 **Aggregator-led density in Dharwad:** One MSME association onboarded 300+ employers in 2 weeks. One ITI onboarded 500+ seekers. These two aggregators, on opposite sides of the use case, were sufficient to establish initial density. The map then started generating matches without additional recruitment. This is the key proof that the approach is faster than field mobilisation at equivalent scale.

🟡 **Voice as genuine zero-barrier entry:** The 2–3 minute voice call in any language on any phone is not a UX improvement on a form — it is a structural change in who can participate. Participation by the long tail (women returning to work, first-generation graduates, ITI graduates, SMBs with no digital presence) was demonstrated in both districts.

🟡 **Cost compression:** Discovery cost dropped from ₹500+ per field survey or job fair interaction to ₹10 per voice AI interaction in the same districts with the same population. 🟡

🟡 **Placement conversion:** Below 10% at job fairs → above 50% in targeted drives using voice-based discovery. Same district, same population, same period. 🟡

🟡 **10,000+ jobs revealed (Ghaziabad):** Fewer than 10% of Ghaziabad's SMBs surfaced on the shared map made over 10,000 local job openings visible in under 60 days. National platforms showed fewer than 100 local listings for the same district at the same time. The jobs had always been there. They were digitally dark.

🟡 **Cross-district compression:** 10 months (Dharwad, pioneer) → 4 months (Ghaziabad, second district). The compression demonstrates that the pathway is transferable and that the timeline depends on actors and readiness, not on technology.

### What failed or caused friction

Not documented in this source. The document describes the approach in terms of what it achieves and what sequence it requires, but does not document specific failures, near-misses, or frictions encountered in Dharwad or Ghaziabad.

**This is a significant gap for the next adopter.** What this pathway cannot yet tell you: what happens when the MSME association is reluctant to onboard, when the CDO moves to a new posting mid-activation, when innovators are slow to engage, or when the facilitation team loses operational discipline. These are predictable risks that the source document does not document.

### What would be done differently

Not documented in this source. No direct deployer reflection on this question exists in the available evidence.

---

## Toolkit

| Asset | Type | Description | Available |
|---|---|---|---|
| AI Diffusion DPGs | Open-source software | 7 building blocks (Knowledge Engine, Memory Layer, Trust Layer, Agent Core, Action Gateway, Reach Layer, Learning Layer) for assembling a production-grade voice AI system. Works with any speech model and LLM. | Open-source; contact [EkStep Foundation](../people-orgs/ai-diffusion-pathways.md) |
| Signal DPG | Open-source software | Manages Blue Dot signals: structures voice input, stores on shared consent-governed rails, handles matching and connection flows, feeds live signals to consuming platforms. | Open-source |
| Aggregator DPG | Open-source software | Gives aggregators tools to register, onboard participants at scale, and track Blue Dot status (active/at-risk/satisfied/stalled). Issues digitally verifiable credentials. | Open-source |
| Facilitator DPG | Open-source software | Gives District Facilitation Team and Jobs Facilitation Centre tools to monitor supply-demand gap and keep ecosystem healthy. | Open-source |
| Replication playbook | Documentation | Playbook documenting what sequence works, drawn from Dharwad and Ghaziabad. "These building blocks can be configured and activated for a district in 2 weeks once the information is collated." | Contact [EkStep Foundation](../people-orgs/ai-diffusion-pathways.md) |

---

## Safety and trust notes

Every Blue Dot exists only because the person or organisation behind it chose to be there. Consent is the foundation — not a policy declaration, but a property of the architecture. Data is collected with consent at the moment of creation, stored on shared public rails, and used only to enable discovery between parties who have both signalled intent. 🟡

The district administration governs the data for their district — accountable for ensuring rails remain open, ecosystem stays live, and participants retain control — but cannot access individual participant data without consent. Aggregators see only their own participants. Innovators access only what participants consent to share. 🟡

The system does not create or impose connections. It enables discovery between parties who have both signalled willingness. This architecture means the AI cannot be used to expose job-seekers to employers they have not consented to engage with.

---

## Policy and regulation notes

🟡 This architecture aligns with India's Digital Personal Data Protection Act (DPDP), 2023. Consent is captured at the point of data creation. Participants retain the right to access, correct, and erase their data. The state operator and district administration function as data fiduciaries — accountable for lawful processing, not owners of the data. Compliance is not a post-facto audit exercise but a built-in property of the rails. Source: Tushar Bansal, EkStep Foundation, May 2026.

For adopters outside India: the architecture's consent-at-creation and participant-ownership principles are likely to satisfy data protection frameworks in other jurisdictions, but specific legal review against local requirements is necessary before deployment.

---

## Related pathways

- [aggregator-led-density-building](aggregator-led-density-building.md) — The D1/D3/D4 sub-pathway: how to build two-sided density specifically, using aggregating institutions
- [consent-based-participant-data](consent-based-participant-data.md) — The B2/B3/F2 sub-pathway: how to design participant-owned, consent-governed data architecture
- [voice-first-access-design](voice-first-access-design.md) — Agriculture context; same voice-first architectural commitment; different sector and problem type
- [enabler-ecosystem-assembly](enabler-ecosystem-assembly.md) — Agriculture ecosystem design; 54-enabler model for comparison with the 2-sided aggregator model here

## Related concepts

- [paradox-of-proximity](../concepts/paradox-of-proximity.md) — The problem this pathway solves
- [ecosystem-aggregator-model](../concepts/ecosystem-aggregator-model.md) — The D1 mechanism in depth
- [network-operator-role](../concepts/network-operator-role.md) — District Champion and Facilitation Team as D4 instantiation
- [compression-sequence](../concepts/compression-sequence.md) — Dharwad → Ghaziabad as livelihoods compression track
- [inclusion-architecture](../concepts/inclusion-architecture.md) — Voice as structural inclusion solution in livelihoods context
- [dpi-ai-frame](../concepts/dpi-ai-frame.md) — Blue Dots AI as DPI for livelihoods; UPI analogy

## Lineage

No prior pathway directly preceded this one — this is the first livelihoods sector pathway in the wiki. The voice-first architecture and DPG approach draw on the same foundations as [voice-first-access-design](voice-first-access-design.md) and the agriculture deployments, but the problem type, ecosystem structure, and data architecture are distinct. This pathway should be read alongside, not as a continuation of, the agriculture pathways.
