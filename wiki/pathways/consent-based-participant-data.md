---
type: pathway
deployment: blue-dots-dharwad, blue-dots-ghaziabad
dimensions: [architecture]
sector: livelihoods
geography: India (Dharwad, Karnataka; Ghaziabad, Uttar Pradesh)
contributor: ai-diffusion-pathways
contributed: 2026-05-21
last-updated: 2026-05-21
times-referenced: 0
---

# Consent-Based Participant Data Architecture

**One-line summary:** How to design a data architecture where participants own their data, consent is built into the rails at the point of creation, and regulatory compliance is a structural property rather than a post-deployment audit exercise.

**Deployment source:** [Blue Dots AI — Dharwad](../deployments/blue-dots-dharwad.md) and [Blue Dots AI — Ghaziabad](../deployments/blue-dots-ghaziabad.md)
**Contributor:** Tushar Bansal — [AI Diffusion Pathways / EkStep Foundation](../people-orgs/ai-diffusion-pathways.md)
**Contributed:** 2026-05-21
**Last updated:** 2026-05-21
**Times referenced:** 0

---

## Context

You are deploying an AI system that handles personal data — skills, location, employment status, income, eligibility for schemes — for a large population of low-income citizens who have little experience with formal digital systems and limited practical ability to exercise rights they do not know they have.

The common approach is to collect data under a broad government mandate, store it centrally, and address privacy through policy commitments and periodic audits. This approach has two failure modes. First, participants do not trust it — and if they do not trust it, they do not participate, which means the infrastructure never reaches density. Second, it creates systemic risk: a data breach or political change that alters how the data can be used affects every participant simultaneously, with no recourse.

The Blue Dots AI architecture takes a structurally different approach: participants own their own data. Consent is captured at the moment of data creation — through the voice interaction itself — not as a checkbox in a form filled out separately. Participants can update, pause, or delete their Blue Dot. The state operator and district administration are data fiduciaries: accountable for lawful processing, not owners of the data. 🟡

This pathway is relevant when:
- Your deployment collects personal data from citizens who are not digitally literate and cannot practically navigate formal data rights processes
- You are operating under India's Digital Personal Data Protection Act (DPDP) 2023, or a comparable framework in another jurisdiction
- You need participant trust to achieve density — and you understand that a data model participants do not trust will not be used
- You are building infrastructure intended to last beyond a single programme cycle, and you need governance that survives political change

The Blue Dots AI deployments in Dharwad and Ghaziabad demonstrate that consent-at-creation is not an idealistic aspiration that slows deployment. It can be operationalised via voice — the consent is captured in the same 2–3 minute call that creates the Blue Dot. 🟡

---

## Shift map

| Shift | Summary | Documented? |
|---|---|---|
| A1 Problem framing | Not the primary focus of this pathway. | — |
| A2 Data posture | FROM: participants' data is collected by the state and stored centrally. TO: participants create their own data signals via consent-based voice interaction and own those signals. The data posture is participant-initiated, not state-collected. | ✓ 🟡 |
| A3 Existing assets | Not the primary focus of this pathway. | — |
| A4 Proof mechanism | Not the primary focus of this pathway. | — |
| B1 Model choice | Not the primary focus of this pathway. | — |
| B2 Data sovereignty | FROM: government owns citizen data; access is governed by policy. TO: citizen owns their Blue Dot; government governs (as data fiduciary) but does not own. Can update, pause, delete at any time. State operator maintains infrastructure; district administration governs for their district. Aggregators see only their own participants. Innovators access only what participants consent to share. | ✓ 🟡 |
| B3 Vendor independence | Open-source DPGs ensure no single vendor controls the rails. The state operator can switch technology partners without participants losing their data or their Blue Dot status. Vendor independence is a data sovereignty property, not just a procurement preference. | ✓ 🟡 |
| B4 DPG vs instance | Signal DPG manages the core data flows: structures participant voice input into a Blue Dot signal, stores on shared consent-governed rails, handles matching and connection flows. The DPG architecture means the data model is the same across districts and deployments — not proprietary to any instance. | ✓ 🟡 |
| C1 Framing | Not the primary focus of this pathway. | — |
| C2 Resistance | Not documented in source. Likely resistance: legal teams or government officials accustomed to state data ownership pushing back on participant-owned model as incompatible with public data governance frameworks. Not evidenced. | ✗ |
| C3 Institutional knowledge | Not documented in source. | ✗ |
| D1 Ecosystem design | Not the primary focus of this pathway. | — |
| D2 Trust source | Not the primary focus of this pathway. | — |
| D3 Coordination mechanism | Not the primary focus of this pathway. | — |
| D4 Network operator | Not the primary focus of this pathway. | — |
| E1 Training timing | Not the primary focus of this pathway. | — |
| E2 Training depth | Not the primary focus of this pathway. | — |
| E3 Agency test | Participant ownership of Blue Dot — the ability to update, pause, or delete — is the structural agency test for this pathway. The data architecture gives participants real control, not nominal rights. Digitally verifiable credentials give participants portable proof that does not depend on any intermediary. | ✓ 🟡 |
| F1 Velocity | Not the primary focus of this pathway. | — |
| F2 Governance | FROM: compliance as post-facto audit. TO: compliance as architectural property. The state operator and district administration function as data fiduciaries under DPDP 2023. Governance is defined by accountability for lawful processing, not by ownership of the data. | ✓ 🟡 |
| F3 Sustainability | Participant ownership of data makes the infrastructure more durable across political cycles: the data cannot be repurposed by a new administration without participant consent. This is a sustainability property, not just a privacy one. | ✓ ⬜ |
| F4 Pilot to deployment | Not documented in source. | ✗ |

---

## Playbook

### What was done and why

**The foundational commitment: consent at creation, not consent as a form**

The conventional approach is to create data collection systems and then add consent mechanisms — checkboxes, privacy notices, terms of service — as compliance requirements. This produces nominal consent that participants do not understand and cannot practically exercise.

The Blue Dots AI approach inverts this: the consent interaction *is* the data creation event. A job-seeker calling a voice number speaks their intent, skills, location, and availability. In speaking, they are creating their own Blue Dot. They are not submitting to a data collection exercise — they are registering their own presence. The consent is implicit in the act of calling and speaking, confirmed in the voice interaction itself. 🟡

This is not merely a better UX for consent. It creates a fundamentally different data model: the data is participant-created, not state-collected. The participant is the origin point of their own record.

**Who holds what, and the data fiduciary model**

The architecture separates three roles that are often conflated in government data systems:

- **Data creator / owner:** The participant (job-seeker, SMB, citizen). Creates the Blue Dot via voice. Owns it: can update, pause, delete.
- **Data custodian / operator:** The state government department or central ministry running the network (skilling mission, labour department, MSME department depending on use case). Maintains the infrastructure. Does not own participant data.
- **Data governor:** The district administration. Accountable for ensuring rails remain open, ecosystem stays live, participants retain control. Governs for their district — can onboard aggregators and innovators, monitor supply-demand gap — but cannot access individual participant data without consent.

This separation is operationalised in India through the DPDP 2023 data fiduciary model: the state operator and district administration are data fiduciaries, accountable for lawful processing, with no proprietary claim on the data itself. 🟡

**Scoped visibility: aggregators and innovators**

Aggregators see only their own participants. An ITI sees only the students it onboarded. An MSME association sees only its member businesses. This scoped visibility is not a policy rule — it is a property of the Aggregator DPG architecture. An aggregator cannot access other participants even if it wanted to.

Innovators (staffing firms, assessment providers, skilling organisations) access only what participants consent to share. When a seeker and an employer connect, both receive digitally verifiable credentials — proof of the connection — without either party's raw data being exposed to the other or to the innovator. 🟡

**Digitally verifiable credentials as participant-portable proof**

The Aggregator DPG enables aggregators to issue digitally verifiable credentials to participants they have onboarded. A job-seeker can present this credential to a potential employer — or to a government official, or to a financial services provider — without that third party needing access to the underlying Blue Dots platform. The credential is the proof; the data stays on the rails.

This is a structural mechanism for reducing transaction costs without exposing participant data. It also gives participants a concrete portable asset from their participation — proof of registration, skills, or connection history — that they carry with them independent of any platform or programme.

### Key decisions

| Decision | Options considered | What was chosen | Why |
|---|---|---|---|
| Data ownership model | Government owns data; platform owns data; participant owns data | Participant owns their Blue Dot — can update, pause, or delete | Trust is the foundation. Every Blue Dot exists because the person chose to be there. A data model where the government or platform owns participant data is incompatible with the consent foundation that makes voluntary participation possible. Without voluntary participation, the infrastructure never reaches density. |
| Consent mechanism | Separate consent form before registration; implied consent via terms of service; consent embedded in the data creation act | Consent captured at the moment of data creation via the voice interaction | Nominal consent — checkboxes, terms of service — does not constitute meaningful consent for populations with low literacy or low familiarity with digital systems. Consent that is embedded in the act of creating one's own record is consent that participants actually understand and exercise. |
| Data fiduciary structure | Single central government data controller; state operators as owners; state operators as fiduciaries | State operator and district administration as data fiduciaries (accountable, not owners) | DPDP 2023 compliance, but also a governance architecture that survives political change. A data fiduciary cannot unilaterally repurpose participant data; an owner can. The fiduciary model is more durable. |
| Aggregator data access | Full platform visibility for aggregators; aggregators see all participants; aggregators see only own participants | Aggregators see only their own participants; verifiable credentials for cross-aggregator verification | Prevents aggregators from using the shared infrastructure as competitive intelligence. Preserves participant privacy across the ecosystem. Verifiable credentials provide the cross-context proof without requiring data exposure. |
| Innovator data access | Innovators can buy access to participant data; innovators see filtered data with consent; innovators access only what participants consent to share | Innovators access only with explicit participant consent; receive verifiable credentials | Protects participants from becoming a commodity sold by the infrastructure. Maintains the participant-controlled model even when private actors are involved. |

### What worked

🟡 **Consent-at-creation via voice is operationally viable:** The 2–3 minute voice call is the full onboarding and consent interaction — there is no separate form, no privacy notice to read, no checkbox to tick. This is not a compromise on consent rigour; it is a consent mechanism designed for the actual population. Source: Tushar Bansal, EkStep Foundation, May 2026.

🟡 **DPDP 2023 compliance as architectural property:** The architecture aligns with DPDP 2023 without requiring a post-deployment compliance exercise. Consent is captured at creation; participants retain access, correction, and erasure rights by virtue of owning their Blue Dot; the state operator is a data fiduciary by the architecture, not by policy declaration alone.

🟡 **Verifiable credentials reduce downstream transaction costs:** When a seeker and employer connect, they exchange verifiable credentials rather than raw data. The employer can verify the seeker's Blue Dot status without accessing the platform or the seeker's full record. This reduces the friction of each connection without increasing data exposure.

### What failed or caused friction

Not documented in this source. Anticipated friction points not evidenced here:

- Government legal teams accustomed to state data ownership frameworks may push back on the participant-ownership model as incompatible with public infrastructure governance
- Departments accustomed to extracting and analysing citizen data for planning purposes may resist a model where they cannot access individual participant records without consent
- Aggregators who are used to owning their constituency data (e.g., an MSME association that considers its member database proprietary) may resist the scoped visibility model

These are inferred risks, not documented failures. Mark as ⬜.

### What would be done differently

Not documented in this source. No direct deployer reflection available.

---

## Toolkit

| Asset | Type | Description | Available |
|---|---|---|---|
| Signal DPG | Open-source software | Core data management: structures participant voice input into a Blue Dot signal, stores on shared consent-governed rails, handles matching and connection flows, feeds live signals to consuming platforms. Implements participant-owned data model. | Open-source; contact [EkStep Foundation](../people-orgs/ai-diffusion-pathways.md) |
| Aggregator DPG | Open-source software | Implements scoped visibility for aggregators; issues digitally verifiable credentials. Open-source. | Open-source |
| DPDP 2023 alignment documentation | Regulatory | The Blue Dots AI architecture's alignment with DPDP 2023 is described at the structural level in the source document. Formal legal review documentation is not confirmed as a standalone asset. | Contact EkStep Foundation |

---

## Safety and trust notes

The consent-at-creation model is itself a safety mechanism: participants cannot be registered without their own voice-initiated action. There is no path by which a government official or aggregator staff member can create a Blue Dot on behalf of a participant without their direct participation.

The "assisted voice" onboarding method (where aggregator staff make calls on behalf of participants) is the one place where this assurance is weaker: if an aggregator staff member initiates and structures the voice call without adequate participant participation, the consent may be nominal. This is a risk not addressed in the source document. Next adopters should design explicit safeguards for the assisted voice channel. ⬜

---

## Policy and regulation notes

🟡 **DPDP 2023 (India):** This architecture was explicitly designed to align with India's Digital Personal Data Protection Act, 2023. Consent is captured at the point of data creation. Participants retain the right to access, correct, and erase their data. The state operator and district administration function as data fiduciaries — accountable for lawful processing, not owners of the data. Compliance is a built-in property of the rails, not a post-facto audit exercise. Source: Tushar Bansal, EkStep Foundation, May 2026.

⬜ **Jurisdictions outside India:** The consent-at-creation and participant-ownership principles are likely to satisfy data protection frameworks in other jurisdictions (GDPR, similar African and South Asian frameworks), but specific legal review against local requirements is necessary. The data fiduciary concept in DPDP 2023 may not map directly to data controller/processor distinctions in other frameworks.

---

## Related pathways

- [local-discovery-infrastructure](local-discovery-infrastructure.md) — The full Blue Dots AI pathway; this pathway documents the B2/B3/F2 data architecture component of that system
- [aggregator-led-density-building](aggregator-led-density-building.md) — The D1/D3/D4 component; the aggregator's scoped visibility is governed by the architecture documented here
- [federated-data-architecture](federated-data-architecture.md) — Agriculture context; federated institutional data (connect at query time) for comparison with participant-created distributed data here

## Related concepts

- [dpi-ai-frame](../concepts/dpi-ai-frame.md) — Participant-created data as a third architecture pattern alongside federate/aggregate; the DPI+AI frame applied to livelihoods
- [federate-vs-aggregate-data](../concepts/federate-vs-aggregate-data.md) — The data architecture decision in agriculture context; participant-created data is a distinct third option not covered in that concept page
- [inclusion-architecture](../concepts/inclusion-architecture.md) — Voice-first access is both the inclusion mechanism and the consent mechanism in this architecture; they are not separable

## Lineage

No prior pathway directly preceded this in the livelihoods sector. The data sovereignty principles draw on the same DPI+AI frame documented in agriculture pathways (see [dpi-ai-frame](../concepts/dpi-ai-frame.md)), but the specific implementation — participant-created data, consent-at-creation via voice, fiduciary governance — is distinct from the institutional-data-federated model in agriculture. The key difference: in agriculture, institutions own data about farmers; in Blue Dots AI, participants own data about themselves.
