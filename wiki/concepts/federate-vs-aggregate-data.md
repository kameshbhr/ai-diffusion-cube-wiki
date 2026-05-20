# Federate vs. Aggregate Data

**Dimension(s):** A: Problem orientation (A2 Data posture); B: Architecture (B2 Data sovereignty); F: Operating model (F2 Governance)
**Type:** Decision

## What this is

A fundamental architectural decision within data posture: when the AI needs to access data from multiple institutions or departments, does it connect at query time (federate) or copy into a central store (aggregate)?

**Federate:** The orchestrating agent connects directly to each institution's databases at the moment of query. Each institution retains ownership of its data. The AI pulls the data, frames the prompt, and sends only the prompt to the LLM — the raw data never leaves the deployer's systems. The connection is live; the data is accessed on demand, not pre-loaded.

**Aggregate:** Data from multiple sources is copied into a central warehouse or knowledge base. Simpler to query consistently; more complex to govern (who controls the central store? how is it kept current?). Raises sovereignty questions about who owns the aggregated data.

## Why it matters

This decision has compounding consequences across architecture (B), data sovereignty (B2), and governance (F2). Choosing wrong creates structural problems that are expensive to reverse after deployment. Federating protects institutional data ownership and avoids creating a new data monopoly; but it requires robust connection infrastructure and may introduce latency. Aggregating simplifies querying but requires institutions to give up data control — a concession that is hard to win and easy to lose.

The decision also interacts with the opt-in/consent question: can data be federated on an opt-in basis (institution decides case by case whether its data is accessed), or is it federated by default once the data sharing agreement is signed? Same question applies to aggregation.

## What the pathways show

🟡 MahaVISTAAR implements federation: the orchestrating agent talks directly to Maharashtra government databases, pulls data, frames the prompt, and sends only the prompt to the LLM. The raw data never leaves. This is described as a sovereignty decision, not a technical footnote.

🟡 The specific formulation from field experience: "Prompt-level interaction protects data better than contracts do. If a vendor's architecture requires that your data be sent to their servers, they have designed a system that works for them, not for you."

🟡 External data sources and DPI foundations are accessed on demand — not pre-loaded into the model. Sovereignty is not just about where data resides; it is about when the AI accesses it.

⬜ The national Bharat-VISTAAR layer introduces a shared knowledge base component — some aggregation at the national layer with federation at the state level. This hybrid model is not fully documented in current sources.

## Key decision criteria for adopters

| Criterion | Favours federation | Favours aggregation |
|---|---|---|
| Data sovereignty requirements | Strong (institutions retain control) | Weak (requires giving up control) |
| Latency tolerance | Low (each query hits live databases) | High (data already in central store) |
| Data freshness requirements | Strong (data is live at query time) | Depends on update cadence |
| Institutional trust between parties | Low (no one needs to trust a central authority) | High (all parties must trust central store operator) |
| Governance complexity | Lower initially | Higher (who controls the aggregate?) |

## Pathways that cover this

- [[deployments/mahavistaar]] — Federation model implemented; only prompt goes to LLM
- [[deployments/bharat-vistaar]] — Partial aggregation at national layer (not fully documented)

## Related concepts

- [[concepts/deploy-first-data-posture]] — The broader data posture shift within which this decision sits
- [[dimensions/architecture]] — B2 data sovereignty full treatment
