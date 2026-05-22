# Dimension 6: Operating Model

**One-line:** What makes it last — how a deployment sustains itself beyond the pilot through governance, performance tracking, and course correction.

---

## What this dimension covers

Most AI deployments succeed as pilots and fail at scale. The operating model dimension is about what happens after the proof of concept.

- **F1 — Velocity:** How fast the deployment moves through its cycles. Speed and scale are the best insurance against the negative coalition that will inevitably develop to stop anything new. Velocity also operates across deployments — each successive adoption should be faster.
- **F2 — Governance:** Who makes decisions, at what level, with what authority, and with what accountability. Governance is not the enemy of speed — it is the condition for sustainable speed.
- **F3 — Sustainability:** How the deployment is funded beyond the initial grant or programme. If the funding model is unclear, the project is already dead.
- **F4 — Pilot to deployment:** What changes as a deployment moves from pilot to full scale. Everyone can do a pilot. Pilots have project funding, excited volunteers, and weekly check-ins. Deployments have none of those.

---

## What the wiki currently holds

Two sources ingested:
1. "The Six Orthogonal Shifts - detailed version 2" (AI Diffusion Pathways initiative) — Strong field evidence on F1, F3 cost data, F4 pilot failure modes. Sector: agriculture.
2. "Blue Dots AI — An AI Diffusion Pathway for Livelihoods" (Tushar Bansal, EkStep Foundation, May 2026) — New F3 pattern (cold start → private actor self-sustainability); new F1 pattern (facilitation team weekly rhythm); livelihoods compression sequence (10 months → 4 months). Sector: livelihoods.

---

## Key patterns across pathways

**F1 — Velocity:**
⬜ Speed and scale are the best insurance against the negative coalition that will inevitably develop to stop anything new. The reformer has enemies in all those who profit from the old order. The best insurance is visible results before the opposition organises.

⬜ Velocity cadence: within a day of someone approaching you, send them a package. Within a week, they should be running a pilot. Within three months, you should know if it works.

🟡 The Amul plus-one pattern: start with Sarlaben advisory, then add AI-based booking for artificial insemination (a small plus-one on what already exists), then microcredit via the cooperative bank, then Bharat Taxi via open network protocols. Each step builds on existing readiness. Never plus-ten.

🟡 Velocity also operates across deployments: 9 months (MahaVISTAAR, pioneer) → 3 months (Ethiopia, first international adopter) → 3 weeks (Amul, cooperative with existing data infrastructure). In the livelihoods track: 10 months (Dharwad, pioneer) → 4 months (Ghaziabad, second district). See [compression-sequence](../concepts/compression-sequence.md).

🟡 Proactive push is a velocity accelerator at the user level. MahaVISTAAR's proactive voice alerts reach 17 lakh farmers daily. The design question: how quickly can you shift from pull (farmer calls you) to push (you call the farmer)?

🟡 **Facilitation team rhythm as a velocity dimension (livelihoods):** In the Blue Dots AI deployments, the District Facilitation Team (6–8 people) maintains weekly discovery rhythm — identifying aggregators, tracking Blue Dot freshness, prompting stalled participants. This ongoing operational cadence is a velocity mechanism: without it, Blue Dots go stale, both sides lose confidence, and discovery reverts to pre-infrastructure patterns. "A live map requires a live rhythm." The velocity question in livelihoods discovery is not how fast to launch but how consistently to maintain. Source: Tushar Bansal, EkStep Foundation, May 2026. 🟡

**F2 — Governance:**
⬜ Governance is not the enemy of speed. It is what lets you scale without stopping to fix things that should have been right from the start. Going fast without governance is going fast towards a wall.

⬜ The same officials who share sensitive data on WhatsApp will cite privacy concerns to block a properly governed AI system. The solution is better governance, not no deployment.

🟡 Procurement is where many deployments die before they start. Government procurement was built for buying hardware and hiring body shops. It was not designed for buying AI capabilities that evolve monthly. RFP specifications become obsolete before the contract is signed. 70% of government respondents say digitalization takes four years from idea to first beneficiary benefit — much of that delay sits in procurement. Procurement reform is a governance dimension, not a separate problem.

⬜ Governance of AI safety is an architectural concern, not just a policy one. An independent moderation layer (500 adversarial attack patterns, domain validation, prompt injection defence) ensures unsafe outputs are caught before they reach the user — not just addressed by policy after the fact.

**F3 — Sustainability:**
🟡 Setup cost: approximately $250,000. Annual maintenance cost: approximately $250,000. Source: AI Diffusion Pathways initiative (reported figure; exact derivation not documented in source).

🟡 Total cost of ownership for AI at population scale is two to five times the number in the original proposal. 

🟡 Maintenance cost breakdown:
- Model inference costs: drop as you switch to open-source and cache common queries
- Telephony and data transfer costs: operational and relatively fixed
- Enterprise service cost: drops as DPG components replace custom-built modules

🟡 The financing model for at-scale diffusion is not "N pathways × $250,000." It is a declining marginal cost curve. The first twenty pathways cost roughly $5 million total; the next twenty cost significantly less because the reusable infrastructure is already in place.

🟡 National-layer amortisation shifts the economics: Bharat-VISTAAR's Rs. 150 crore allocation creates a national layer that amortises infrastructure costs across all state nodes. Maharashtra does not bear the full cost of the knowledge base, AgriStack, or ICAR integration — those sit at the national level.

🟡 **Cold start → self-sustaining economics (livelihoods):** The Blue Dots AI deployments document a specific F3 pattern for two-sided discovery marketplaces. Before private actors have a reason to join (before there is sufficient density of verified participants), government or philanthropic funding must cover the cold start period: facilitation team salaries, voice AI setup, and aggregator mobilisation for the first 12 months. Once density is reached and innovators are active, the ecosystem generates its own economic value and does not require continuous subsidy. In Dharwad and Ghaziabad, the cold start threshold was reached within the first three months of aggregator mobilisation. The unit economics: a ₹10 voice interaction surfaces a worker who generates ₹1 lakh in annual local economic activity — the ROI case for the funder is straightforward once the numbers are named. Source: Tushar Bansal, EkStep Foundation, May 2026. 🟡

⬜ The 12-month funded commitment is a minimum threshold, not a guarantee. Timeline to private actor self-sustainability depends on district density targets, aggregator engagement speed, and the local private sector's appetite for verified candidate pools. Dharwad and Ghaziabad are the only documented reference points; both are in India. Whether this timeline holds in lower-density or lower-SMB-density districts is not yet documented.

**F4 — Pilot to deployment:**
⬜ Pilot has project funding, excited volunteers, and weekly check-ins. Deployment has none of those. If the operating model is "same as the pilot but bigger," it will fail.

⬜ No widely accepted template for "how to run AI in government" exists. Every organisation invents its own, makes its own mistakes, learns its own lessons. The knowledge does not transfer because the institutional mechanisms for transfer do not exist. That is the gap the diffusion pathway must fill.

⬜ The pilot's output is not a working system — it is a set of learnings that inform the deployment design. An eight-week pilot followed by structured review, before any decision on scaling. Those who treat the pilot as a vanity launch find the compounding stops there.

⬜ Write the operating manual for year three before you write the pilot plan for month one. Who handles bugs on a Tuesday morning? Who decides when the model needs retraining? Who trains the trainers for the next posting cycle? If these questions are not answered before you start, you have built a demo that will be switched off the moment the project champion moves to a different posting.

---

## Key decisions an adopter faces

| Decision | What the evidence shows |
|---|---|
| How fast to move? | Plus-ones, not plus-tens. Day 1: package. Week 1: pilot. Month 3: know if it works. Speed is insurance against the negative coalition. |
| How to design governance? | Design it before you go fast, not after. Governance is the condition for sustainable speed, not an obstacle to it. Include procurement in the governance design — this is where many deployments die. |
| What is the full cost of ownership? | Budget 2-5x the number in your original proposal. Setup ~$250,000; annual maintenance ~$250,000 (these are initiative-level figures — validate against your specific context). Costs decline with each successive deployment as DPG components replace custom modules. |
| What is the sustainability model? | Answer before you start. Who maintains in year three? Who pays for inference when the grant runs out? If you cannot answer these, the project is already dead. |
| How to design the pilot? | Eight weeks + structured review before any scaling decision. Pilot output is learnings, not a working system. Write the year-three operating manual before writing the pilot plan. |

---

## Common failure modes

- **Big launch.** Everyone can do a pilot. A deployment is not a scaled-up pilot — it is a different operating model. If you cannot describe what is different about how the deployment runs compared to the pilot, you have not done the design work.
- **Governance as obstacle.** Treating governance as something that slows things down produces deployments that move fast and break things that matter. Governance is the condition for sustainable speed.
- **Procurement as blocker.** An adopter can design good data protection, good quality benchmarks, and a good regulatory posture and still be blocked by a procurement cycle that authorises a model that is two generations old by the time the contract is executed. Procurement reform must be part of the governance design from the start.
- **"We'll figure out sustainability later."** If the funding model is unclear when the deployment starts, the deployment is already dead — it just doesn't know it yet. Technology evolution outpaces institutional adaptation; a model trained today may be obsolete in six months.
- **Treating the pilot as the point.** The pilot's output is learnings. Those who treat the pilot as a vanity launch find the compounding stops there.

---

## Pathways in this dimension

- [mahavistaar](../deployments/mahavistaar.md) — F1 (proactive push, 17 lakh daily alerts)
- [amul-sarlaben](../deployments/amul-sarlaben.md) — F1 (plus-one scaling pattern documented)
- [bharat-vistaar](../deployments/bharat-vistaar.md) — F3 (national-layer amortisation; Rs. 150 crore)
- [compression-sequence](../concepts/compression-sequence.md) — F1 velocity across deployments
- [blue-dots-dharwad](../deployments/blue-dots-dharwad.md) — F1 (10-month pioneer; aggregator-led density acceleration); F3 (cold start → private actor self-sustainability within 3 months)
- [blue-dots-ghaziabad](../deployments/blue-dots-ghaziabad.md) — F1 (4-month activation; compression from Dharwad); F3 (state scaling to multiple districts)

---

## Gaps

- F4 is the most important and most under-documented. No current source describes the specific transition process from pilot to deployment for any named deployment — what changed in team structure, governance, cost profile, or technical infrastructure.
- F3: the $250,000 / $250,000 figures are initiative-level estimates. No deployment-specific cost breakdown is documented. The livelihoods cold start cost (facilitation team + voice AI + aggregator mobilisation for 12 months) is similarly not broken down with numbers.
- F2: governance structure at the deployment level (who makes decisions, at what authority level, with what accountability) is not documented for any specific deployment in current sources. The District Facilitation Team's governance mechanisms in Blue Dots AI are described at the operational level but not at the decision-authority level.
- F1: the "negative coalition" pattern — who resists, when, and how it was overcome — is named conceptually but not documented with deployment-specific evidence. In Blue Dots AI, the facilitation team's rhythm-keeping function is documented, but resistance patterns are not.
- F3 livelihoods: what happens in districts where the private sector is too thin to reach self-sustainability — no documented evidence.
