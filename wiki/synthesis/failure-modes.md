# Failure Modes — Known Patterns from Operations

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bharat-VISTAAR
**Last updated:** 2026-05-28

## The Pattern

The OAN source documentation names several failure patterns observed or anticipated across deployments. These are not failures of individual deployments in isolation — they are structural risks that any comparable deployment should plan for. Most are avoidable if identified before they occur; none are avoidable if discovered after scale.

## Evidence

### Commercial LLM cost spiral (MahaVistaar)

Before the serving infrastructure migration, MahaVistaar was running at ₹9.4/question on Azure GPT-4.1 and trending toward ₹6 lakh per day at growing query volume. At the query volumes a successful deployment generates, a commercial frontier LLM API is not a viable production serving model. The resolution was architectural: migrate to self-hosted fine-tuned Qwen3.5-27B at ₹0.05/question. The planned 16-GPU cluster projects to approximately ₹2 crore per year versus approximately ₹18 crore per year on the Azure run-rate.

The failure mode is not that the commercial API is expensive — it is that the cost trajectory is not visible until query volume grows, and the migration is non-trivial to execute under operational pressure. A deployment that does not plan for this migration in advance will face it at the worst possible moment.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Inter-departmental data blockage (MahaVistaar)

The state agriculture department held data in a system the extension directorate could not access. Resolving this required a joint secretary-level meeting and took time to convene. This is an institutional coordination failure mode: data sharing agreements that appear straightforward at the working level require senior authority to resolve when they cross departmental boundaries.

The mitigation is not the federated architecture itself — federated architecture still requires the owning department to consent to the AI system querying its data. The mitigation is identifying data governance blockers before deployment and convening the required authority level early, rather than discovering the blockage after launch.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Ecosystem orphan (general)

A deployment without a named network operator loses ecosystem coherence over time. As individual partners change priorities, the ecosystem erodes — data feeds go stale, technology integrations break, knowledge sources stop being updated — with no one holding responsibility. The OAN model assigns this role explicitly to EkStep Foundation. A deployment that launches without a named operator and explicit operator mandate is accumulating this risk from day one.

### Workforce dependency (general)

If extension officers become dependent on the AI system and cannot perform their advisory role when the system is unavailable, the deployment has created a fragility rather than a capability. This risk is named in the OAN framework (the E3 agency test shift) but is not yet documented as having occurred or been tested in any current deployment.

### Pilot-to-production architecture gap (general)

Deployments that build a prototype for the pilot and then rebuild for production face a transition risk — the production rebuild may not replicate pilot performance, the time and cost of the rebuild is typically underestimated, and learnings from the pilot do not transfer cleanly to a new codebase. OAN deployments use the same DPG architecture from pilot through production, explicitly eliminating this failure mode.

## What This Means for a Next Adopter

Plan for the commercial LLM cost spiral before it happens. If you launch on a commercial API, set a query volume threshold that triggers a serving architecture review. Build the migration plan before you need it.

Identify your data governance blockers before deployment. Map the data sources you need and the institutional authorities required to share them. If inter-departmental or inter-ministry data sharing is required, convene those conversations before deployment.

Name a network operator before you launch. Assign the ecosystem health role explicitly, with mandate and accountability, before the ecosystem is needed.

Test for E3 (workforce agency) before you declare success. High adoption plus inability to function without the system is a risk signal, not a success metric.

## Open Questions

What failure modes have actually occurred in live operations — not anticipated risks, but documented incidents? The OAN sources anticipate failure modes but do not document operational incidents. A future update to this page should capture actual incidents from live deployment, including the resolution and what was changed in the system or process.

How does the safeguard model perform in production? False positive rate (outputs incorrectly blocked), false negative rate (harmful outputs reaching users), and the operational process when the safeguard flags an output are not documented for any deployment.
