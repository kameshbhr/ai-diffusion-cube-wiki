# 70-30 Split

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bihar Krishi, Ethiopia ATI, Blue Dots AI, Bharat-VISTAAR
**Last updated:** 2026-06-02

## The Pattern

Across every documented deployment in this wiki, approximately 30% of the challenge sits in the technology dimension (architecture, data, AI infrastructure) and approximately 70% sits in the non-technology dimensions (institution, ecosystem, workforce, operating model). This is not a claim that technology is easy — MahaVistaar's seven-layer architecture, dual-provider topology, and cost optimisation required significant technical work. It is a claim that the technology work, once done, is more tractable and more recoverable than the non-technology work. The typical deployment that fails does not fail because the AI produced wrong outputs; it fails because no institution was willing to say "this runs in my name," or because the workforce was not trained, or because the pilot funding ended with no transition to sustainable operations.

The 70/30 split carries a direct implication for how deployers should allocate attention and budget. Deployers who spend 80% of their planning time on model selection, infrastructure choices, and data pipelines are allocating effort against 30% of the challenge. The deployments documented here that reached scale — MahaVistaar at 17 lakh daily advisories, Bihar Krishi at 850,000+ registered farmers, Amul Sarlaben at 3.6 million members — invested comparably in governance design, ecosystem assembly, and workforce transition.

## Evidence by Dimension

### B — Architecture (the 30%)

MahaVistaar's technical work was substantial and specific. The production serving architecture required a choice between self-hosted infrastructure (4×H100 GPUs, TP=4, vLLM serving, fine-tuned Qwen3.5-27B) and Azure OpenAI as a fallback — with a 180× cost difference between the two (₹0.05/question vs ₹9.4/question). The dual-provider topology required prefix caching and context management design. The Marathi voice pipeline required dialect-specific corpus work. The independent moderation layer (GPT-OSS Safeguard 20B) required integration and calibration.

This was real technical work. It was also work that, once done, transferred to every subsequent deployment. Ethiopia ATI did not rebuild it. Amul Sarlaben adapted it in three weeks. The 30% designation is not a claim that architecture work is trivial — it is a claim that architecture work, once done by a pioneer deployment, does not need to be done again by subsequent deployments in the same network.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### C — Institution (part of the 70%)

The six deployments documented in this wiki required the following institutional work, none of which was technology:

Bihar Krishi required alignment across multiple Bihar state departments, connection of 50+ government schemes, and sustained political support through the 4th Agriculture Roadmap process. The institutional framing (roadmap, not project) is what secured multi-year funding and kept the deployment alive through staff changes.

Bharat-VISTAAR required a Union Budget announcement, ministerial launch, and Prime Minister endorsement — institutional alignment at national government level. The Rs. 150 crore allocation was a national budget decision, not a technology procurement. The institutional work to secure that commitment is not documented in detail, but its precondition was years of state-level field evidence.

Ethiopia ATI's three-month deployment timeline was enabled by ATI's national transformation mandate — a pre-existing institutional authority that could align the Ministry of Agriculture, meteorological services, and research institutes without requiring new institutional arrangements. Countries attempting a similar deployment without an equivalent of ATI would need to create that institutional alignment first, which would likely be the longest part of the deployment.

[See full pathway: Bihar Krishi](../pathways/bihar-krishi.md) | [Bharat-VISTAAR](../pathways/bharat-vistaar.md)

### D — Ecosystem (part of the 70%)

MahaVistaar required 54 ecosystem partners across four layers (institutional/governance, technology/AI, structured data, knowledge/documents). The assembly, alignment, and sustained coordination of 54 organisations is a non-technology challenge. The OAN Diffusion Pathway documents that Ethiopia required entirely different partners — reflecting that the 54-enabler ecosystem is not reusable across geographies even when the architecture is. The ecosystem assembly work begins again in each new geography.

Amul Sarlaben's ecosystem was significantly smaller — Amul holds institutional, data, and member-relationship roles that required multiple separate organisations in state government deployments. This was a structural advantage of the cooperative model, not a technology advantage. The smaller ecosystem (primarily internal cooperative functions plus EkStep/OpenAgriNet for DPG deployment and Bhashini for language support) is what enabled the three-week deployment. The technology was the same as MahaVistaar; the ecosystem was simpler.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md) | [Amul Sarlaben](../pathways/amul-sarlaben.md)

### E — Workforce (part of the 70%)

Bihar Krishi trained 15,000+ extension workers across 38 districts. The Six Orthogonal Shifts framework cites this as the canonical example of structured, deliberate, scaled workforce training for an institutional AI deployment. 15,000 people, 38 districts: the logistics of that training programme are not a technology problem. The curriculum design, the trainer network, the scheduling, the geographic distribution across all districts — these are workforce management and training design problems.

Amul Sarlaben's workforce transition is structurally different: the 1,400 veterinary doctors whose records feed the system had their role change from the primary advisory source to a second-level escalation for cases the AI cannot resolve. This transition did not require a training programme — the cooperative relationship already structured the veterinary network's role. The absence of a documented workforce resistance challenge in Amul contrasts with the Bihar Krishi training requirement: cooperative workforces and government extension officer workforces have different starting conditions.

[See full pathway: Bihar Krishi](../pathways/bihar-krishi.md)

### F — Operating Model (part of the 70%)

Blue Dots AI's livelihoods deployment documents the operating model challenge at its most explicit. The flywheel economics (more employers → richer demand signals → more relevant matches → more workers trust the system → more employer participation) only compound if operations are sustained. The Dharwad district deployment (10 months) and Ghaziabad deployment (4 months) are documented as proofs of the flywheel — but sustaining the flywheel requires sustained operations, not sustained technology investment. The district administration governance node, NGO trust fabric, and MSME data contribution are all non-technology operating model commitments.

[See full pathway: Blue Dots AI](../pathways/blue-dots.md)

## What This Means for a Next Adopter

The 70/30 observation is a planning tool, not a budget formula. It does not mean 70% of your budget should go to non-technology activities — the technology investment may be lumpy and front-loaded in ways that skew the budget even when the challenge distribution is 70/30. What it means is that your attention and your risk register should be weighted 70/30.

The practical implication: if your deployment plan has one paragraph on governance and three pages on model selection, your plan is misaligned with where deployments fail. Rebalance by documenting explicitly: who is the network operator? How will workforce training work? What is the operating model after the pilot funding ends? Who owns steady-state operations? If you cannot answer these questions in detail, you have unsolved 70% problems, regardless of how well-designed your architecture is.

Technology problems are more visible and more recoverable than non-technology problems. When the data integration stalls or the voice pipeline has latency issues, you can diagnose and fix the problem. When the network operator role is vacant or the institution has not committed to steady-state funding, the problem is harder to name and slower to resolve. Invest in solving the 70% first.

## Open Questions

The 70/30 estimate is a pattern observation across a small set of deployments, not a formal measurement. No deployment in this wiki has attempted to quantify the split precisely — for example, by measuring actual team time allocation or budget distribution across technology and non-technology activities. A deployment that tracked this explicitly would provide stronger evidence for or against the 70/30 claim.

The split may differ across sectors and deployment types. Agricultural deployments in India and Ethiopia have a relatively mature institutional environment (extension systems, agricultural departments, established cooperative structures) that may make the institutional work more tractable than it would be in health, education, or livelihoods in urban informal sectors. Blue Dots AI's four-lever model suggests the institutional and ecosystem work in livelihoods is at least as complex, but it is not yet documented at the same scale as MahaVistaar.
