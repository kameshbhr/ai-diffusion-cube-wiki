# Dimension 1: Problem Orientation

**One-line:** What you build on — the specific problem, for whom, and what success looks like from the end user's point of view.

---

## What this dimension covers

Problem orientation is the foundation on which every other dimension rests. A deployment that gets this wrong cannot be saved by good architecture or a capable institution.

- **A1 — Problem framing:** The specific problem being solved, for whom, why the current system does not solve it, and what success looks like from the end user's point of view. Not the deployer's theory of change — the user's lived experience of the gap.
- **A2 — Data posture:** What data exists, where it lives, who controls it, and whether it can be connected (not necessarily cleaned). Data availability is often the binding constraint — but the binding constraint is access, not quality.
- **A3 — Existing assets:** What is already in place — prior pilots, legacy systems, databases, institutional processes, community structures — that can be built on or must be worked around.
- **A4 — Proof mechanism:** How the deployment will demonstrate that it works, at what threshold of evidence, for which audiences. Proof requirements differ across funders, governments, and field workers.

**Open question (potential A5):** Inclusion design — whether the system is built for the person with the least access (voice-first, feature phone, low literacy) rather than the median user. Field evidence suggests this is independently variable from A1-A4. See [inclusion-architecture](../concepts/inclusion-architecture.md).

---

## What the wiki currently holds

One foundational source: "The Six Orthogonal Shifts - detailed version 2" (AI Diffusion Pathways initiative). This provides FROM→TO operational formulations for A1-A4, field evidence from MahaVISTAAR (Maharashtra), Amul/Sarlaben, Ethiopia/ATI, Bihar Krishi, and the AI Commons curation exercise.

---

## Key patterns across pathways

**A1 — Problem framing:**
🟡 More than half of the builders whose 67 AI impact stories were curated for the AI Commons could not articulate their own problem statement — it had to be written for them after interviews. The pathway's first function, before presenting solutions, is helping the adopter formulate their problem.

🟡 Specificity drives adoption. In MahaVISTAAR, 205,000 crop/pest queries per month is evidence that when the problem is framed at the right granularity ("leaf curling in chilli — what to do?"), adoption takes care of itself. The test: can you name the specific question the specific person is asking today?

🟡 The system's categories must match the user's mental model, not the deployer's organisational chart. Grouping use cases by what farmers are trying to do (asking about a sick animal, checking scheme eligibility, tracking an application) produces a more adoptable architecture than grouping by technical taxonomy.

⬜ Problems come in two modes — inbound (user comes with a question) and outbound (system anticipates a need). See [inbound-vs-outbound-problem-modes](../concepts/inbound-vs-outbound-problem-modes.md). MahaVISTAAR's shift from inbound to outbound (17 lakh proactive daily alerts) is where the system moved from useful to indispensable.

**A2 — Data posture:**
🟡 The unlock is access, not quality. In MahaVISTAAR, departments had APIs that had existed for years but had never been called. The connection itself was the intervention — no data cleaning was required to start.

🟡 Waiting for perfect data before deploying is waiting for a reason that will never arrive on its own. AI reveals what data actually is: in Maharashtra, officials asked "whose data is right?" for the first time once AI connected databases that had never been queried together.

🟡 Data flows in both directions: the system returns anonymised, aggregated signals back to institutions (which advisories are being accessed, which crops have insufficient guidance, which regions show stress). AI creates a feedback loop that improves institutional data over time.

⬜ Two decisions sit within data posture that adopters must resolve early: federate vs. aggregate, and opt-in/consent-based vs. pre-loaded. See [federate-vs-aggregate-data](../concepts/federate-vs-aggregate-data.md).

**A3 — Existing assets:**
🟡 Every deployment that moved fast started with an inventory, not a specification. Maharashtra had fragmented advisory platforms, university databases, weather services, and market data — all working in isolation. The feasibility question was not "what do we need?" but "what can be joined?"

🟡 Asset readiness varies significantly. Amul brought 2 billion procurement transactions, 50 years of cooperative data, and 1,200+ veterinary doctor records — enabling a 3-week deployment. Ethiopia had limited digital advisory infrastructure — the same pathway worked but the first step differed. The question: where on the readiness gradient does your existing asset base sit, and what is the minimum viable starting set?

**A4 — Proof:**
🟡 Proof must be product-independent. The moment you tie it to one vendor's platform, you have proved that their product works, not that the approach works.

🟡 Two proof types are necessary: demonstration proof (triggers the decision to start) and experiential proof (creates the internal champion). See [proof-types-demonstration-experiential](../concepts/proof-types-demonstration-experiential.md). The Amul CEO's conversion happened because he saw AI working on his own data, not through a slide deck.

🟡 The most powerful proof is the compression sequence: 9 months (MahaVISTAAR) → 3 months (Ethiopia) → 3 weeks (Amul). The claim is not "the system works" but "the pathway makes each next adoption faster." See [compression-sequence](../concepts/compression-sequence.md).

---

## Key decisions an adopter faces

| Decision | What the evidence shows |
|---|---|
| How specific should the problem be? | Name the specific person and the specific question they are asking today. "We want to use AI in agriculture" is not enough. "Leaf curling in chilli — what to do?" is. |
| Should we clean data before deploying? | No. Connect first, deploy, let AI reveal what data actually is. Cleaning demand follows deployment. |
| What is our minimum viable starting asset? | Map what exists before specifying what to build. Every department has a database. The question is what can be joined. |
| What counts as adequate proof? | Working demonstration with real users in a real setting, product-independent. Demonstration proof first, then experiential proof for the internal champion. |
| Inbound or outbound, or both? | Start with inbound (answer questions users bring), but design for outbound (anticipate needs). The shift to outbound is where scale and indispensability emerge. |

---

## Common failure modes

- **Cannot articulate the problem statement.** More than half of builders in the AI Commons curation exercise could not do this. If the pathway provider or adopter cannot name the specific person whose life gets better and explain how, they are not ready to build.
- **Waiting for perfect data.** Leads to indefinite delay. The data question should be "what exists across silos and can we connect it?" not "is it clean enough?"
- **Building for the wrong user.** A system designed for smartphone-literate users in data-connected areas will not reach the people with the greatest need. See [inclusion-architecture](../concepts/inclusion-architecture.md).
- **Vendor-specific proof.** Ties the adopter's credibility to one vendor's platform rather than demonstrating that the approach works independent of any vendor.

---

## Pathways in this dimension

- [mahavistaar](../deployments/mahavistaar.md) — A1 (problem framing at right granularity, inbound→outbound); A2 (data connection without cleaning); A3 (API inventory); A4 (multi-institutional proof)
- [amul-sarlaben](../deployments/amul-sarlaben.md) — A3 (deep existing asset base enabling 3-week deployment); A4 (experiential proof via CEO conversion)
- [ethiopia-ati](../deployments/ethiopia-ati.md) — A3 (limited starting assets, same pathway); A4 (cross-country proof)

---

## Gaps

- No pathway currently documents A2 (data posture) from the perspective of an adopter with poor-quality data (as opposed to siloed-but-existing data). The Malawi case (67 health databases, all unconnected) is referenced but not documented.
- Proof mechanisms for non-agriculture sectors (health, education) are not yet documented.
- Inclusion design (potential A5) lacks a dedicated pathway — only deployment-level observations exist.
