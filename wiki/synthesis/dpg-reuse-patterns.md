# DPG Reuse Patterns — What Transferred, What Was Rebuilt

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Ethiopia ATI, Bharat-VISTAAR, Amul Sarlaben, Bihar Krishi
**Last updated:** 2026-05-28

## The Pattern

Across the deployments documented in this wiki, a consistent pattern of reuse and rebuild emerges: architecture components transferred with low friction, domain knowledge transferred with medium friction, and institutional and ecosystem conditions required near-complete rebuilding in each new context. The compression sequence (9 months → 3 months → 3 weeks) tracks directly with the maturity of the reusable component library. What a next adopter can inherit from this network, and what they must build, is now partially documentable — though gaps remain.

A corollary finding: the components that got rebuilt in each deployment were not usually rebuilt because they were bad — they were rebuilt because the adopter did not know they could be inherited, or because the handoff mechanism between deployments had not been established. This points to a gap in the network itself: reuse requires not just good components but a working transfer protocol.

## Evidence

### What Transferred — Architecture Layer

**Federated data architecture pattern**: The decision to connect to data at query time via API rather than centralise it was established in MahaVistaar and inherited by Ethiopia ATI. 🟡 The transfer was facilitated by EkStep Foundation's involvement in both deployments. A deployer without EkStep involvement would need to discover this pattern independently — it is documented in the MahaVistaar serving architecture note but is not packaged as a standalone reusable decision.

**Dual-provider inference pattern (vLLM + commercial API fallback)**: Established in MahaVistaar and available for inheritance. 🔵 Whether Ethiopia ATI or any other deployment has specifically adopted this pattern is not documented. The pattern is most relevant at deployments approaching the cost threshold where self-hosted inference becomes economical (implied threshold: approximately 200,000–300,000 queries/month based on MahaVistaar evidence).

**Seven-layer system architecture**: The conceptual architecture (user → interface → moderation → AI decision engine → knowledge/scientific models → live data sources → DPI foundation) is documented and reusable as a planning framework for any federated AI advisory deployment. 🟡 Whether subsequent deployments have used this framework explicitly in their architecture design is not documented.

**Moderation layer design approach**: The principle of a fully decoupled moderation layer (separate from the main LLM, testing for domain validity, content filtering, prompt injection defense, adversarial patterns) is documented from MahaVistaar. 🔵 The specific 500 adversarial attack patterns are not publicly released. A next deployer can inherit the design principle and methodology; the specific test suite requires direct access to MahaVistaar team knowledge.

### What Transferred — Knowledge Layer

**ICAR agricultural knowledge**: Integrated into MahaVistaar and Bharat-VISTAAR. 🟡 This is India-specific — not transferable directly to Ethiopia, where the relevant knowledge authority is the Ethiopian Institute of Agricultural Research (EIAR) or ATI itself. Ethiopia ATI would have required Ethiopia-specific crop and pest knowledge, which is a rebuild not an inheritance.

**IMD weather integration pattern**: The pattern of integrating a national meteorological service's live data feed is transferable; the specific IMD API is India-specific. 🟡 Ethiopia ATI would need to integrate Ethiopia's national meteorology authority. The pattern transfers; the implementation does not.

**Amul's 30M cattle health records**: Cooperative-owned longitudinal data used as an AI knowledge base is a pattern. The specific data is Amul-specific and not transferable. 🟡 The pattern — using the deploying institution's own longitudinal data as a knowledge base rather than generic external literature — is reusable for any cooperative or institution with comparable data assets.

### What Was Rebuilt — Institutional and Ecosystem Layer

**Government approval and funding relationships**: These were rebuilt from scratch in every deployment. 🟡 The Maharashtra relationship does not transfer to Bihar or Ethiopia. The institutional relationship work is context-specific and non-transferable. The framework for thinking about institutional framing (project vs capability, accountability structure, procurement mechanism) is transferable; the specific relationships are not.

**Ecosystem assembly**: MahaVistaar's 54-organisation ecosystem map does not transfer to Bihar Krishi or Ethiopia ATI — different contexts require different organisations. 🟡 The methodology for assembling an ecosystem across four layers (Institutional and Governance, Technology and AI, Structured Data, Knowledge and Documents) is a transferable framework. The specific organisations are not.

**Language and localisation**: Every deployment required rebuilding the localisation layer for its specific linguistic context. Marathi (MahaVistaar) does not transfer to Amharic (Ethiopia). The localisation process and tooling may be transferable; the output is not. 🟡

**Field workforce network**: The extension worker network trained by Bihar Krishi across 38 districts was rebuilt from scratch for that context. The training methodology and materials may be partially transferable; the network itself is not. 🟡

### The Transfer Gap

The compression from 9 months (MahaVistaar) to 3 months (Ethiopia ATI) to 3 weeks (Amul Sarlaben in a specific configuration) demonstrates that transfers occurred. 🟡 But the mechanism of transfer — how EkStep Foundation packaged and conveyed architecture decisions to Ethiopia ATI, what documentation existed, what conversations happened — is not described in available sources. This is the critical gap for future scaling: the compression only continues if there is a working handoff protocol, not just reusable components sitting in a repository.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)
[See full pathway: Ethiopia ATI](../pathways/ethiopia-ati.md)

## What This Means for a Next Adopter

Map what you need against what this network has already built before you write a single line of code or a single procurement specification. The architecture layer is available for inheritance: federated data pattern, dual-provider inference, moderation design approach, seven-layer architecture framework. Connecting to EkStep Foundation or an equivalent network participant who has worked across these deployments is the fastest path to this inheritance.

Be clear about what you will have to rebuild: institutional relationships, ecosystem assembly, language localisation, and field workforce networks are context-specific and cannot be shortened by architecture inheritance. Budget and timeline these accurately — underestimating the rebuilding cost is the most common cause of the 3-month deployment taking 9 months.

The knowledge layer is intermediate: domain knowledge (crops, pests, weather, livestock) must be contextualised for your geography and language, but the structure of the knowledge base — how to organise and query it — is transferable. Work with your domain authority (the equivalent of ICAR or EIAR in your context) to identify what already exists in structured form, and design the knowledge integration to use it as-is rather than requiring a full knowledge reconstruction.

## Open Questions

The transfer protocol — how components are actually handed from one deployment to the next — is not documented. A next adopter who works with EkStep Foundation or an equivalent partner should ask specifically: what is the handoff process, what documentation exists, and what decisions need to be remade from scratch in this new context?

Whether DPG components beyond the architecture layer (governance models, training materials, evaluation benchmarks) have been packaged for reuse is not documented in available sources.

Whether the reuse pattern will hold when a deployment operates entirely outside EkStep Foundation's network — with a different technology partner — is an open question that the current evidence cannot resolve.
