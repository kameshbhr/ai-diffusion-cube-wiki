# Compression Proof — From 9 Months to 3 Months to 3 Weeks

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Ethiopia ATI, Amul Sarlaben
**Last updated:** 2026-05-28

## The Pattern

The time required to go from commitment to a working deployment has compressed dramatically across successive deployments in this network: 9 months for the first full deployment (Maharashtra), 3 months for the next national-scale deployment (Ethiopia ATI), and 3 weeks for the most recent (Amul Sarlaben, in a specific configuration). This is not a coincidence of simpler requirements — each successive deployment was at least as complex as the prior one. The compression is the direct result of reusable architecture components, accumulated deployment knowledge, and a maturing network of partners who have worked together before.

This pattern has a direct implication for any next adopter: if you can connect to this network and its accumulated assets, your time-to-deployment is not bounded by how long it took the first person to figure this out. The learning compounds.

## Evidence

### MahaVistaar — 9 Months

MahaVistaar was the first full-scale deployment in this network. It took approximately 9 months from commitment to working production system. 🟡 This timeline reflects the work of building the foundation: assembling the 54-organisation ecosystem across four layers, negotiating data access with 25+ partner organisations, establishing the federated architecture design, building the moderation layer (including 500 adversarial attack patterns), fine-tuning the Qwen3.5-27B model on agricultural domain data, and establishing the multi-channel interface (voice 155313, WhatsApp, app, web). 🟡 Each of these activities required time not because the work was slow but because none of it had been done before in this configuration.

The output of 9 months of work was not only a working deployment — it was a reusable architecture. The federated data design, the dual-provider inference pattern, the moderation layer, the ecosystem coordination model, and the training and evaluation methodology are all assets that subsequent deployments can inherit rather than rebuild.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Ethiopia ATI — 3 Months

Ethiopia ATI launched in February 2026, approximately 3 months after commitment. 🟡 The deployment targets 15 million+ smallholder households in a country where agriculture is 35% of GDP — a scale and complexity comparable to or exceeding MahaVistaar. The compression from 9 months to 3 months was not the result of lower ambition; it was the result of EkStep Foundation's involvement in both deployments, which enabled architecture transfer. 🟡

The 3-month timeline was achieved by not rebuilding what MahaVistaar had already built: the federated data architecture, the inference infrastructure pattern, the moderation layer design, and the ecosystem assembly methodology were all available as inheritance. The Ethiopia-specific work — integration with the Fayda digital identity infrastructure, adaptation of agricultural knowledge for Ethiopian crops and agro-climatic zones, language localisation — was the real content of the 3 months. 🟡

[See full pathway: Ethiopia ATI](../pathways/ethiopia-ati.md)

### Amul Sarlaben — 3 Weeks

Amul Sarlaben reached a working deployment in 3 weeks in a specific configuration. 🟡 The evidence for this timeline is reported in the Shifts framework document; the specific configuration and what "working deployment" means in this context is not further specified in available documentation. The plausible explanation is that Amul's existing data infrastructure (2 billion transactions, 30 million cattle records) and the reuse of architecture components from earlier deployments in the network compressed the work to a very small increment — essentially, adaptation rather than construction. 🟡

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

## What This Means for a Next Adopter

The compression sequence tells you something specific: the first deployment in a new configuration takes the longest because it is building the reusable foundation, not just delivering a product. If you are attempting an agricultural AI deployment in a country or sector not yet represented in this network, expect 6–9 months to first working deployment if you are not inheriting architecture components. If you are deploying in a context where EkStep Foundation or a comparable network participant can transfer components, 3 months is achievable. If your deployment is primarily an adaptation of an existing working system — new data, new language, same architecture — 3 weeks is the lower bound that has been demonstrated.

The practical implication is: do not start from scratch if you do not have to. The cost of connecting to this network is lower than the cost of rebuilding its assets. The 54-organisation ecosystem map, the moderation layer with 500 attack patterns, the vLLM + Azure OpenAI dual-provider pattern, and the fine-tuning methodology are all available to be inherited. What you will build is the Ethiopia layer, not the MahaVistaar foundation.

The second implication is sequencing. The compression works because certain decisions are made early and irrevocably: commitment to federated data (no centralisation negotiation required), commitment to dual-provider inference (vendor independence from day one), commitment to pre-launch workforce training (Bihar Krishi model). Deployments that defer these decisions to "after pilot" tend not to achieve the compression — they spend the time resolving decisions that should have been made at the start.

## Open Questions

The specific configuration of Amul Sarlaben's 3-week deployment is not documented. Understanding what exactly was done — and what was explicitly deferred to a later phase — would provide a clearer blueprint for replication.

Whether the compression continues beyond 3 weeks, or whether there is a floor below which timeline reduction produces unacceptable quality trade-offs, is an open question. Ethiopia ATI's outcome evidence (whether the 3-month timeline produced a system that is achieving the 8% income boost ambition) will be a key data point.

Whether the compression pattern transfers to sectors outside agriculture — health, education, livelihoods — is not yet evidenced.
