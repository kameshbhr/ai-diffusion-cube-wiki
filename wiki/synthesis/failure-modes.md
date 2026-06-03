# Failure Modes

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bihar Krishi, Ethiopia ATI, Blue Dots AI, Bharat-VISTAAR
**Last updated:** 2026-06-02

## The Pattern

Deployments fail in predictable ways. The failure modes documented here are not hypothetical — they are named patterns derived from field evidence across the deployments in this wiki, including cases where deployments anticipated and avoided a failure mode, and cases where they encountered it directly. The catalogue is not exhaustive; it reflects what the available evidence reveals. Each failure mode is named to make it recognisable in the field before it fully develops.

Most documented failure modes sit in the non-technology dimensions. Architecture failures happen, but they tend to be recoverable — a data integration that stalled, a vendor constraint that required a workaround. The failure modes that end deployments tend to be institutional: the network operator role is vacant, the political cover disappears, the workforce is not trained in time, or the operating model assumes funding that does not materialise. This distribution is consistent with the 70/30 observation: 70% of the failure surface is non-technical.

## Failure Modes by Dimension

### A — Problem Orientation Failures

**Technology-push deployment.** The AI is deployed because it is available, not because a specific user need has been identified and confirmed. Symptoms: low uptake despite working technology; farmer or user queries that reveal the system was built for a different problem than users actually have; usage metrics not linked to any outcome the user cares about. The preventive shift is to start with the problem framing, not the technology inventory.

**Assumed data readiness.** The deployment plan assumes data is available that does not exist, is not accessible, or is in a form that requires transformation before use. Symptoms: deployment timeline extends before users are reached; data access negotiations consume resources planned for deployment; the system launches with a smaller knowledge base than planned. MahaVistaar documented dialect variation in the Marathi corpus as an unanticipated data quality issue that required specific resolution. The preventive shift is to conduct a data audit before finalising the deployment plan.

### B — Architecture Failures

**Vendor lock-in.** The deployment is built on a single vendor's infrastructure — a proprietary AI model, a closed data platform, a single cloud provider — in a way that makes migration prohibitively expensive. Symptoms: cost escalation that the deploying institution cannot sustain; inability to respond to vendor policy changes; political resistance to institutional dependence on a foreign technology vendor. MahaVistaar's dual-provider topology (self-hosted primary, Azure fallback) was designed specifically to avoid this pattern. The preventive shift is to use open-source DPGs, open protocols (Beckn), and open standards from the start.

**Staleness cascade.** The AI's knowledge base is not updated when underlying data changes — crop advisories become outdated, scheme eligibility rules change, weather data feeds go stale. Users receive confident but incorrect answers. Symptoms: farmer complaints about wrong advice; extension workers correcting AI outputs routinely; uptake decline after an initial period. The OAN architecture's real-time data connection (rather than batch-loaded snapshots) was designed to prevent this. The preventive shift is to distinguish between knowledge that changes slowly (ICAR advisory corpus) and data that changes rapidly (weather, market prices, scheme status) and connect to fast-changing data in real time.

**Harmful output reaches user.** The AI produces wrong, harmful, or misleading advice — incorrect pesticide dosage, wrong scheme eligibility, misinformation about a treatment — and a farmer acts on it. The severity depends on the domain: wrong crop advisory can cost a season; wrong veterinary or medical advice can cause harm. MahaVistaar and Amul Sarlaben both use an independent moderation layer (a separate AI model reviewing outputs before they reach farmers). The preventive architecture is moderation-before-output, not review-after-complaint.

### C — Institution Failures

**Non-transferability.** Deployment knowledge is held by one or two individuals on the deployment team and is not codified. When those individuals move, the knowledge is lost and the deployment stalls. The preventive shift (documented from MahaVistaar's pioneer experience and applied in subsequent deployments) is to codify architecture, governance frameworks, failure modes, and deployment playbooks explicitly during the build — not as an administrative afterthought.

**Pilot-forever trap.** The deployment is framed as a pilot and evaluated as a pilot, with no agreed transition pathway to sustained operations. Funding runs out, the team disbands, the system is not maintained, and what was working is lost. Symptoms: repeated "we need to extend the pilot" conversations; no institutional owner for steady-state operations; metrics focused on deployment activity rather than user outcomes. The preventive shift is to establish the operating model and institutional ownership before the pilot begins, not after it ends.

**Political dependency.** The deployment depends on a single political champion — a minister, a secretary, a senior official — whose transfer or departure takes the deployment's political cover with it. Symptoms: sudden slowdown or pause in approvals when key official changes; procurement and funding stalls that did not exist before; institutional partners withdraw without the champion's presence. The preventive shift is to embed the deployment in a multi-year roadmap or budget commitment (Bihar's 4th Agriculture Roadmap, Ethiopia's Digital Agriculture Roadmap 2025–2032, Bharat-VISTAAR's Union Budget allocation) before the champion changes.

### D — Ecosystem Failures

**Absent network operator.** No single organisation is accountable for saying "this runs in my name." The deployment is structured as a consortium of equal partners. Symptoms: accountability diffuses when something goes wrong; no one can make decisions quickly; partners are not aligned on what the system is for; deployment timeline extends indefinitely. ATI's national mandate was specifically cited as the enabler for Ethiopia's three-month deployment — without a network operator that could align Ministry of Agriculture, meteorological services, and research institutes, the timeline would have been much longer. The preventive shift is to identify the network operator before the deployment begins.

**Partner commitment decay.** Ecosystem partners whose participation was strong at the start reduce their commitment over time — data feeds are not maintained, validation inputs are not provided, coordination meetings are not attended. Symptoms: knowledge base becomes stale as partner data stops flowing; deployment team spends increasing time on partner management rather than deployment improvement; outputs quality declines. The preventive shift is to design partner commitments with explicit, maintained incentive alignment — not to assume goodwill is sufficient.

**Conflicting mandates.** Two or more partners have mandates that pull in different directions — a data-sharing requirement from one partner conflicts with a data sovereignty principle held by another; a farmer outcome metric held by the deployer conflicts with a usage metric held by a funder. Symptoms: decisions stall at the point of conflict; the deployment team is caught between competing instructions; inconsistent outputs as each partner's priority is served in rotation. The preventive shift is to map mandate conflicts explicitly before the ecosystem is assembled.

### E — Workforce Failures

**Rubber-stamping.** Extension workers or field staff systematically approve AI outputs without review, treating the AI as definitively correct rather than as a reference layer. This is the mirror failure to resistance: resistance means workers override the AI reflexively, rubber-stamping means workers accept it reflexively. Both eliminate the human judgment that the system design depends on. The Six Orthogonal Shifts framework names this specifically as a failure mode in the extension workforce context. The preventive shift is to train workers on when to verify AI outputs and what cases require human judgment — not just on how to use the system.

**Abdication.** Workers reduce their own capability over time by delegating to the AI what they previously did themselves. The progressive loss of expertise means when the system is unavailable, no one can fill its function. Amul Sarlaben's field note documents the watchword: information alone is not the point; there is skill in the hand that counts for more than information in the head. The preventive shift is to design AI as an amplifier of human skill, not a replacement for it — and to measure worker capability independent of AI availability.

**Training timing failure.** Workforce training happens too late — after deployment, when workers are already forming habits around the system without guidance. Symptoms: inconsistent extension officer practice across districts; workers using the system in ways it was not designed for; quality variation that cannot be explained by the system's outputs. Bihar Krishi's 15,000+ extension worker training programme was integral to the rollout, not bolted on after. The preventive shift is to treat workforce training as a deployment dependency — it must precede user-facing launch, not follow it.

### F — Operating Model Failures

**Sustainability gap.** The deployment is built on funding (grant, pilot budget, international development partner support) that does not have a planned transition to sustainable domestic funding. When the initial funding ends, operations stop. Symptoms: operating costs not documented; no domestic budget line for the system; dependency on international partners for recurring costs. The preventive shift is to document operating costs accurately, identify the domestic institutional owner for steady-state operations, and establish the funding transition before the pilot ends.

**Metric staleness.** The deployment measures what was easy to count at launch (registrations, calls, downloads) and does not track whether the system is achieving outcomes (yield improvement, income increase, employment connection). Over time the metrics diverge from what matters — the system looks successful by its own measures while delivering less than claimed. The preventive shift is to define outcome metrics before deployment and measure them from the start, even if they are harder to count.

## What This Means for a Next Adopter

The most important failure modes to address before a deployment begins are the institutional ones: non-transferability, the pilot-forever trap, political dependency, and the absent network operator. These are the failure modes that end deployments that are technically working. Technology failures (vendor lock-in, staleness cascade, harmful output) are more visible and more recoverable — they present as symptoms and can be diagnosed. Institutional failures often look like inertia or funding shortfalls, masking the structural cause.

Build a failure mode review into your deployment planning: for each failure mode named here, ask explicitly whether your current plan would trigger it. The cost of that review is low. The cost of encountering an avoidable failure mode in deployment is high.

## Open Questions

The failure mode catalogue is drawn primarily from agricultural deployments in India and Ethiopia. Livelihoods deployments (Blue Dots AI) and health or education deployments (not yet documented in this wiki) may surface different failure modes — particularly in the D (ecosystem) dimension, where the partner mix and mandate alignment challenges are different.

The rubber-stamping and abdication failure modes (E dimension) are named in the Six Orthogonal Shifts framework but not yet documented with specific field evidence from a deployment where they occurred. A deployment that observed and documented these patterns — including what interventions addressed them — would significantly strengthen this catalogue.
