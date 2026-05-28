# Dimension Shifts — The 21 FROM→TO Patterns

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bharat-VISTAAR, Bihar Krishi, Ethiopia ATI
**Last updated:** 2026-05-28

## The Pattern

Across the five OAN deployments, each of the six dimensions shows a consistent FROM→TO shift — a characteristic move from how AI deployments are typically approached to how successful ones are actually structured. These 21 sub-component shifts (7 technology, 14 non-technology) are not prescriptions; they are patterns extracted from field experience. The 30/70 split between technology and non-technology sub-components reflects where effort actually concentrates in practice: two-thirds of the decisions that determine whether a deployment scales are non-technology.

Note: A5 (inclusion design) is listed in the source framework as a proposed addition to the A-dimension sub-components. It is included here as a proposed shift, not yet a confirmed sub-component.

## Evidence

### A — Problem Orientation

**A1 — Problem Framing: from generic use case to specific population with named failure condition**

FROM: generic AI use case definition ("what can AI do in agriculture?") TO: specific problem with a named population and a clear articulation of why the existing system fails them.

MahaVistaar's problem statement was specific: the extension officer network cannot deliver personalised advice to 1.5 crore Maharashtra farmers at the query cadence required for time-sensitive decisions. This specificity drove architecture choices — voice telephony for access reach, federated real-time data for answer currency, proactive alerts for time-critical conditions. A generic framing would not have generated these constraints.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**A2 — Data Posture: from waiting for clean centralised data to deploying with federated data**

FROM: waiting for a clean, centralised data lake before deployment TO: designing a federated architecture that connects to data where it lives.

All OAN deployments connect to data at query time rather than migrating it to a central store. The inter-departmental data-sharing blockage in MahaVistaar — where the state agriculture department held data in a system the extension directorate could not access — was resolved by the federated approach: data never left its owning department, so no departmental consent to migration was required.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**A3 — Existing Assets: from building from scratch to assembling from DPGs, data, and prior deployments**

FROM: treating every deployment as a greenfield build TO: inventorying existing assets (DPG layer, institutional data, knowledge repositories) before deciding what to build.

The OAN DPG layer is an existing asset at the technology level. ICAR research data (Bharat-VISTAAR), Amul cooperative data (Sarlaben), and state agricultural databases (MahaVistaar) are existing assets at the data level. Amul Sarlaben deployed in 3 weeks because it assembled from existing assets rather than building from scratch.

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

**A4 — Proof: from disconnected pilot to pilot on production architecture**

FROM: a proof-of-concept pilot running on a prototype, to be replaced by a production rebuild TO: a pilot that runs on the same architecture as production.

All OAN deployments are built on the same DPG-based architecture from the outset. There is no pilot-to-production architecture gap, and no migration risk. The proof and the scale pathway are the same system.

**A5 — Inclusion Design (proposed): from accessibility as a later layer to access constraints as first-order design inputs**

FROM: accessibility features added after the core architecture is defined TO: access constraints (language, literacy, connectivity) treated as first-order design constraints that determine the interface.

Voice-first telephony was chosen before architecture was detailed, because the access constraints of Maharashtra's farmer population — Marathi, low digital literacy, no reliable data connectivity — were treated as non-negotiable. All OAN deployments share this characteristic: the interface choice (voice over telephony) is an access decision, not a feature decision.

### B — Architecture

**B1 — Model Choice: from commercial frontier LLM to fine-tuned open-weights model**

FROM: commercial frontier LLM API (GPT-4 class) as the production serving infrastructure TO: fine-tuned open-weights model deployed self-hosted.

MahaVistaar began on Azure GPT-4.1 at ₹9.4/question. The architecture migrated to self-hosted fine-tuned Qwen3.5-27B at ₹0.05/question — a 188× cost reduction. The fine-tuned smaller model also responds more predictably within the agricultural domain, making the safeguard model's task easier. A deployment that does not plan for this migration will face it at the worst moment — when query volume is growing and the commercial API cost is spiralling.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**B2 — Data Sovereignty: from centralised data lake to federated data**

FROM: centralised data lake owned by the deployer TO: federated architecture where each institution retains sovereignty over its data.

All OAN deployments use federated architecture. No institution was required to migrate data out of its own systems. The federated approach is both a technical design choice and an institutional negotiation strategy: it removes the main objection institutional data owners have to participation.

**B3 — Vendor Independence: from locked-in cloud stack to open DPG layer with pluggable components**

FROM: proprietary cloud AI stack (single vendor dependency) TO: open DPG layer with protocol-based ecosystem interoperability.

The OAN DPG layer is open-source and deployable without a specific cloud vendor. The Beckn protocol enables ecosystem interoperability without proprietary standards. The MahaVistaar serving migration (Azure GPT-4.1 to self-hosted Qwen) demonstrated vendor independence in practice, not just in principle.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**B4 — DPG vs Instance: from each deployment building its own system to shared DPG layer plus thin configuration**

FROM: each new deployment rebuilding the full technology stack TO: shared DPG layer maintained by a network operator, with each deployment adding only language, domain, and institutional configuration.

The compression from MahaVistaar's original build to Amul Sarlaben's 3-week deployment is the quantified evidence for this shift. Bihar Krishi, as an independent deployment not using the OAN DPG layer, is the intended comparison case — but its timeline and cost are not yet documented.

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md) | [Bihar Krishi](../pathways/bihar-krishi.md)

### C — Institution

**C1 — Institutional Framing: from project to transformation**

FROM: positioned as a technology project with a defined end date TO: positioned as a transformation of the extension delivery system with ongoing mandate.

MahaVistaar is positioned under the Commissioner of Agriculture as a transformation — not a project. This framing affects funding (recurring rather than project-based), staffing (permanent rather than contracted), and survival through political change. A project mandate ends; a transformation mandate must be explicitly dismantled.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**C2 — Resistance and Non-Transferability: from communication problem to structural design problem**

FROM: institutional resistance treated as something to be overcome through explanation and demonstration TO: institutional resistance treated as a structural design problem requiring authority and accountability changes.

The joint secretary-level meeting required to resolve MahaVistaar's data-sharing blockage was not resolved by explaining the technology. It required convening the authority level at which a structural data governance question could be decided. Resistance in large government organisations is often a signal that a decision requires authority that has not yet been engaged, not that the technology needs better communication.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**C3 — Institutional Knowledge: from individual champions to embedded process**

FROM: deployment knowledge held by individual champions who may leave TO: knowledge embedded in the OAN DPG layer, in documented processes, and in institutionalised training.

The OAN DPG layer represents institutionalised knowledge — architecture decisions, safety patterns, and ecosystem coordination models that can survive the departure of the individuals who designed them. A deployment that exists only in the heads of its champions is a succession risk.

### D — Ecosystem

**D1 — Ecosystem Design: from deployer plus vendor to minimum viable ecosystem with named roles**

FROM: deployment imagined as a two-party relationship between deployer and technology vendor TO: minimum viable ecosystem with named roles across institutional, technology, data, and knowledge layers.

MahaVistaar mapped 54 enablers across four layers. The number is not the point — the point is that the roles are named and the minimum set required for the system to function is identified before deployment, not discovered when a gap causes an incident.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**D2 — Trust Source: from trust in the AI to trust in the institution**

FROM: trust in the AI system itself (accuracy, reliability) as the primary adoption driver TO: trust sourced from the deploying institution, with the AI delivered under that institution's brand and channel.

Farmers trust MahaVistaar because it is the Commissioner of Agriculture's system, delivered on government short code 155313. Amul Sarlaben's trust source is the Amul cooperative relationship. Ethiopia ATI's trust source is ATI's government mandate. In none of these deployments is the AI itself the trust source — the institution is.

[See full pathways: MahaVistaar](../pathways/mahavistaar.md) | [Amul Sarlaben](../pathways/amul-sarlaben.md) | [Ethiopia ATI](../pathways/ethiopia-ati.md)

**D3 — Coordination Mechanism: from informal relationships to protocol-based coordination with a named operator**

FROM: ecosystem coordination through informal personal relationships TO: protocol-based coordination (Beckn protocol) with a named network operator holding the coordination function.

The Beckn protocol provides a standards-based coordination mechanism that survives personnel changes. EkStep Foundation as named network operator holds the coordination function across the OAN ecosystem — relationships do not need to be rebuilt when individuals move.

**D4 — Network Operator: from no named operator to explicit mandate**

FROM: no organisation explicitly responsible for ecosystem health TO: named network operator (EkStep Foundation) with an explicit mandate.

EkStep Foundation is the named network operator across all OAN deployments. Without this role explicitly assigned, ecosystems erode: data feeds go stale, technology integrations break, and knowledge sources stop being updated, with no one holding responsibility for any of it.

[See entity: EkStep Foundation](../entities/ekstep-foundation.md)

### E — Workforce

**E1 — Training Timing: from post-deployment training to training integrated into system design**

FROM: training delivered at deployment launch as an afterthought TO: training integrated into system design from the beginning, with escalation paths designed around what the human workforce can handle.

Extension officer roles in MahaVistaar (Krishi Sahayaks, BOs, SDOs) are designed into the system architecture — the escalation paths in the AI advisory (situations where the system directs farmers to a human officer) are designed with the workforce's capability and availability in mind, not bolted on afterward.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**E2 — Training Depth: from tool training to capability building**

FROM: training staff to use the system (which buttons to press, which menus to navigate) TO: training staff to interpret, verify, and extend AI outputs.

Not documented in detail across any OAN deployment. The shift is named in the framework as critical — an extension officer trained only to use the system becomes dependent on it, whereas one trained to verify and extend outputs maintains capability if the system is unavailable or wrong.

**E3 — Agency Test: from measuring system usage to testing whether people can work without it**

FROM: measuring adoption (how many staff are using the system) as the primary workforce metric TO: testing whether staff can still do their core job if the system goes offline.

Not documented in detail across any OAN deployment. The framework proposes this as a critical check for any deployment that replaces or augments human advisory roles. High adoption combined with inability to function without the system is a fragility indicator, not a success signal.

### F — Operating Model

**F1 — Velocity: from plus-one scaling to compressed replication**

FROM: each new deployment treated as a new project (adding one at a time, each requiring the same build effort) TO: replication with compression (each new deployment faster and cheaper than the previous, due to DPG accumulation).

The compression from MahaVistaar to Amul Sarlaben (3 weeks) is the evidence. Bihar Krishi, as an independent deployment, is intended to provide the comparison — but its timeline is not yet documented.

[See synthesis: Compression Proof](compression-proof.md)

**F2 — Governance: from governance as constraint to governance as enabler**

FROM: governance processes (approvals, sign-offs) treated primarily as delays to route around TO: governance clarity (right level of authority engaged at right time) as the mechanism that resolves structural blockages.

The joint secretary-level meeting that resolved MahaVistaar's data-sharing blockage is the evidence: when the right authority was convened, a structural stall was resolved. The failure mode is not engaging that authority level early enough, not the governance process itself.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**F3 — Sustainability: from deferred funding clarity to pre-scale cost model**

FROM: funding model deferred until after the pilot proves value TO: cost model built before scale, with a documented projection of infrastructure investment versus ongoing API cost.

MahaVistaar's serving cost analysis (₹25 lakh for 6-month 4-GPU cluster; ₹2 crore/year planned versus ₹18 crore/year Azure run-rate) is the evidence. The deployer can make an informed decision about infrastructure investment before being locked into a cost trajectory at scale.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

**F4 — Pilot to Deployment: from prototype replaced by production to pilot IS production**

FROM: prototype pilot to be replaced by a separate production build TO: pilot running on the same architecture as production from day one.

All OAN deployments use the DPG-based architecture from pilot through production. There is no transition risk between pilot and production because the pilot is already production-grade. The cost of rebuilding is eliminated, and the learnings from the pilot accumulate directly in the production system.

## What This Means for a Next Adopter

The 21 shifts are most useful as a diagnostic: if your current deployment design sits on the FROM side of multiple sub-components, you are accumulating risk that will compound at scale. The highest-leverage shifts:

B1 (model choice) — do not anchor on a commercial frontier LLM API as production serving infrastructure. Fine-tune a smaller open-weights model early; the cost and control advantages compound with scale.

A2 (data posture) — do not wait for centralised, clean data. Design federated from the start; it is easier than migrating later and removes institutional objections.

D4 (network operator) — name the network operator before you need them. Ecosystem collapse often happens when no one is explicitly responsible for ecosystem health.

F3 (sustainability) — build a cost model before scale, not after.

## Open Questions

E2 (training depth) and E3 (agency test) are named shifts but not yet documented with field evidence. A next contributing deployment should capture what training approach was used and whether extension officers could still function if the system went offline.

Bihar Krishi, as an independent deployment, could document the FROM side of the B4 shift — what does it cost and take to build without the DPG layer? This comparison data point does not yet exist in the wiki.
