# Dimension Shifts — FROM→TO Patterns

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bharat-VISTAAR, Bihar Krishi, Ethiopia ATI
**Last updated:** 2026-05-28

## The Pattern

Across five deployments spanning government, cooperative, and civil society actors in India and Ethiopia, a consistent set of orientation shifts appears — decisions that moved the deployment from a default posture toward a posture that made scale possible. These are not recommendations derived from theory. They are patterns extracted from what the deployments that reached scale actually did, compared with what comparable deployments that stalled tended to do. Taken together, they describe 21 FROM→TO movements across all six dimensions.

The common thread across all 21 shifts is a movement from institution-centric to user-centric, from project to capability, and from centralised to federated. Each shift has a cost in institutional comfort and a return in deployment durability.

## Evidence

### A — Problem Orientation Shifts

**A1 — Problem Framing**
FROM: Deploying a technology solution (answering the question "what can AI do?")
TO: Solving a specific user problem (answering the question "what does this farmer need at 6am before going to the field?") ⬜

In MahaVistaar, the deployment team documented the user constraint profile (rural, variable-literacy, Marathi-speaking, mobile-only) before designing the interface. The voice short code 155313 is the outcome of a problem framing exercise, not a technology preference. 🟡 In Amul Sarlaben, the problem statement — 1,400 vets for 3.6 million farmers and 22 million cattle — is numerically specific enough to generate a clear solution direction. 🟡

**A2 — Data Posture**
FROM: Waiting for clean, centralised data before deploying
TO: Deploying on the data that exists, federated, and improving data quality iteratively ⬜

MahaVistaar's federated architecture — connecting to data at query time via API rather than centralising it — is the clearest example of this shift. 🔵 The deployment did not wait for a unified agricultural database; it connected to what existed (ICAR knowledge, IMD weather, state scheme data) and composed them at inference time. In Amul Sarlaben, the existing 2 billion transactions and 30 million cattle records were used as-is, without requiring a separate data cleaning or migration project. 🟡

**A3 — Existing Assets**
FROM: Building new when something usable already exists
TO: Inheriting and adapting existing infrastructure, knowledge bases, and institutional relationships ⬜

Ethiopia ATI reached launch in 3 months by inheriting architecture components from MahaVistaar rather than building from scratch. 🟡 Bharat-VISTAAR inherits the MahaVistaar state deployment as its first and most complete spoke. The ICAR knowledge base, IMD weather feeds, and Agristack data infrastructure are existing assets that multiple deployments drew on rather than rebuilt.

**A4 — Proof**
FROM: Seeking proof of concept before investing in production infrastructure
TO: Using real-scale pilots to generate proof, accepting initial inefficiency as the cost of honest evidence ⬜

MahaVistaar's cost trajectory — from ₹9/question on commercial APIs to ₹0.05/question on self-hosted infrastructure — shows a deployment that operated at real scale under inefficient conditions long enough to understand the cost problem, then solved it once the problem was defined by evidence. 🔵 The 342,000+ users and 1.67M+ questions represent the proof base. Bihar Krishi's 20-25% monthly engagement rate and 38,000+ scheme applications are the proof signals that preceded recognition (ET DigiTech Gold, SKOCH Gold). 🟡

**A5 — Inclusion Design**
FROM: Designing for the average or majority user and adding accessibility as a feature
TO: Designing for the hardest-to-reach user and letting everyone else benefit ⬜

The voice short code design in every deployment reflects this shift: by designing for users who cannot navigate a smartphone app, the deployments served all users through a channel that is universally accessible. 🟡 Amul Sarlaben's explicit targeting of women milk producers (majority of 3.6M), Bihar Krishi's 25% women farmer registration, and Ethiopia ATI's 14 million women target all reflect intentional inclusion design. 🟡

### B — Architecture Shifts

**B1 — Model Choice**
FROM: Using the most capable available model regardless of cost and data residency
TO: Choosing the model that is accurate enough for the domain, cost-sustainable at scale, and controllable by the institution ⬜

MahaVistaar's migration from Azure GPT-4.1 to fine-tuned Qwen3.5-27B is the clearest evidence: the fine-tuned model is more accurate on agricultural domain tasks (94% vs 91% on field evaluation sets) and costs 180× less per question. 🔵 The commercial model was not the right choice for scale, even though it was the easier choice for a pilot.

**B2 — Data Sovereignty**
FROM: Sending institution data to external AI services for processing
TO: Keeping institution data in place and sending only prompts to the AI layer ⬜

MahaVistaar's federated architecture is the primary evidence: only the prompt is sent to the LLM; raw institution data stays where it lives. 🔵 This decision resolved data sovereignty concerns across 25+ partner organisations without requiring multi-year data-sharing negotiation.

**B3 — Vendor Independence**
FROM: Single-provider dependency
TO: Dual-provider or multi-provider architecture with automatic failover ⬜

MahaVistaar's vLLM primary + Azure OpenAI fallback design, with 100-call cap per endpoint triggering automatic spillover, is the documented evidence. 🔵 This architecture maintains service availability if any single provider has an outage, and enables cost-driven migration without service disruption.

**B4 — DPG vs Instance**
FROM: Building a deployment-specific system that cannot be reused
TO: Building on or contributing to digital public goods that others can inherit ⬜

Ethiopia ATI's ability to launch in 3 months depends on the MahaVistaar components being reusable. 🟡 EkStep Foundation's role across multiple deployments reflects a deliberate DPG strategy: build once, adapt many times. The Beckn protocol integration in Bharat-VISTAAR provides interoperability across the hub-and-spoke federation.

### C — Institution Shifts

**C1 — Framing**
FROM: Framing AI deployment as a technology project with a defined end date
TO: Framing it as an institutional capability change with no end date ⬜

Not documented with specific named examples across deployments. The multi-year timelines and ongoing operational investment in MahaVistaar and Bihar Krishi suggest this shift has occurred in practice. ⬜

**C2 — Resistance and Non-Transferability**
FROM: Treating workforce and institutional resistance as a people problem to manage around
TO: Treating resistance as an information signal about what needs to change ⬜

Bihar Krishi's pre-launch training of 15,000+ extension workers reflects a decision to address resistance before it becomes a deployment blocker. 🟡 Whether specific resistance incidents were documented and how they were resolved is not available across other deployments.

**C3 — Institutional Knowledge**
FROM: Knowledge about the deployment residing in a few key individuals
TO: Knowledge embedded in documented systems, processes, and training materials that survive individual turnover ⬜

Not documented with specific named evidence across deployments.

### D — Ecosystem Shifts

**D1 — Ecosystem Design**
FROM: Contracting with vendors to deliver a system
TO: Assembling a network of peers with differentiated roles and shared stakes in the outcome ⬜

MahaVistaar's 54-organisation ecosystem, structured across four layers (Institutional and Governance, Technology and AI, Structured Data, Knowledge and Documents), is the clearest evidence. 🟡 No single organisation could have delivered this alone — not EkStep, not the Government of Maharashtra, not ICAR.

**D2 — Trust Source**
FROM: Institutional authority as the primary trust signal (government says this is reliable)
TO: Peer validation and demonstrated accuracy as the trust source (the farmer's neighbour got good advice from this) ⬜

Not documented with specific named evidence across deployments. The 98.5% positive feedback in MahaVistaar suggests peer-to-peer trust amplification is occurring, but the mechanism is not documented. 🟡

**D3 — Coordination Mechanism**
FROM: Hierarchical coordination (one organisation directs all others)
TO: Protocol-based coordination (shared standards allow autonomous actors to coordinate without a single director) ⬜

Bharat-VISTAAR's hub-and-spoke federation, with each state deployment retaining autonomy while connecting to a national layer, reflects this shift. 🟡 The Beckn protocol provides the technical coordination mechanism.

**D4 — Network Operator**
FROM: No one holding the network together (everyone assumes someone else is)
TO: An explicit network operator role with defined responsibilities and authority ⬜

The network operator role is documented as a structural requirement in the Shifts framework but is not attributed to a specific named individual or organisation in any of the five deployments in available documentation. This is a cross-deployment gap.

### E — Workforce Shifts

**E1 — Training Timing**
FROM: Training field staff after the system is live (they learn as it rolls out)
TO: Training field staff before the system is live (they encounter it as expert users, not surprised recipients) ⬜

Bihar Krishi's pre-launch training of 15,000+ extension workers across 38 districts is the primary evidence for the value of this shift. 🟡 The contrast is implied across other deployments where training timing is not documented — absence of documentation may reflect that this decision was not made consciously.

**E2 — Training Depth**
FROM: Training on how to use the system (button-pressing)
TO: Training on what the system is for, what it cannot do, and how to handle its failures ⬜

Not documented with specific evidence across deployments.

**E3 — Agency Test**
FROM: Field staff are passive relayers of AI outputs
TO: Field staff exercise judgement about when to use AI outputs, when to override them, and when to escalate ⬜

Not documented with specific evidence across deployments.

### F — Operating Model Shifts

**F1 — Velocity**
FROM: Long planning cycles before any deployment decision
TO: Committing to a launch date and working backward, accepting that some things will not be ready ⬜

Ethiopia ATI's 3-month commitment-to-launch timeline is the clearest evidence. 🟡 The compression was possible because the team committed to a date and then made sequencing decisions about what was essential for launch versus what could follow. Whether this produced quality trade-offs that became problems later is not documented.

**F2 — Governance**
FROM: Governance designed to prevent failure (risk minimisation)
TO: Governance designed to detect and recover from failure quickly (resilience design) ⬜

Not documented with specific named evidence across deployments.

**F3 — Sustainability**
FROM: Funding model dependent on external grants with no path to institutional sustainability
TO: Funding model embedded in the institution's core budget or revenue model ⬜

Amul Sarlaben's cooperative economics provide inherent sustainability alignment: improved cattle health and milk yield directly improve Amul's supply and producer income. 🟡 Government deployments (MahaVistaar, Bharat-VISTAAR, Bihar Krishi) depend on government budget lines or civil society funding, creating a different sustainability challenge.

**F4 — Pilot to Deployment**
FROM: Pilot as a bounded experiment that ends with a decision to proceed or not
TO: Pilot as a scaled learning environment that becomes production when it has earned the right to ⬜

MahaVistaar's progression from early pilot to 342,000+ users and 440,000 queries/month reflects this shift in practice — there is no documented single "go to production" decision; the deployment grew into production. 🟡

## What This Means for a Next Adopter

These 21 shifts are not a checklist to complete sequentially. They represent orientation decisions that need to be made at different points in the deployment journey. The most consequential shifts for a deployer in the early stages are A1 (problem framing), A2 (data posture), B2 (data sovereignty), C1 (institutional framing), and D4 (network operator). These are the decisions that are hardest to reverse once made.

For a deployer at pilot stage, the most consequential shifts are E1 (training timing) and F1 (velocity). Pre-deployment workforce training (Bihar Krishi's model) is significantly cheaper than post-launch resistance management. Commitment to a launch date (Ethiopia ATI's model) produces a different quality of preparation than open-ended readiness assessment.

For a deployer at scaling stage, F3 (sustainability) is the highest-stakes decision. A deployment that has grown on grant funding and has not identified a path to institutional budget or revenue-model sustainability will stall at a predictable point — usually at the second or third funding cycle renewal.

## Open Questions

Whether the FROM posture in each shift reflects an active decision or simply an absence of awareness of the alternative is not documented. Understanding this distinction would help a next adopter know which shifts require persuasion and which require only awareness.

The network operator shift (D4) is consistently unresolved in available documentation. A next deployment that clearly documents who held this role and what it actually involved would significantly strengthen this evidence base.

Whether the shifts are sequentially dependent — whether some must happen before others can — is an open question that the current evidence cannot definitively resolve.
