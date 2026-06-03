# DPG Reuse Patterns

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bihar Krishi, Ethiopia ATI, Blue Dots AI, Bharat-VISTAAR
**Last updated:** 2026-06-02

## The Pattern

Digital Public Goods (DPGs) — open-source, open-protocol infrastructure components — are the mechanism by which deployment knowledge compounds across contexts. When a deployment codifies its architecture, governance frameworks, failure modes, and deployment playbooks into DPGs, subsequent deployments can start from the highest point the prior deployment reached rather than from scratch. The compression from nine months (MahaVistaar) to three months (Ethiopia ATI) to three weeks (Amul Sarlaben) is the operational evidence for DPG reuse. But not everything transfers, and the reuse pattern is not uniform: what transfers is the architecture and the governance framework; what does not transfer is the ecosystem, the language pipeline, and the institutional context.

The distinction between a DPG and a DPG instance matters. A DPG is the reusable building block — the open-source code, the protocol, the governance framework. A DPG instance is a specific deployment of that building block in a specific context. MahaVistaar is a DPG instance — it is not itself reusable, but the DPGs it was built with and the codified knowledge it produced are. Subsequent deployers draw on the DPGs and the codified knowledge, not on MahaVistaar's specific configuration.

## Evidence by Deployment

### MahaVistaar — the pioneer, the DPG generator

MahaVistaar was the first deployment to build the full OAN architecture: a seven-layer system (user layer, interface layer, moderation layer, AI decision engine, knowledge/scientific models, live data sources, DPI foundation), the data connector approach (connecting to data where it lives rather than centralising it), the language pipeline methodology for Marathi, the model evaluation benchmarks, the failure mode library, and the governance frameworks. Nine months of pioneer work produced not just a working deployment but a codified library of assets.

The specific DPGs produced or validated by MahaVistaar: the OpenAgriNet Knowledge Engine DPG (crop and livestock advisory), Memory Layer DPG (farmer interaction history), Trust Layer DPG (independent moderation), Agent Core DPG (orchestration), Action Gateway DPG (scheme access), Reach Layer DPG (multi-channel voice and app access), Learning Layer DPG (query-as-feedback loop), Signal DPG (demand visibility), Aggregator DPG (demand pattern synthesis), and Facilitator DPG (governance and coordination).

What MahaVistaar produced that is reusable: the architecture design, the governance framework, the failure mode library, the language pipeline methodology (as a starting framework, adapted per language), the model evaluation benchmarks, and the deployment playbooks.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Bharat-VISTAAR — DPG amplification at national scale

Bharat-VISTAAR reused the OAN DPG architecture directly. The six-month compression relative to MahaVistaar (building on established architecture rather than constructing it) was driven by DPG reuse. The national layer added one structural element that MahaVistaar did not have: the hub-and-spoke federation model, where state and cooperative platforms connect as nodes to a national knowledge base, ICAR advisory corpus, and AgriStack integration. This federation architecture is itself a reusable DPG-level design — any country building a national agriculture AI layer can draw on it.

What Bharat-VISTAAR added to the DPG library: the hub-and-spoke federation architecture pattern, the national scheme integration approach (PM-KISAN, PMFBY, Soil Health Card, Kisan Credit Card), and the national voice short-code access model (155261).

[See full pathway: Bharat-VISTAAR](../pathways/bharat-vistaar.md)

### Amul Sarlaben — DPG adaptation to cooperative context

Amul Sarlaben is the sharpest example of DPG reuse. The three-week deployment was possible because every DPG from MahaVistaar was available, and Amul's cooperative data foundation (50 years of records, 2 billion transactions, 30 million cattle with unique IDs) was the richest starting point of any documented deployment. The adaptation task was focused: contextualise the DPGs to the cooperative institutional structure, connect to Amul's cooperative data infrastructure, and adapt the Reach Layer DPG for Gujarati voice access.

What Amul Sarlaben contributed to the DPG library: the cooperative data architecture pattern (connecting 50 years of transaction data to AI advisory without centralising or exposing raw records), the plus-one service extension sequence (how to grow a cooperative AI deployment beyond advisory one step at a time), and the trust design pattern (how to signal institutional identity and user-centricity through naming and voice persona).

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

### Ethiopia ATI — first cross-geography reuse

Ethiopia was the proof that the DPG library is not context-specific to India. The OAN Diffusion Pathway documents that Ethiopia's evaluators assessed the existing DPG library and determined what needed adaptation rather than construction. The architecture transferred. The governance framework transferred. The language pipeline methodology transferred as a starting framework — Oromo and other Ethiopian languages required specific adaptation work. The failure mode library transferred.

What did not transfer: the 54-enabler ecosystem. Ethiopia required entirely different partners — different government ministries, different research institutes, different development partners. The ecosystem does not transfer with the technology; it must be assembled in each new geography. The OAN Diffusion Pathway explicitly notes that the four-layer ecosystem structure (institutional/governance, technology/AI, structured data, knowledge/documents) holds constant, even when every specific partner changes.

What Ethiopia ATI contributed to the DPG library: the national transformation institute as network operator model (applicable to countries where no single ministry has cross-institutional authority), the climate intelligence integration design (embedding real-time climate signals into farm advisory for COP and climate-vulnerable contexts), and the proof that the DPG library transfers across geographies with adaptation rather than reconstruction.

[See full pathway: Ethiopia ATI](../pathways/ethiopia-ati.md)

### Bihar Krishi — independent build, then DPG connection

Bihar Krishi was not built on OAN DPGs initially — it was built independently with MicroSave Consulting and Gates Foundation support, under a different institutional logic, and then connected to the Bharat-VISTAAR national layer when it launched. This is the alternative pathway to DPG deployment: build independently on your own terms, then connect to the DPG infrastructure retroactively.

The Bihar Krishi pattern has both advantages and costs. The advantage: Bihar could move at its own pace and on its own terms, without waiting for the OAN DPG library to be available. The cost: Bihar's build took longer and likely cost more than it would have if it had started from the OAN DPG foundation. The retrospective connection to Bharat-VISTAAR gave Bihar access to national scheme data, ICAR advisory, and AgriStack integration that it did not have as a standalone deployment — these are the benefits Bihar could not have achieved independently.

[See full pathway: Bihar Krishi](../pathways/bihar-krishi.md)

### Blue Dots AI — DPG for livelihoods, distinct architecture

Blue Dots AI introduces a distinct DPG set for livelihoods discovery — the Four DPGs (AI Diffusion DPG, Signal DPG, Aggregator DPG, Facilitator DPG) address the paradox of proximity problem in livelihoods rather than the advisory access problem in agriculture. The architecture overlap with the OAN agriculture DPGs is structural (federated data connection, open protocols, consent-based design) but the specific DPGs are different.

The Blue Dots DPG library is at an earlier stage of codification than the OAN agriculture DPGs — the Dharwad and Ghaziabad deployments are the initial pilots, and the compression from ten months to four months is early evidence that the DPG reuse pattern is beginning to hold. The livelihoods DPG library is in the same position the OAN agriculture library was in after MahaVistaar: one pioneer deployment has produced the assets, and the question is whether subsequent deployments will use and extend them.

[See full pathway: Blue Dots AI](../pathways/blue-dots.md)

## What Transfers, What Does Not

**Transfers:** Architecture design and seven-layer system structure. Governance frameworks. Failure mode library. Language pipeline methodology (as a starting framework requiring language-specific adaptation). Model evaluation benchmarks. Deployment playbooks. Data connector approach.

**Does not transfer (must be rebuilt in each new geography or context):** The ecosystem of specific partners. Language-specific corpus and ASR/TTS calibration. Institutional context and network operator identity. Data access arrangements with specific institutions.

**Partially transfers:** The institutional model (the concept of a network operator with national mandate transfers; the specific institution does not). The four-layer ecosystem structure (the layers are constant; the partners within each layer change).

## What This Means for a Next Adopter

Before building anything, conduct a DPG audit: what has already been built in the OAN or Blue Dots DPG libraries that applies to your deployment? The audit question is not "can I use this?" but "what specifically about my context requires adaptation, and what can I use without modification?"

The Bihar Krishi pattern — build independently, connect retroactively — is viable but expensive. If the OAN DPG library applies to your context, starting from it will save you months and significant cost. The investment in the OAN DPG library was made by the pioneer deployments for exactly this reason.

If you are the pioneer deployment in a new geography or sector, invest in codification as a core build task. Your codification is the gift to the next deployment that starts from your work. The compression from nine months to three months to three weeks happened because each pioneer invested in making their knowledge transferable.

## Open Questions

The reuse pattern is documented for agriculture deployments only. Whether the OAN agriculture DPGs can be adapted for health, education, or other sectors — or whether those sectors require new DPG libraries built from scratch — is not yet documented. Blue Dots AI's livelihoods DPGs are a separate library; the extent to which they draw on structural patterns from OAN agriculture DPGs is not fully documented.

The failure mode library — one of the most valuable transferable assets — is partially documented in this wiki but not yet at the level of specificity that would make it directly actionable in a new deployment. A deployment that contributed a detailed, case-specific failure mode library would significantly strengthen this asset.
