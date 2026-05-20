# Dimension 2: Architecture

**One-line:** What you build with — the technology stack that keeps a deployment flexible, evolvable, and connected to existing systems.

---

## What this dimension covers

Architecture is the set of technical choices that determine whether a deployment can adapt as needs evolve, swap components as the market changes, and integrate with the legacy systems it must live alongside.

- **B1 — Model choice:** Which AI model(s) are used, why, and what the trade-offs are. Includes decisions about foundation models vs. fine-tuned vs. custom-built. Also includes the independent moderation layer — a separate model that performs domain validation, content safety filtering, and prompt injection defence.
- **B2 — Data sovereignty:** Where data lives, who controls it, and how the deployment handles sensitive data. The key principle: the orchestrating agent talks to the deployer's databases, pulls data, frames the prompt, and sends only the prompt to the LLM — raw data never leaves the deployer's systems.
- **B3 — Vendor independence:** How locked-in the deployment is to any single vendor. Open source, open protocols, open standards are survival strategies, not ideological preferences.
- **B4 — DPG vs. instance:** Whether the deployment is built as or on a Digital Public Good (open, replicable, forkable) or as a specific instance. Separation of reusable code from the deployment instance is what drives down cost and time for each successive deployment.

**Note on depth:** Field experience reveals a seven-layer system architecture beneath these four sub-components: user layer, interface layer, moderation layer, AI decision engine, knowledge/scientific models, live data sources, DPI foundation. An adopter will need architectural guidance at a level of detail that B1-B4 alone cannot provide. This is flagged as an open question in the framework — B1-B4 are the right Level 3 categories, but the depth beneath Shift B is greater than beneath other shifts.

---

## What the wiki currently holds

One foundational source: "The Six Orthogonal Shifts - detailed version 2" (AI Diffusion Pathways initiative). Provides FROM→TO formulations for B1-B4, with strongest field evidence from MahaVISTAAR (B2 data sovereignty model) and Amul/Sarlaben (B1 model evaluation).

---

## Key patterns across pathways

**B1 — Model choice:**
⬜ The frontier model race is irrelevant to most of the world's problems. The AI that exists today is adequate for agriculture advisories, health screenings, educational support, and government service delivery. The gap is not in model capability — it is in institutional readiness to use what is already available.

🟡 You don't choose one model. You choose at least two: one to moderate, one to advise, and they must be independent. The architecture needs a separate moderation layer — domain validation, content safety filtering, and prompt injection defence — decoupled from the advisory engine.

🟡 Model evaluation is as important as model selection. In Amul's deployment, fine-tuned smaller open-source models achieved 94% accuracy against 91% for larger commercial APIs on field evaluation sets. The right model is not the latest model — it is the model that performs best on adversarial test sets specific to your domain (up to 500 attack patterns documented).

🟡 The deployment topology decision — commercial API (variable cost, lower control) vs. self-hosted (fixed cost, full control) — carries cost, latency, and sovereignty implications that compound over time.

**B2 — Data sovereignty:**
🟡 The MahaVISTAAR implementation: the orchestrating agent talks directly to government databases, pulls the data, frames the prompt, sends only the prompt to the LLM. Raw data never leaves. This is described explicitly as a sovereignty decision, not a technical footnote.

🟡 "Prompt-level interaction protects data better than contracts do. If a vendor's architecture requires that your data be sent to their servers, they have designed a system that works for them, not for you."

🟡 Every claim in the system's response should be grounded in a verified source with attribution. The farmer does not receive an AI opinion — they receive institutional knowledge, delivered through an AI interface, with the source named. The institution's authorship stays visible in every answer.

🟡 External data sources and DPI foundations are accessed on demand — not pre-loaded into the model. Sovereignty is not just about where data resides; it is about when the AI accesses it.

**B3 — Vendor independence:**
⬜ Vendor capture happens when large technology companies have more sales engineers than most government departments have technologists. The information asymmetry is severe. After every pilot, the question to ask: who controls what scales? If the answer is one vendor, you have a dependency, not a deployment.

⬜ At the protocol level, open standards like Beckn allow standardised discovery and interaction across independent providers — vendor independence enforced through protocol design, not just contractual terms. Each layer should be designed so it can evolve independently: the AI model can be swapped without changing the data sources; the voice pipeline can be upgraded without changing the orchestration logic.

**B4 — DPG vs. instance:**
🟡 Ethiopia's 3-month deployment was possible because the architecture, governance frameworks, language pipeline methodology, data connector approach, model evaluation benchmarks, and failure mode library from MahaVISTAAR were all transferable assets. This is B4 in practice: the DPG components transferred; the instance was built for Ethiopia's context.

⬜ The DPG is not just code — it is code plus documented organisational knowledge (a collaboration blueprint covering governance models, enabler networks, and institutional arrangements). A DPG that insists on being deployed as a full stack is behaving like a vendor, not a public good. Reuse at the component level — not full stack — is what drives down the cost and time of each successive deployment.

⬜ When the line between building and deploying blurs, the system stalls on questions of liability and accountability. The code builder's accountability stops at the code. The deployer's accountability starts at the deployment. Drawing this line clearly is not a technical task — it is an institutional one.

---

## Key decisions an adopter faces

| Decision | What the evidence shows |
|---|---|
| Which model(s) to use? | Normal AI is good enough. Choose for domain accuracy on adversarial test sets, not for brand recognition. Require an independent moderation layer. |
| Commercial API vs. self-hosted? | Evaluate cost, latency, and sovereignty implications over time, not just at procurement. Open-source fine-tuned models have outperformed commercial APIs on domain-specific evaluation sets. |
| Where does data go? | Only the prompt should go to the LLM. The orchestrating agent accesses deployer databases, frames the prompt, sends only the prompt. Prompt-level interaction protects data better than contracts. |
| How to avoid vendor lock-in? | Open standards, open protocols. Design so each layer can evolve independently. After every pilot: who controls what scales? |
| What to contribute as a DPG vs. build as an instance? | Separate reusable code from the deployment. Document organisational knowledge as part of the DPG. Reuse at the component level. |

---

## Common failure modes

- **Waiting for a better model.** The gap is not in model capability but in institutional readiness. A better model is an excuse, not a strategy.
- **Choosing one model.** The architecture needs at least two (moderation + advisory), independent of each other.
- **Sending raw data to the model provider.** If a vendor's architecture requires your data on their servers, they have designed a system for them, not for you.
- **Single-vendor stack.** Creates a dependency that is hard to exit. Vendor capture is structural when the information asymmetry between large tech companies and government is severe.
- **Confusing building with deploying.** When the DPG builder also controls the deployment, liability and accountability blur, and the system stalls.

---

## Pathways in this dimension

- [mahavistaar](../deployments/mahavistaar.md) — B2 (federation model, only prompt to LLM); B3 (open protocol use); B4 (DPG as source for Ethiopia transfer)
- [amul-sarlaben](../deployments/amul-sarlaben.md) — B1 (model evaluation evidence: 94% vs 91%)
- [ethiopia-ati](../deployments/ethiopia-ati.md) — B4 (DPG component transfer enabling 3-month deployment)

---

## Gaps

- Seven-layer system architecture (user, interface, moderation, AI decision engine, knowledge/scientific models, live data sources, DPI foundation) is not yet documented with per-layer guidance. This is flagged as an open framework question.
- B3 vendor independence: field evidence of specific contracts or procurement structures used to enforce independence is not documented.
- B4: how DPG components are documented and made discoverable for next adopters is not described — what is in the "collaboration blueprint" beyond what this source names?
