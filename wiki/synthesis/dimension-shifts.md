# Dimension Shifts

**Type:** Synthesis **Deployments cited:** MahaVistaar, Bharat-VISTAAR, Amul Sarlaben, Bihar Krishi, Ethiopia ATI, Blue Dots AI **Last updated:** 2026-06-02

## The Pattern

Across every documented deployment in this wiki, the move from idea to working-at-scale required the same set of fundamental reorientations — not just in technology choices, but in how problem framers, institutions, ecosystems, workforces, and operating teams thought about what they were doing. The Six Orthogonal Shifts framework names 21 of these FROM→TO transitions, grouped by dimension. They are not a checklist — they are a map of where deployments typically stall, and what the evidence says about how to move past each stall.

The 70/30 observation running through this evidence is structural, not incidental: approximately 70% of the failure and adaptation surface sits in the non-technology dimensions (institution, ecosystem, workforce, operating model), while the technology dimension (architecture, data) accounts for approximately 30%. Deployments that over-index on technology choices and under-invest in institutional, ecosystem, and workforce design tend to produce capable systems that do not spread.

## Evidence by Dimension

### A — Problem Orientation

**A1 — FROM: Technology-push framing TO: User-pull framing.** The shift is from "we have AI, let us deploy it" to "farmers cannot get timely crop advisory at scale, and here is the specific constraint preventing that." MahaVistaar's problem framing began with the Saagu Baagu pilot evidence — 21% yield increase and 9% pesticide reduction for cotton farmers in Telangana — which established that the advisory access problem was real and AI could address it. Blue Dots AI's framing began with the "paradox of proximity" — supply and demand co-exist in the same district but cannot find each other due to digital invisibility. Both are user-pull framings: the AI was selected because the problem required it, not the reverse.

**A2 — FROM: Data collection as prerequisite TO: Data connection as architecture.** Early deployments assumed a data-collection phase had to precede the AI deployment. MahaVistaar showed that the data already existed in fragmented form across the Agriculture Department, ICAR, IMD, and market systems — the architecture challenge was connection, not collection. Amul Sarlaben demonstrated this at its most extreme: 50 years of cooperative data, 2 billion procurement transactions, and records on 30 million cattle existed in Amul's systems, with no AI layer to surface them to farmers. Data connection, not data collection, was the architectural task.

**A3 — FROM: Building for average users TO: Designing for the hardest-to-reach first.** MahaVistaar's voice-first design in Marathi on any phone — driven by the access constraints of smallholder farmers without smartphones or broadband — meant the system worked for the most excluded users and was usable by all. Blue Dots AI made the same choice: the Four DPGs are designed for workers without stable internet and informal employers without digital presence. The shift is from "design for the median user and assume the rest will adapt" to "design for the hardest-to-reach and let the system work outward from there."

**A4 — FROM: Proof by demonstration TO: Proof by field outcome.** All deployments documented here moved from showing the technology working in a controlled setting to showing field outcomes (yield increases, income improvements, scheme applications submitted, employment connections made). The Saagu Baagu cotton pilot — cited in Bharat-VISTAAR as the evidence that the national architecture was worth building — is the canonical example. Ethiopia ATI's 8% income boost within five years is the stated outcome target that will govern whether the national deployment is considered successful.

**A5 — FROM: Inclusion as a feature TO: Inclusion as a design constraint.** MahaVistaar's language design, Amul Sarlaben's Gujarati voice channel, Ethiopia ATI's Oromo voice pipeline, and Blue Dots AI's consent-first data architecture were all inclusion decisions that shaped core architecture. They were not added after the core system was built. The shift is from "we will add language support later" to "the system does not exist until it is reachable by the hardest-to-reach user in the farmer's or worker's terms."

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### B — Architecture

**B1 — FROM: Model selection as a primary decision TO: Model as a replaceable component.** MahaVistaar's architecture explicitly separates the model layer from the service layer — Azure OpenAI GPT-4o as the fallback, a fine-tuned Qwen3.5-27B running on 4×H100 GPUs (TP=4) as the primary, with vLLM serving. The model can be swapped without rebuilding the surrounding system. The cost implication was decisive: ₹9.4/question at Azure vs ₹0.05/question self-hosted — a 180× difference that only becomes available when model choice is made separately from service architecture.

**B2 — FROM: Centralised data storage TO: Federated data connection.** All deployments in this wiki connect to data where it lives rather than replicating it into a central store. MahaVistaar connects to Department of Agriculture data, ICAR, IMD, and market feeds at query time. Bharat-VISTAAR connects to AgriStack, PM-KISAN, PMFBY, and ICAR without centralising them. Blue Dots AI's Signal DPG creates shareable demand signals without exposing raw worker data. The shift avoids data sovereignty disputes and allows institutional data owners to retain control, which was a precondition for their participation.

**B3 — FROM: Single-vendor dependency TO: Open-protocol vendor independence.** The OAN stack uses open-source DPGs, open protocols (Beckn), and open standards throughout. MahaVistaar's dual-provider topology — self-hosted primary, cloud fallback — means no single vendor failure takes the system down. The Beckn protocol enables Amul Sarlaben to offer Bharat Taxi on the same platform without integrating a new vendor at the system level.

**B4 — FROM: Building the whole system TO: Adapting the reusable layer.** The compression from 9 months (MahaVistaar) to 3 months (Ethiopia ATI) to 3 weeks (Amul Sarlaben) was driven by the shift from building to adapting. Ethiopia evaluated what needed adaptation, not what needed construction. Amul adapted MahaVistaar's architecture, governance frameworks, and deployment playbooks to a cooperative data context in three weeks. The shift is from "we are building an AI system" to "we are contextualising a proven architecture."

[See full pathway: MahaVistaar](../pathways/mahavistaar.md) | [Amul Sarlaben](/broken/pages/CvkYDreqsGaIAPd4DhZe)

### C — Institution

**C1 — FROM: Project framing TO: Transformation framing.** Bihar Krishi was embedded in Bihar's 4th Agriculture Roadmap — not deployed as a standalone technology project but as a component of a multi-year agricultural transformation programme. Ethiopia ATI's Digital Agriculture Roadmap 2025–2032 provides the same institutional framing. The shift from "we are running a technology pilot" to "we are running a national transformation programme with this as a component" changes what gets funded, who is accountable, and how long institutional support lasts.

**C2 — FROM: Assuming tacit knowledge transfers TO: Recognising non-transferability.** The Six Orthogonal Shifts framework documents this as a specific failure mode: deployment knowledge that is held implicitly by the deployment team and not codified does not transfer when key people move. MahaVistaar documented its architecture, governance frameworks, and failure mode library explicitly — these became the transferable assets that made Ethiopia and Amul possible. The shift is from "the team knows how to do this" to "the knowledge is documented in a form that makes the next deployment cheaper."

**C3 — FROM: Waiting for political permission TO: Building political support through demonstration.** Bharat-VISTAAR was announced in the Union Budget 2026-27 after state-level deployments had produced field evidence. The national allocation of Rs. 150 crore followed state-level proof, not preceded it. Prime Minister Modi's endorsement at the India AI Impact Summit followed working deployments, not proposals. The shift is from "we cannot act without political approval" to "we build the evidence that makes approval follow."

[See full pathway: Bihar Krishi](/broken/pages/BVetJI7LT04tWO9ekmVn) | [Bharat-VISTAAR](/broken/pages/VGFgrEvo55jInllGOyEC)

### D — Ecosystem

**D1 — FROM: Building a deployment team TO: Building a network operator role.** MahaVistaar had 54 ecosystem partners — the architecture, knowledge, technology, and data layers each required different partners. The network operator (EkStep Foundation, then the Maharashtra Department of Agriculture) held the ecosystem together by "saying this runs in my name" — providing the institutional anchor that made every partner's participation credible. ATI in Ethiopia played the same role: as a national transformation institute spanning government functions, it could align the Ministry of Agriculture, meteorological services, and research institutes in a way no single ministry could. The shift is from "who do we hire" to "who can say this runs in their name."

**D2 — FROM: Trust as a precondition TO: Trust as a design element.** Amul Sarlaben's institutional credibility comes from 50 years of daily milk procurement with 3.6 million members — a trust relationship that pre-dates the AI deployment. Bharat-VISTAAR speaks as the Ministry of Agriculture with ICAR advisory authority. MahaVistaar speaks as the Department of Agriculture Maharashtra. In every documented case, the AI was attributed to an institution the end user already trusted. The shift is from "users will trust the AI if it gives good answers" to "users will trust the AI if it speaks as an institution they already trust."

**D3 — FROM: Assuming partners will align TO: Designing coordination mechanisms.** MahaVistaar's 54-partner ecosystem required explicit coordination mechanisms — governance structures, role definitions, escalation paths — not just goodwill. Blue Dots AI's four-lever model (district administration as governance node, NGOs as trust fabric, MSMEs as data contributors, workers as signal generators) documents each partner's role and what holds their participation. The shift is from "these organisations share our goals" to "these organisations have defined roles and incentive alignment."

**D4 — FROM: Equal-weight partnerships TO: Network operator primacy.** Every documented deployment has one organisation that holds the "network operator" role — the institution that says "this runs in my name" and bears responsibility for the system's outputs. EkStep Foundation in MahaVistaar, ATI in Ethiopia, Amul in Sarlaben, the Ministry of Agriculture in Bharat-VISTAAR. Without this anchor, accountability diffuses and nothing moves. The shift is from "we are all equal partners in this consortium" to "one institution is accountable, and the others contribute under that anchor."

[See full pathway: MahaVistaar](../pathways/mahavistaar.md) | [Blue Dots AI](/broken/pages/uuLUvqUaE9WM7YiEeH71)

### E — Workforce

**E1 — FROM: Training as a deployment step TO: Training as an ongoing architecture.** Bihar Krishi trained 15,000+ extension workers across 38 districts — not as a one-time event at launch but as a structured, district-level rollout integral to deployment. The Six Orthogonal Shifts framework cites Bihar Krishi as the canonical example of deliberate, scaled workforce training for an institutional AI deployment. The shift is from "train the trainers before launch" to "workforce training is part of the system architecture."

**E2 — FROM: Training for compliance TO: Training for capability.** The distinction is whether training teaches workers to follow a new workflow or teaches them to understand what the AI can and cannot do, so they can use it well in novel situations. Extension workers who understand the AI's knowledge boundaries can escalate appropriately; workers trained only to follow workflows cannot. The shift is from "here is the new process" to "here is how the AI works and why its outputs should be verified in these specific cases."

**E3 — FROM: AI as answer machine TO: AI as agency amplifier.** The Amul Sarlaben deployment documented a specific field finding: younger family members who lack thirty years of dairy experience can now access expert knowledge through Sarlaben — "informed, therefore powerful to make choices; freedom comes from knowing, and nobody can fool me." This equaliser effect was not designed in — it emerged from the field. The watchword from the same deployment: information alone is not the point; there is skill in the hand that counts for more than information in the head. AI should make the farmer's or worker's skill more precise, not substitute for it. The shift is from "AI provides the answer" to "AI provides the information that enables the person to act more capably."

[See full pathway: Bihar Krishi](/broken/pages/BVetJI7LT04tWO9ekmVn) | [Amul Sarlaben](/broken/pages/CvkYDreqsGaIAPd4DhZe)

### F — Operating Model

**F1 — FROM: Plus-ten ambition TO: Plus-one sequencing.** Amul Sarlaben is the canonical example: start with advisory → add AI booking for artificial insemination → add microcredit → add Bharat Taxi via Beckn. Each step adds one capability to what already exists. Never plus-ten. The operational risk of adding many features simultaneously is that no single feature gets the focus it needs to work well, and failure in one undermines trust in all. The shift is from "we will build the full system" to "we will add one thing at a time, and each addition builds on demonstrated readiness."

**F2 — FROM: Governance as accountability TO: Governance as learning loop.** MahaVistaar's query log creates a visible demand signal for knowledge gaps — queries the system cannot answer reveal what knowledge needs to be added. Bharat-VISTAAR inherits this architecture at the national level. Blue Dots AI's Aggregator DPG creates shared intelligence for district administration from anonymised demand signals. The shift is from "governance tells us who is responsible when something goes wrong" to "governance tells us what the field is revealing and how to respond."

**F3 — FROM: Pilot-to-project TO: Pilot-to-infrastructure.** Bihar Krishi connected to Bharat-VISTAAR when the national layer launched — retrospectively gaining access to national scheme data, ICAR advisory, and AgriStack integration it did not have as a standalone deployment. The shift is from "we will run a project and evaluate whether to continue" to "we will build infrastructure that compounds in value with every additional node, and the infrastructure framing is established before the pilot begins."

**F4 — FROM: Cold-start deployment TO: Compression through reuse.** The compression from 9 months to 3 months to 3 weeks is the operational evidence for this shift. Each subsequent deployment started from a higher floor because predecessor deployments had codified their architecture, governance frameworks, and failure modes. The shift is from "every deployment starts from the beginning" to "every deployment starts from the highest point the prior deployment reached."

[See full pathway: Amul Sarlaben](/broken/pages/CvkYDreqsGaIAPd4DhZe) | [Bihar Krishi](/broken/pages/BVetJI7LT04tWO9ekmVn)

## What This Means for a Next Adopter

The 21 shifts are not sequential — they do not have to be completed in order. But they cluster around two critical early decisions that unlock the rest.

The first is the network operator decision (D4). Before committing to a deployment, identify which institution can say "this runs in my name" with the authority to align the other partners. If no institution can do this, the deployment will stall in coordination before it stalls in technology. ATI's national mandate is what made the three-month Ethiopia deployment possible — not the technology.

The second is the framing decision (C1 and A1 together). A deployment framed as a technology project will be evaluated as a technology project — limited budget, time-bounded, no workforce training, no sustainability beyond the pilot. A deployment framed as a transformation initiative will be funded, governed, and staffed differently. The shift in framing is a precondition for most of the other shifts, and it costs nothing except clarity about what you are doing.

For technology decisions: the evidence consistently shows that model choice is less important than architecture choice (B1 vs B2). A system built on federated data connection and open protocols can swap its AI model; a system built on a single vendor or a centralised data store cannot. Make the architecture decision first and let the model selection follow.

## Open Questions

The shift evidence is strongest for agriculture deployments in India and Ethiopia. Blue Dots AI provides early evidence for livelihoods, but the flywheel compounding pattern (F3 applied to demand-signal infrastructure) has not yet been tested across multiple geographies. A livelihoods deployment outside India would significantly strengthen or qualify the pattern.

The workforce shift evidence (E1–E3) is thin outside Bihar Krishi. Most deployments document what happened to extension workers at a summary level but not the training design, timing, or resistance pattern. A deployment that documents its workforce transition in detail — what was taught, when, what resistance looked like, and what resolved it — would fill a significant evidence gap.
