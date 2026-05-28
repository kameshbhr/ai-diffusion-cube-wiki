# DPG Reuse Patterns — What Transfers Across Deployments and What Doesn't

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bharat-VISTAAR, Ethiopia ATI, Bihar Krishi
**Last updated:** 2026-05-28

## The Pattern

The OpenAgriNet DPG layer is the primary reuse vehicle across OAN deployments. What the DPG layer transfers between deployments, and what must be rebuilt for each, determines how much compression is achievable. The pattern across five deployments shows consistent transfer of architecture and infrastructure, and consistent rebuilding of language, domain knowledge, and institutional configuration.

## Evidence

### MahaVistaar → Amul Sarlaben

**What transferred:** The full OAN DPG codebase — 7-layer system architecture, safeguard model integration, serving infrastructure patterns, Beckn protocol integration, federated data query architecture, and EkStep Foundation network orchestration.

**What was rebuilt:** Gujarati language ASR/TTS configuration, dairy domain knowledge base (cattle breeds, feed regimes, milk yield, animal health), Amul cooperative scheme information, and integration with Amul's data infrastructure.

**Compression achieved:** Three-week deployment versus MahaVistaar's original full-build timeline (not documented). This is the clearest quantified evidence of DPG reuse value in the wiki.

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

### MahaVistaar → Bharat-VISTAAR

**What transferred:** OAN DPG layer.

**What was rebuilt:** Hindi and English language configuration, ICAR knowledge integration (crop research, pest databases, soil health data), national scheme information, and national-level data source connections.

**Compression achieved:** Not documented.

[See full pathway: Bharat-VISTAAR](../pathways/bharat-vistaar.md)

### MahaVistaar → Ethiopia ATI

**What transferred:** OAN DPG layer.

**What was rebuilt:** Amharic language configuration, Ethiopian crop and climate knowledge, and Fayda digital ID integration. The Fayda integration is a new integration type — connecting to a national digital ID system — not present in any Indian deployment.

**Compression achieved:** Not documented specifically.

The Ethiopia deployment is the most significant portability test: the DPG layer transferred across a language family (Indo-Aryan to Semitic), a national DPI foundation (India's stack to Ethiopia's Fayda-based stack), and a continental context. The fact that it transferred at all — with Amharic language configuration and Fayda integration as the primary new build elements — is evidence that the DPG layer was designed with international portability in mind from the outset.

[See full pathway: Ethiopia ATI](../pathways/ethiopia-ati.md)

### Bihar Krishi (non-OAN comparison)

Bihar Krishi is an independent state deployment that did not use the OAN DPG layer. It is included here as the intended comparison case: what does a comparable deployment cost and take without the shared DPG infrastructure? This data is not yet documented in available sources. Capturing Bihar Krishi's build timeline and cost would make the DPG reuse value precisely quantifiable, turning a directional claim into a measured one.

[See full pathway: Bihar Krishi](../pathways/bihar-krishi.md)

## What This Means for a Next Adopter

The DPG reuse pattern is the primary reason to enter the OAN ecosystem rather than building independently. The minimum viable new build for an OAN deployment is: language configuration + domain knowledge + institutional data integration. Everything else — architecture, safety, serving infrastructure, ecosystem coordination — is inherited from the maintained DPG layer.

Two caveats are important. First, "language configuration" is not trivial for low-resource languages. Languages well-served by Bhashini and AI4Bharat's production-quality models (major Indian languages) can be configured quickly. For languages outside that set — Amharic, Odia, regional languages with limited training data — building or sourcing ASR/TTS capability may be the longest-lead element of the deployment. Assess language readiness before estimating timelines.

Second, deployments that require architecture changes to the DPG layer — not just configuration but actual code changes to shared components — need to coordinate with EkStep Foundation to manage those changes back into the shared layer, or they will face the cost of maintaining a fork. The governance model for DPG layer contributions and forks is not documented in available sources.

## Open Questions

What is the precise time and cost breakdown for the "what was rebuilt" elements (language, domain, integration) versus the "what transferred" elements (DPG layer)? This would make the reuse value precisely quantifiable rather than directionally indicated.

Are there elements of the DPG layer that have been forked or modified by any deployment? If so, how is the long-term coherence of the shared layer maintained?

Bihar Krishi's timeline and cost remain undocumented — capturing these would close the comparison case and provide the empirical evidence base the B4 shift pattern currently lacks.
