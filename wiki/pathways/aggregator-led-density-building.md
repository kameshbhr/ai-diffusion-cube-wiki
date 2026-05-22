---
type: pathway
deployment: blue-dots-dharwad, blue-dots-ghaziabad
dimensions: [ecosystem]
sector: livelihoods
geography: India (Dharwad, Karnataka; Ghaziabad, Uttar Pradesh)
contributor: ai-diffusion-pathways
contributed: 2026-05-21
last-updated: 2026-05-21
times-referenced: 0
---

# Aggregator-Led Density Building

**One-line summary:** How to build two-sided density in a discovery marketplace rapidly by onboarding existing institutions rather than recruiting participants one by one — reaching the long tail in weeks, not months.

**Deployment source:** [Blue Dots AI — Dharwad](../deployments/blue-dots-dharwad.md) (pioneer) and [Blue Dots AI — Ghaziabad](../deployments/blue-dots-ghaziabad.md) (second district)
**Contributor:** Tushar Bansal — [AI Diffusion Pathways / EkStep Foundation](../people-orgs/ai-diffusion-pathways.md)
**Contributed:** 2026-05-21
**Last updated:** 2026-05-21
**Times referenced:** 0

---

## Context

You are designing a two-sided marketplace or discovery infrastructure — livelihoods, welfare scheme access, health referrals, agricultural services — and you face the fundamental cold start problem: without enough participants on both sides, no one finds a match, early users lose confidence, and the platform collapses before it can demonstrate value.

The default approach is field mobilisation: deploying teams to recruit participants one by one. This is expensive, slow, and never reaches density. A job fair costs ₹500+ per interaction and yields below 10% placement. Six months of field mobilisation may not achieve what one well-chosen aggregator achieves in two weeks. 🟡

The aggregator model solves this differently. Instead of recruiting individuals, recruit the institutions that already hold trust relationships with the long tail — ITIs with hundreds of enrolled students, MSME associations with hundreds of member businesses, NGOs with deep community connections. One committed aggregator on each side of a use case provides the density that makes matching possible.

This pathway is relevant when:
- You are deploying infrastructure that requires participation on two distinct sides (seekers and providers, beneficiaries and scheme administrators, patients and referral centres)
- The participants you need to reach are not on national platforms and are not individually digitally accessible
- You have a six-to-twelve week window to reach meaningful density before early adopters lose confidence
- There are existing institutions in your target geography that already hold trust relationships with the population you need

Dharwad (Dharwad, Karnataka): one MSME association onboarded 300+ employers in 2 weeks; one ITI onboarded 500+ seekers. These two institutions, on opposite sides of the livelihoods use case, were sufficient to establish density on the shared map. 🟡

---

## Shift map

| Shift | Summary | Documented? |
|---|---|---|
| A1 Problem framing | Not the primary focus of this pathway. | — |
| A2 Data posture | Not the primary focus of this pathway. | — |
| A3 Existing assets | The aggregating institutions themselves are the critical existing asset. ITIs, MSME associations, NGOs, skilling centres with enrolled populations exist in virtually every district. The question is which ones have the strongest relationships and widest reach on each side of the use case. | ✓ 🟡 |
| A4 Proof mechanism | Density reached rapidly (weeks) is the early proof that makes both sides believe the infrastructure is real. 300+ employers in 2 weeks (Dharwad MSME association); 500+ seekers onboarded (Dharwad ITI). These numbers establish credibility before matches are made. | ✓ 🟡 |
| B1 Model choice | Bulk voice upload is the key B1 feature for aggregators: onboard constituents en masse via voice rather than individual form-filling. The Aggregator DPG provides tools for mass onboarding and real-time status tracking. | ✓ 🟡 |
| B2 Data sovereignty | Aggregators see only their own participants — an ITI sees students it onboarded; an MSME association sees its member businesses. Aggregators issue digitally verifiable credentials that enable a receiver to verify a Blue Dot in seconds without exposing raw data. | ✓ 🟡 |
| B3 Vendor independence | Not the primary focus of this pathway. | — |
| B4 DPG vs instance | Aggregator DPG is purpose-built for this function: register, onboard at scale, track participant status (active / at-risk / satisfied / stalled), issue verifiable credentials. Open-source; any aggregating institution can deploy it. | ✓ 🟡 |
| C1 Framing | Not the primary focus of this pathway. | — |
| C2 Resistance | Not documented in source. Risk: an aggregating institution may resist onboarding its constituents onto infrastructure it does not control. This is a likely friction point not yet documented with evidence. | ✗ |
| C3 Institutional knowledge | Not documented in source. | ✗ |
| D1 Ecosystem design | The minimum viable ecosystem is one aggregator per side of the use case, selected before activation begins. For livelihoods: one ITI or college (seeker side) + one MSME association (provider side). These are institutions that already serve the long tail — the task is not to create them but to find them. Additional aggregators are layered in as density grows. | ✓ 🟡 |
| D2 Trust source | Aggregators carry their existing trust relationship with constituents into the platform. The endorsement of a known institution — "our association recommends this; here is how to register" — carries weight that a government portal or direct outreach does not. Trust is delegated from the aggregator to the infrastructure. | ✓ 🟡 |
| D3 Coordination mechanism | Aggregators are onboarded in sequence: provider-side and seeker-side aggregators both onboarded before participants join, so both sides of the map have density simultaneously. The District Facilitation Team tracks aggregator engagement weekly — which aggregators are active, which are stalling, which Blue Dots are going cold. | ✓ 🟡 |
| D4 Network operator | The District Facilitation Team is the operational spine for aggregator coordination. The District Champion's endorsement gives aggregators a reason to commit before they can see value themselves. Without the Champion's named commitment, aggregators face an uncertain investment of their relationship capital. | ✓ 🟡 |
| E1 Training timing | Not documented in source for aggregators or their constituents. | ✗ |
| E2 Training depth | Not documented in source. | ✗ |
| E3 Agency test | Aggregators issue digitally verifiable credentials to participants — a structural mechanism that gives participants portable, independently verifiable proof of their status. This reduces participant dependency on the aggregating institution for ongoing verification. | Partial ⬜ |
| F1 Velocity | One strong aggregator on each side and the map starts doing the work — in Dharwad, this happened within weeks of the first aggregator pair being onboarded. The velocity lever here is relationship leverage, not technology. | ✓ 🟡 |
| F2 Governance | Aggregators see only their own participants. Innovators access only with participant consent. This scoped visibility is a governance property of the Aggregator DPG architecture, not a policy rule. | ✓ 🟡 |
| F3 Sustainability | Once aggregators are active and density is established, the map generates its own momentum — automated nudges bring participants back, matches occur without further facilitation effort. The aggregator model concentrates the cold start investment (onboarding 300+ employers in 2 weeks) rather than spreading it indefinitely across field mobilisation. | ✓ 🟡 |
| F4 Pilot to deployment | Not documented in source. | ✗ |

---

## Playbook

### What was done and why

**Step 1: Identify, before activation, one strong aggregator on each side**

Before any participant registration begins, the District Facilitation Team identifies at minimum one strong institution on each side of the use case. "Strong" means: already serves the long tail (not the digitally fluent), has an active membership or enrolment relationship, and has a leader or secretary who will personally champion the onboarding.

Do not begin participant recruitment without these two institutions in place. A map with density on only one side produces no matches, and both sides lose confidence simultaneously. 🟡

For livelihoods use cases: one ITI or college (seeker side) and one MSME association or employer network (provider side). For welfare use cases: one CSC or gram panchayat (beneficiary side) and one scheme-issuing department (provider side). The structure is universal; the specific institutions vary.

**Step 2: Mass onboard via existing relationships**

The aggregator does not recruit individuals — it converts its existing membership or enrolment into Blue Dots. The onboarding mechanism is designed to minimise friction for the aggregator:

- **Bulk voice upload:** The aggregator's database of members or students is pre-loaded; participants receive an automated voice call that confirms and structures their signal. Minimal effort from the participant; minimal coordination cost for the aggregator.
- **QR code:** A poster or WhatsApp link takes participants to a voice-based onboarding flow. Works in contexts where the aggregator has a physical presence (ITI campus, MSME association office, skilling centre).
- **Assisted voice:** Aggregator staff make calls on behalf of participants — effective for populations with very low digital confidence.

**Step 3: Track and prevent attrition**

The Aggregator DPG gives every aggregator real-time visibility into participant status: who is active, who is at-risk, which Blue Dots are going cold. This is a significant change from field surveys, which produce static annual snapshots. Aggregators see their population weekly.

When a Blue Dot goes cold — the participant has become inactive, the vacancy has been filled, the seeker has found work — the system prompts both the aggregator and the participant. This feedback loop keeps the map fresh and prevents the attrition that kills two-sided marketplaces.

**Step 4: Layer in additional aggregators as density grows**

Once the first aggregator pair has established density, additional aggregators on each side can be onboarded with lower effort — the infrastructure is proven, the map has visible activity, and new aggregators join because they can see the value rather than being asked to trust a promise. The first aggregator pair is the hardest; each subsequent pair is easier.

### Key decisions

| Decision | Options considered | What was chosen | Why |
|---|---|---|---|
| Who qualifies as an aggregator? | Any institution willing to participate; only government institutions; only institutions with strong digital infrastructure | Institutions that already hold trust relationships with the long tail, regardless of digital sophistication | The aggregator's value is its relationship capital, not its technology. An MSME association with no website but 300 active member businesses is more valuable than a digital platform with a large nominal membership and no active relationships. |
| How many aggregators before launch? | Launch with whoever is available; wait until many aggregators are ready | At minimum one per side of the use case, both committed before any participant registration begins | One per side is sufficient to establish density if both are strong. Launching with zero on one side produces no matches and loses both sides simultaneously. |
| Onboarding mechanism | Individual digital registration; field worker-mediated; aggregator-led bulk | Aggregator-led bulk (voice, QR, assisted) | Removes the participant onboarding burden from the facilitation team and places it with the institution that already has the relationship. One MSME association calling its own member businesses is more trusted and more efficient than a government team cold-calling the same businesses. |
| What the aggregator can see | Full participant data across the platform; only their own participants | Only their own participants | Data privacy and trust boundary. An ITI does not need to see employer vacancy data. An MSME association does not need to see other institutions' participants. Scoped visibility builds trust and reduces risk of aggregator overreach. |

### What worked

🟡 **Mass onboarding velocity in Dharwad:** One MSME association onboarded 300+ employers in 2 weeks. One ITI onboarded 500+ seekers. These numbers establish that the aggregator model achieves in days what field mobilisation achieves in months — and does so through relationship leverage, not technology.

🟡 **Relationship trust as the onboarding mechanism:** The aggregator's existing relationship with its constituency is the critical asset. Participants register because their ITI or MSME association is telling them to — not because they independently discovered and trust the government platform. This trust delegation is what makes mass onboarding possible at the speed documented.

🟡 **Verifiable credentials as a post-onboarding value-add:** Aggregators issuing digitally verifiable credentials to participants gives participants portable proof — a job-seeker can verify their Blue Dot status to a potential employer without the employer needing to access the platform. This reduces transaction costs downstream and gives participants a concrete reason to maintain their Blue Dot.

### What failed or caused friction

Not documented in this source. Likely friction points that a next adopter should plan for, but which are not evidenced here:

- An aggregator institution whose leadership is willing but whose operational staff do not follow through on bulk onboarding
- Aggregators who onboard constituents but do not maintain the relationship, leading to rapid Blue Dot attrition
- Resistance from an aggregator whose leadership perceives the shared infrastructure as a competitive threat (e.g., a staffing agency that aggregates job-seekers and does not want to make them discoverable on a shared map)

These are inferred risks, not documented failures. Mark as ⬜.

### What would be done differently

Not documented in this source. No direct deployer reflection available.

---

## Toolkit

| Asset | Type | Description | Available |
|---|---|---|---|
| Aggregator DPG | Open-source software | Platform for aggregating institutions: register, onboard participants at scale (bulk voice, QR, assisted), track Blue Dot status (active/at-risk/satisfied/stalled), issue digitally verifiable credentials. | Open-source; contact [EkStep Foundation](../people-orgs/ai-diffusion-pathways.md) |
| Aggregator identification checklist | Methodology | Criteria for identifying strong aggregating institutions on each side of a use case (implied from source; not described as a standalone document). | Not confirmed as standalone — contact EkStep Foundation |

---

## Safety and trust notes

The scoped visibility model — aggregators see only their own participants, innovators access only with participant consent — is a safety property, not just a policy. It prevents aggregators from using the shared infrastructure as a surveillance or competitive intelligence tool against participants they have not onboarded. 🟡

Digitally verifiable credentials mean that when a participant shares their Blue Dot status with a third party, that third party can verify without accessing the underlying data. The credential is the proof; the raw data stays on the rails. 🟡

---

## Policy and regulation notes

🟡 The aggregator data governance model aligns with DPDP 2023: aggregators act as consent managers for their constituents (they facilitated the onboarding consent) but do not own participant data. The state operator is the data fiduciary. This separation of consent management from data ownership is a structural compliance property, not a policy statement.

---

## Related pathways

- [local-discovery-infrastructure](local-discovery-infrastructure.md) — The full Blue Dots AI pathway of which this is the D1/D3/D4 component
- [consent-based-participant-data](consent-based-participant-data.md) — The data architecture that governs what aggregators can and cannot see
- [enabler-ecosystem-assembly](enabler-ecosystem-assembly.md) — Agriculture ecosystem design: 54-enabler model for comparison with the 2-sided aggregator pairing documented here

## Related concepts

- [ecosystem-aggregator-model](../concepts/ecosystem-aggregator-model.md) — Full concept treatment of the aggregator model pattern
- [network-operator-role](../concepts/network-operator-role.md) — The District Champion and Facilitation Team whose endorsement makes aggregator commitment credible
- [paradox-of-proximity](../concepts/paradox-of-proximity.md) — The problem the aggregator model is deployed to solve
- [inclusion-architecture](../concepts/inclusion-architecture.md) — The aggregator model reaches the same long tail that voice-first access is designed to serve

## Lineage

No prior pathway directly preceded this. The aggregator model is structurally distinct from the 54-enabler ecosystem assembly documented in [enabler-ecosystem-assembly](enabler-ecosystem-assembly.md). That pathway assembles knowledge infrastructure; this pathway assembles two-sided participant density. Both are D1 ecosystem design but solve different problems.
