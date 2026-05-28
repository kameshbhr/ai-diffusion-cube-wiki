# Failure Modes — Named Patterns and Field Examples

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Bharat-VISTAAR, Bihar Krishi, Amul Sarlaben, Ethiopia ATI
**Last updated:** 2026-05-28

## The Pattern

Across the deployments documented in this wiki, a set of recurring failure patterns appear — not as complete failures that shut down a deployment, but as stall points, quality degradations, and adoption barriers that cost time, money, and impact. The most valuable characteristic of named failure modes is that they are recognisable before they become critical: a deployer who knows these patterns can watch for their early signals.

The documented failure modes fall into four categories: architecture failures (the system does something harmful or wrong at scale), institutional failures (the deployment runs out of mandate or money), ecosystem failures (a key relationship breaks down), and adoption failures (the target user never engages). Available documentation from the five deployments provides direct evidence for some failure modes and implied evidence for others.

## Evidence

### Failure Mode 1: Cost Spiral at Scale

What it is: The deployment works well at pilot scale, but the cost per query on commercial AI infrastructure becomes unsustainable as volume grows. The deployment either caps usage (defeating the purpose) or runs out of budget before it can demonstrate impact.

Evidence: MahaVistaar experienced this directly. 🔵 In November 2025, the deployment was paying approximately ₹9/question on Azure GPT-4.1, with costs tracking toward ₹6 lakh per day as Voice AI scaled. At 440,000 queries/month, the monthly cost would have been approximately ₹40 lakh — ₹4.8 crore per year, rising. The resolution was migration to self-hosted vLLM infrastructure, reducing cost to ₹0.05/question — a 180× reduction. 🔵 Without this resolution, the deployment would have faced a choice between capping usage and running out of budget.

Early warning signals: Monthly AI infrastructure invoices growing faster than query volume growth. Cost-per-query not decreasing as volume increases (no economies of scale on commercial pricing).

Prevention: Design for dual-provider inference from day one (commercial API + self-hosted fallback). Plan the migration to self-hosted infrastructure as a Phase 2 activity, not an emergency response.

### Failure Mode 2: Ecosystem Orphaning

What it is: The deployment's key institutional driver leaves (promotion, transfer, retirement), and no one else has the authority, relationships, or knowledge to hold the ecosystem together. Partners quietly disengage, data feeds go stale, and usage declines without anyone explicitly deciding to shut down.

Evidence: Not directly documented in any of the five deployments — this may reflect the recency of the evidence base (all deployments are active) or it may reflect that the documentation does not capture this risk. The Shifts framework document identifies institutional non-transferability (C2) as a shift that must be made — from knowledge residing in key individuals to knowledge embedded in systems and processes. ⬜ The absence of documentation about specific near-stall moments across all five deployments is itself a gap.

Early warning signals: Only one person can answer questions about how a specific ecosystem partnership works. Meeting notes about partner coordination are not systematically recorded. New staff joining the deployment team need to be briefed verbally about how the ecosystem works.

Prevention: Document ecosystem relationships (roles, access credentials, escalation contacts) in a system that survives individual departure. The Bihar Krishi model — 15,000 trained extension workers — distributes deployment knowledge across a large enough population that no single departure creates a critical gap.

### Failure Mode 3: Workforce Resistance Solidification

What it is: Field workers — extension officers, local advisers, frontline staff — perceive the AI system as a threat to their role. Initially passive, this resistance solidifies into active non-use: the system exists, queries are possible, but the people who would route farmers to it do not, because they have concluded it threatens their value. Usage metrics never reach the thresholds needed to demonstrate impact.

Evidence: Bihar Krishi's pre-launch training of 15,000+ extension workers is the clearest evidence of a deployment that explicitly addressed this risk before it could materialise. 🟡 The implicit signal is that deployments which train after launch face a version of this problem: extension workers who first encounter the system in the field, without having been prepared, tend to interpret it as a replacement rather than a tool. The absence of documented workforce resistance incidents across other deployments may reflect that this risk was either managed well or not documented when it occurred.

Early warning signals: Extension workers use the system only when directly observed. Usage is high at demonstration events and low in the weeks after. Field workers cannot explain what the system does differently from a Google search.

Prevention: Train before launch, not after (Bihar Krishi model). Train at sufficient depth that field workers understand what the system cannot do, not just how to operate it. Give field workers a visible role in the AI's improvement (feedback loops, override mechanisms).

### Failure Mode 4: Output Metrics Without Outcome Evidence

What it is: The deployment measures what is easy to measure (queries answered, users registered, satisfaction ratings) rather than what funders and governments care about (farmer income, crop loss, health outcomes). When the first funding cycle renewal comes, the deployment cannot demonstrate value in terms that justify continued investment.

Evidence: This risk is present across all five deployments in this wiki. 🟡 MahaVistaar measures unique users, query volume, and satisfaction (97%+) but outcome metrics (farmer income change, crop loss reduction) are not documented. Bihar Krishi measures registration, scheme applications, and engagement rate but not agricultural outcomes. Amul Sarlaben has no documented outcome metrics. Ethiopia ATI's 8% income boost ambition (5-year target) is the most explicit outcome target in this wiki, but Phase 1 outcome measurement methodology is not described. 🟡

Early warning signals: The deployment team can fluently describe usage metrics but needs to pause to answer the question "has this helped a farmer earn more?" Funders or government counterparts have begun asking about impact rather than reach.

Prevention: Define outcome metrics before deployment begins. Identify a measurement methodology (randomised surveys, ICAR crop loss data comparison, cooperative production data) that is feasible at the deployment's geographic scale. Build data collection for these metrics into field operations from day one.

### Failure Mode 5: Data Access Stall

What it is: The deployment's data dependencies — weather feeds, scheme databases, market prices — require data-sharing agreements from partner institutions. Negotiations for these agreements take months or years. The deployment waits, the technical team churns, and by the time the agreements are signed the system architecture has changed and the data is in a different format than expected.

Evidence: The federated data architecture chosen by MahaVistaar is a direct solution to this failure mode. 🔵 By connecting to data at query time via API rather than centralising it, the deployment bypassed the need for data-sharing agreements entirely — the data stays in place, and access is granted at the API level rather than as a transfer. Whether this architecture was chosen because data-sharing negotiations had already stalled is not documented, but the architecture's effect is clear: 25+ partner organisations whose data feeds the system without multi-year agreement processes. 🔵

Early warning signals: The deployment plan depends on a data-sharing MOU with a government department that has not yet responded to the initial request. The technical architecture centralises data as a phase 1 activity.

Prevention: Design for federated data access from the start. Only initiate data-sharing negotiations for data that genuinely cannot be accessed at the API layer.

## What This Means for a Next Adopter

Of these five failure modes, two are particularly high-probability for a first-time deployer: Cost Spiral at Scale (Failure Mode 1) and Output Metrics Without Outcome Evidence (Failure Mode 4). Both are preventable with early architectural and measurement decisions that do not require significant additional resources.

The governance and accountability failure modes (Failure Modes 2 and 3) tend to be invisible until they have already occurred. The best prevention is to ask, before launch, what happens to this deployment if the person driving it leaves in the next six months — and then to make the answer satisfying.

## Open Questions

Specific near-stall incidents are not documented across any of the five deployments. A next contributor who documents a moment when the deployment nearly failed — and what specifically got it through — would add high-value evidence to this page.

Whether these failure modes are independent or whether they tend to cluster (a deployment experiencing Cost Spiral also tends toward Output Metrics Without Outcome Evidence) is not evidenced.

Whether failure modes differ by sector (agriculture vs health vs livelihoods) or by institutional actor type (government vs cooperative vs civil society) is not yet evidenced from this wiki's base.
