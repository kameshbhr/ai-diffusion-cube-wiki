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
