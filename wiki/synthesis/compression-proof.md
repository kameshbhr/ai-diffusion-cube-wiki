# Compression Proof — Speed of Replication Across Deployments

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bharat-VISTAAR, Ethiopia ATI, Bihar Krishi
**Last updated:** 2026-05-28

## The Pattern

Each successive OAN deployment has taken less time than the previous. The compression is not the result of a more capable team working faster — it is the result of the OAN DPG layer accumulating reusable components that new deployments configure rather than build. The headline figure is Amul Sarlaben: deployed in three weeks. What the three weeks covered, what it did not require, and what this means for a next adopter is documented here.

## Evidence

### MahaVistaar

MahaVistaar is the anchor OAN deployment — the system the DPG layer was built around. It required building all seven layers of the system architecture (user, interface, moderation, AI decision engine, knowledge/scientific models, live data sources, DPI foundation) plus the ecosystem coordination model, the serving infrastructure, the safeguard architecture, and the domain knowledge base for Maharashtra agriculture. The specific build timeline for MahaVistaar is not documented in available sources. It serves as the baseline — the full-build deployment against which subsequent compressions are measured.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Amul Sarlaben

Amul Sarlaben deployed in three weeks. The three-week figure is documented in OAN sources as evidence of DPG reuse compressing deployment time. What the three weeks covered: Gujarati language configuration (ASR/TTS tuning), dairy domain knowledge base (cattle breeds, feed regimes, milk yield, animal health), Amul cooperative scheme information, and integration testing. What the three weeks did not require: rebuilding the OAN DPG layer, the serving infrastructure, the safeguard model architecture, the 7-layer system architecture, or the ecosystem coordination model — all of these were inherited from MahaVistaar's DPG layer.

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

### Ethiopia ATI

Ethiopia ATI is an international deployment enabled by OAN DPG reuse. Specific timeline is not documented in available sources. The deployment required Amharic language configuration, Ethiopian crop and climate knowledge, and Fayda digital ID integration — a new integration type (national digital ID) not present in Indian deployments. Whether the Fayda integration extended the timeline versus a simpler reconfiguration deployment is not documented.

[See full pathway: Ethiopia ATI](../pathways/ethiopia-ati.md)

### Bihar Krishi (comparison)

Bihar Krishi is an independent state deployment that did not use the OAN DPG layer. It is included here as the intended comparison: what does a comparable deployment cost and take to build without the shared DPG infrastructure? This data is not yet documented. Capturing Bihar Krishi's build timeline and cost would make the compression claim precisely quantifiable rather than directionally evident.

[See full pathway: Bihar Krishi](../pathways/bihar-krishi.md)

## What This Means for a Next Adopter

If you are a government or cooperative seeking to deploy agricultural AI advisory, the OAN DPG layer means you can target a three-week deployment rather than a multi-month build. The three weeks covers language configuration, domain knowledge, and deployment-specific data integration. Everything else — architecture, safety, serving infrastructure, ecosystem coordination — is built, tested in production, and maintained by EkStep Foundation.

The caveat: the compression is real only if your deployment fits the OAN model (voice-first agricultural advisory, federated data architecture, Beckn-based ecosystem). If your use case requires significant architecture changes — a different interface type, a domain outside agriculture, a fundamentally different data access model — you are back to building rather than configuring, and the three-week figure does not apply.

Contact EkStep Foundation through the OpenAgriNet programme to assess fit before committing to a timeline.

## Open Questions

MahaVistaar's original build timeline is not documented. Knowing this would make the compression figure more precise: how many weeks or months does the DPG layer save per deployment?

Bharat-VISTAAR's deployment timeline is not documented.

Bihar Krishi, as an independent (non-OAN) deployment, could provide the counterfactual needed to make this claim empirically precise. A contribution documenting Bihar Krishi's build timeline and cost would be one of the highest-value additions to this wiki.
