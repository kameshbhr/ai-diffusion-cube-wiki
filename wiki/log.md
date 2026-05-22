# Wiki Log

Append-only chronological record of all operations.

---

## 2026-05-20 init | Wiki initialised | Pages created: 9 | Pages updated: 0

Starting state created per CLAUDE.md schema:
- wiki/index.md
- wiki/log.md
- wiki/overview.md
- wiki/dimensions/problem-orientation.md
- wiki/dimensions/architecture.md
- wiki/dimensions/institution.md
- wiki/dimensions/ecosystem.md
- wiki/dimensions/workforce.md
- wiki/dimensions/operating-model.md

No sources ingested. Awaiting first source in raw/.

---

## 2026-05-20 ingest | "The Six Orthogonal Shifts - detailed version 2" (AI Diffusion Pathways initiative) | Pages created: 14 | Pages updated: 9

**Source:** raw/AI Diffusion Pathways - The six orthogonal shifts across tech and non-tech for diffusion pathways.pdf (16 pages)

**What this source is:** Framework document providing FROM→TO operational formulations for all 21 sub-components across the six dimensions, with field evidence from five deployments: MahaVISTAAR (Maharashtra, pioneer, 9 months), Ethiopia/ATI (first international adopter, 3 months), Amul/Sarlaben (cooperative, 3 weeks), Bihar Krishi (state government, independent build), Bharat-VISTAAR (national layer). Also references Malawi (67 health databases, unconnected) and AI Commons (67 impact stories curated).

**Evidence quality in this source:** Specific numbers from named deployments 🟡; framework analysis and FROM→TO formulations ⬜; field accounts and quotes 🟡.

**Pages created:**
- wiki/deployments/mahavistaar.md
- wiki/deployments/bharat-vistaar.md
- wiki/deployments/amul-sarlaben.md
- wiki/deployments/bihar-krishi.md
- wiki/deployments/ethiopia-ati.md
- wiki/concepts/compression-sequence.md
- wiki/concepts/deploy-first-data-posture.md
- wiki/concepts/proof-types-demonstration-experiential.md
- wiki/concepts/network-operator-role.md
- wiki/concepts/federate-vs-aggregate-data.md
- wiki/concepts/inbound-vs-outbound-problem-modes.md
- wiki/concepts/inclusion-architecture.md
- wiki/people-orgs/ai-diffusion-pathways.md

**Pages updated:** wiki/dimensions/problem-orientation.md, wiki/dimensions/architecture.md, wiki/dimensions/institution.md, wiki/dimensions/ecosystem.md, wiki/dimensions/workforce.md, wiki/dimensions/operating-model.md, wiki/index.md, wiki/log.md, wiki/overview.md

**Key new knowledge:**
- Compression sequence (9 months → 3 months → 3 weeks) with named deployments
- Deploy-first data posture shift (access not quality; connection is the intervention)
- Two proof types (demonstration + experiential)
- D4 network operator: four institutional types documented; field failure case documented
- Cost data: ~$250k setup, ~$250k/year maintenance; declining marginal cost curve
- Total cost of ownership 2-5x original proposal
- Plus-one velocity pattern (Amul)
- Procurement as governance failure mode
- Agency test: both positive outcome and risk documented from Amul

**Open questions flagged in source:**
- Inclusion architecture: does not fit cleanly into B sub-components; proposed as potential A5
- Seven-layer system architecture is richer than B1-B4 captures (user, interface, moderation, AI decision engine, knowledge/scientific models, live data sources, DPI foundation)

**Significant gaps identified:**
- No standalone pathway pages (require direct provider contributions)
- F4 (pilot to deployment) most important underdocumented sub-component
- C2 (resistance) under-documented across all sources
- Non-agriculture sectors entirely absent
- F2 governance: procurement failure named but no solution pathway documented

---

## 2026-05-20 ingest | "OAN Diffusion Pathway — Package of Pathways" (EkStep Foundation, 2026) | Pages created: 2 | Pages updated: 9

**Source:** raw/OAN-DiffusionPathway.pdf — Type A reader document (frontline adopter orientation). Covers all five documented deployments as narrative and context: what farmers are actually doing on live systems; the structural problem the pathway addresses; who has walked it; the DPI+AI frame; the system architecture.

**Evidence quality:** Entirely 🟡 (reported-by-participant) and ⬜ (analytical/synthesis). No first-hand field observation 🔵 in this source. Numbers are attributed to named deployments.

**Pages created:**
- wiki/concepts/dpi-ai-frame.md
- wiki/concepts/seven-layer-architecture.md

**Pages updated:**
- wiki/deployments/mahavistaar.md — scale metrics (342k unique users, 1.67M questions, 791k sessions, 97%+/98.5% feedback, 440k total queries/month, 15 stage-based proactive advisories); short code 155313
- wiki/deployments/bharat-vistaar.md — ministry named (Ministry of Agriculture and Farmers Welfare); launch date (17 Feb 2026, Jaipur); PM Modi endorsement; 10 schemes listed; short code 155261; Saagu Baagu pilot evidence (21% yield increase, 9% pesticide reduction)
- wiki/deployments/amul-sarlaben.md — scale updated (3.6M vs prior 25 lakh — contradiction flagged); 18,500+ villages; 22M cattle; 1,400 vets; 1M+ downloads; short code 08035453545; PM Modi citation; expansion plans
- wiki/deployments/bihar-krishi.md — 850k+ registered farmers; May 2025 start; 38k+ scheme applications; 20-25% engagement; 20M reached; partners named (MicroSave Consulting, Gates Foundation); awards (ET DigiTech 2025 Gold, SKOCH 2025 Gold); Bihar node of Bharat-VISTAAR
- wiki/deployments/ethiopia-ati.md — ATI confirmed as national transformation institute (prior uncertainty resolved); launched Feb 2026; Fayda integration; 30M farmers targeted; 14M women; 8% income ambition; COP32 context; Digital Agriculture Roadmap 2025-2032; Addis Ababa socialisation workshop
- wiki/concepts/inclusion-architecture.md — major update: Nilekani quote; "voice is not a feature, it is the architectural response"; short codes for all deployments; voice-dissolves-barriers framework
- wiki/concepts/inbound-vs-outbound-problem-modes.md — new data: 440k total queries/month; 15 crop-calendar proactive advisories; third mode (participatory/crowdsourced) noted as emerging
- wiki/index.md — updated all deployment summaries; added two new concept entries
- wiki/log.md — this entry

**Key new knowledge:**
- DPI+AI frame: precise definition of what DPI is, what AI adds, and why their separation is an architectural requirement (not a design preference)
- Seven-layer system architecture fully documented for the first time (previously flagged as gap)
- Moderation layer (Layer 3) formally documented: independent model, decoupled from advisory engine, adversarial test sets of 500+ patterns
- "No tool = no answer; no source = no claim" guardrail documented as Layer 4 Tool Orchestration design principle
- GPU compute as primary cost driver; transition from commercial APIs to self-hosted open-source models as the key infrastructure decision ahead
- Voice as structural inclusion solution (not a feature): "Voice is not a feature of the OAN pathway. It is the architectural response to the inclusion problem." — Nandan Nilekani quote documented
- Bihar Krishi: "built first on its own terms, then connected" — path distinct from other deployments; OAN amplified what existed
- Bharat-VISTAAR: Saagu Baagu pilot (21% yield increase, 9% pesticide reduction for cotton in Telangana) as the evidence base for the national design

**Contradiction flagged:**
- Amul scale: prior source said "25 lakh" (2.5M); this source consistently says 3.6M. Both figures recorded in deployment page. Possible explanation: 2.5M = active/registered users; 3.6M = full cooperative membership. Unresolved.

**Pathway pages built (approved by user):**
- wiki/pathways/voice-first-access-design.md
- wiki/pathways/federated-data-architecture.md
- wiki/pathways/institution-as-authority-trust.md
- wiki/pathways/enabler-ecosystem-assembly.md

**Pathway proposals declined:**
- Pathway 4 (inbound-to-outbound transition): evidence audit found end-state description only — no decisions, challenges, or comparative outcomes documented. Not sufficient for a pathway page.
- Pathway 5 (farmer capability progression): lacks cross-deployment evidence to qualify as a pathway or concept page.

**Gaps still open after this ingest:**
- Training depth (E1/E2) for all five deployments: this source adds no new evidence
- Governance structure (F2): no new detail in any deployment
- Failure modes / frictions: this source is explicitly not a case study and names no specific failures beyond what previous source documented
- Ethiopia actual usage data: 30M is targeted, not measured
- F4 (pilot to deployment) remains underdocumented

---

## 2026-05-21 ingest | "Blue Dots AI — An AI Diffusion Pathway for Livelihoods" (Tushar Bansal, EkStep Foundation, May 2026) | Pages created: 4 | Pages updated: 12

**Source:** raw/[Internal] AI Diffusion Pathway for Blue Dots in Livelihoods.pdf (12 pages)

**What this source is:** Deployment pathway document for the Blue Dots AI platform — shared digital discovery infrastructure for district-level livelihoods. Covers two pilot districts: Dharwad (Karnataka, pioneer, 2024) and Ghaziabad (Uttar Pradesh, second district). Also names Uttar Pradesh and Karnataka as scaling to multiple districts (2025–26). Sector: livelihoods / district economy — the first non-agriculture source ingested into this wiki.

**Contributor confirmed:** Tushar Bansal, EkStep Foundation. This source also explicitly names EkStep Foundation as the institution behind the AI Diffusion Pathways initiative — resolving the attribution uncertainty flagged in the 2026-05-20 ingest.

**Evidence quality in this source:** Specific numbers from named deployments 🟡; framework analysis and deployment architecture ⬜; direct quotes from source document 🟡. No first-hand field observation 🔵 in this source — all evidence is participant-reported or analytical.

**Pages created:**
- wiki/deployments/blue-dots-dharwad.md — Dharwad district, Karnataka; pioneer livelihoods deployment; 10 months to self-sustaining ecosystem
- wiki/deployments/blue-dots-ghaziabad.md — Ghaziabad district, UP; second deployment; 4 months to activation; 10,000+ jobs visible from <10% SMB coverage
- wiki/concepts/paradox-of-proximity.md — Local discovery failure framework; supply and demand in proximity but cannot find each other; Ghaziabad evidence
- wiki/concepts/ecosystem-aggregator-model.md — Mass onboarding via existing institutions; two-sided density without person-by-person mobilisation; Dharwad evidence

**Pages updated:**
- wiki/concepts/compression-sequence.md — Added livelihoods track (Dharwad 10mo → Ghaziabad 4mo); distinguished from agriculture track; noted parallel nature of two sequences
- wiki/concepts/inclusion-architecture.md — Added Blue Dots AI evidence: 2–3 min voice call on any phone; ₹500+ → ₹10 cost shift; livelihoods sector extension
- wiki/concepts/dpi-ai-frame.md — Added Blue Dots AI as DPI for livelihoods (UPI analogy explicitly stated in source); introduced participant-created consent-governed data as third architecture pattern alongside federate/aggregate
- wiki/concepts/network-operator-role.md — Added District Facilitation Team + District Champion as fifth institutional type; documented distinction between Champion (names deployment) and Facilitation Team (maintains rhythm); "this runs in my name" phrase formally documented
- wiki/people-orgs/ai-diffusion-pathways.md — Confirmed EkStep Foundation attribution; added Tushar Bansal as named contributor; added Blue Dots deployments; noted livelihoods sector extension
- wiki/dimensions/problem-orientation.md — Added paradox-of-proximity pattern under A1; added livelihoods deployments to pathways section; updated gaps
- wiki/dimensions/ecosystem.md — Added ecosystem aggregator model under D1; added District Champion/Facilitation Team refinement under D4; added Blue Dots deployments; updated gaps
- wiki/dimensions/operating-model.md — Added cold start → self-sustaining F3 pattern; added facilitation team rhythm as F1 velocity mechanism; added livelihoods compression to F1; updated gaps
- wiki/index.md — Added new deployment and concept entries; reorganised deployments by sector

**Key new knowledge:**
- First non-agriculture sector documented: livelihoods / district economy
- Paradox of proximity: local discovery failure as root cause of jobs/skills crisis in Indian districts
- Blue Dots AI platform: shared digital discovery infrastructure via voice (any phone, any language, 2–3 min)
- Ecosystem aggregator model: two-sided density building via existing institutions; Dharwad evidence (300+ employers in 2 weeks from one MSME association; 500+ seekers from one ITI)
- Cold start → self-sustaining economics: 12-month funded commitment; threshold reached in 3 months in Dharwad and Ghaziabad
- District Facilitation Team (6–8 people) as operational spine: rhythm keeper, distinct from District Champion
- "This runs in my name" phrase formally documented as the anchor-adopter test
- EkStep Foundation confirmed as institution behind AI Diffusion Pathways initiative (resolves prior uncertainty)
- Parallel compression sequence in livelihoods sector: 10 months → 4 months (different mechanism from agriculture track)
- Economic case quantified: ₹1,050 crore/year GDP addition per district from 5% workforce participation improvement; ₹87,500 crore across 100 districts
- Four DPGs documented: Signal DPG, Aggregator DPG, Facilitator DPG, AI Diffusion DPGs (7 open-source building blocks)
- DPDP 2023 compliance as architectural property, not post-facto audit
- Digitally verifiable credentials for Blue Dots: participants can be verified in seconds

**Contradictions with existing pages:** None found. Blue Dots AI evidence is additive, not contradictory, to existing pages. The participant-created data architecture in Blue Dots AI is a new pattern alongside (not contradicting) the federate-vs-aggregate concept from agriculture deployments. Flagged in dpi-ai-frame.md.

**Pathway pages built (approved by user — pathways 1, 2, and 4 of the four proposed):**
- wiki/pathways/local-discovery-infrastructure.md — Full Blue Dots AI approach; A1, A4, B1–B4, D1–D4, F1, F3
- wiki/pathways/aggregator-led-density-building.md — D1/D3/D4; aggregator-led mass onboarding; Dharwad evidence
- wiki/pathways/consent-based-participant-data.md — B2/B3/F2; participant-owned consent-at-creation data architecture; DPDP 2023

**Pathway proposal declined:**
- Pathway 3 (Cold start to self-sustaining ecosystem): user did not select. Evidence in this source folds into F3 sections of local-discovery-infrastructure.md and the operating-model dimension page.

**Open questions / gaps identified:**
- E1–E3 (workforce/training) for both Blue Dots deployments: not documented at all
- C2 (resistance) in livelihoods context: not documented
- F2 governance specifics for District Facilitation Team: not documented
- A2/A3 (data posture, existing assets) for district-economy deployments: not documented
- D2 (trust source) in livelihoods: why do job-seekers and SMBs trust Blue Dots? Not documented
- What happens when no strong aggregator exists on one side of a use case: not documented
- F3 livelihoods: cold start sustainability in low-density districts outside India: not documented
- F4 (pilot to deployment) remains underdocumented across all sectors
