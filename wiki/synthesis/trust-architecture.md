# Trust Architecture — How Trust Was Built Across Deployments

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bihar Krishi, Ethiopia ATI, Bharat-VISTAAR
**Last updated:** 2026-05-28

## The Pattern

Every deployment in this wiki required trust to be established at multiple levels simultaneously: trust from end users (farmers) that the AI advice is reliable, trust from institutional partners that their data is protected and their role is respected, trust from field workforce that the AI is a tool rather than a replacement, and trust from government that the deployment is accountable and controllable. These are four distinct trust relationships, and each requires a different mechanism. Conflating them — or investing in only one while neglecting the others — produces characteristic failure modes.

The evidence across five deployments suggests that the most durable trust architectures are those that make the trust mechanism visible: the farmer can see where the advice comes from (ICAR, IMD, state extension), the partner can verify that their data has not moved, the field worker can override the AI when they believe it is wrong, and the government can audit what the system said. Invisible trust mechanisms — "just trust the AI" — have not produced durable scale in any documented case.

## Evidence

### MahaVistaar

MahaVistaar's trust architecture operates across all four levels. End-user trust is evidenced by 97%+ positive feedback (98.5% most recent measurement) across 342,000+ unique users. 🟡 What produced this trust is partly the accuracy of advice (94% on field evaluation sets) 🔵 and partly the attribution architecture: when the system answers a question, it draws on named and credible knowledge sources (ICAR, IMD, government scheme databases) rather than presenting AI-generated content as authoritative without grounding.

Institutional partner trust was built through the federated data architecture. 🔵 Partners who were concerned about their data leaving their systems were shown that only the prompt is sent to the LLM — the raw data stays where it lives. This visible mechanism resolved objections that would otherwise have required years of data-sharing negotiation.

The moderation layer (GPT-OSS Safeguard 20B, 500 adversarial attack patterns, domain validation) provides the government trust mechanism: it is documented evidence that the deployment has tested its harm boundaries and has a system for catching failures before they reach users. 🔵 Whether this moderation layer was specifically cited in government approval conversations is not documented.

Field workforce trust — whether extension workers trusted the system enough to recommend it to farmers — is not directly evidenced in available documentation.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Amul Sarlaben

Amul Sarlaben's trust architecture is grounded in cooperative ownership: the AI is trained on Amul's own 2 billion transactions and 30 million cattle records. 🟡 This is a qualitatively different trust mechanism from MahaVistaar: the farmers using Sarlaben are Amul cooperative members, and the system is trained on their collective data. The trust relationship is cooperative (this is our data, this is our system) rather than governmental (the state provides this service) or neutral-expert (ICAR says so).

The 1 million+ app downloads are a proxy for farmer trust — trust sufficient to install and actively use an application. 🟡 Whether there are adverse outcome reports (farmers who acted on AI advice and lost income or cattle health as a result) is not documented. The absence of such documentation may reflect absence of incidents or absence of a reporting mechanism.

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

### Bihar Krishi

Bihar Krishi's trust architecture is primarily built through the field workforce layer. 🟡 The pre-launch training of 15,000+ extension workers across 38 districts means that when the platform reached farmers, it was introduced by a trusted local person — the extension worker — rather than arriving as an unknown external system. This peer trust mechanism (your local extension officer recommends this) is a fundamentally different and more durable trust pathway than any institutional communication campaign.

The 20-25% monthly engagement rate suggests trust sufficient to sustain repeated use, not just initial adoption. 🟡 Whether there were specific trust-breaking incidents (wrong advice, system outages, data concerns) and how they were handled is not documented.

[See full pathway: Bihar Krishi](../pathways/bihar-krishi.md)

### Ethiopia ATI

Ethiopia ATI's trust architecture is at an early stage — the deployment launched in February 2026 and evidence of trust establishment is not yet available. 🟡 The Fayda digital ID integration provides a specific trust signal: the deployment is using Ethiopia's government-backed identity infrastructure, which carries institutional authority that a standalone system would not have. 🟡

[See full pathway: Ethiopia ATI](../pathways/ethiopia-ati.md)

### Bharat-VISTAAR

Not documented. The national-scale trust architecture for Bharat-VISTAAR — how 28+ state governments, ICAR, IMD, and domain-specific operators trust each other and the central hub — is not described in available sources.

[See full pathway: Bharat-VISTAAR](../pathways/bharat-vistaar.md)

## What This Means for a Next Adopter

Design your trust architecture before you design your user interface. The four trust relationships (end user, institutional partner, field workforce, government) each need a named mechanism, not a general commitment to quality. A next adopter should be able to answer the following questions before deployment:

How does the end user know the advice is grounded in credible knowledge — not just AI-generated text? In every documented deployment, the answer involves attributing advice to named institutional sources (ICAR, Amul's own cattle records, the cooperative's veterinary database).

How does each institutional partner verify that their data has not moved? In every documented deployment, the answer involves a federated architecture and a demonstration that the partner can verify data access logs. A partner who has to trust your word is a fragile partner.

How does the field worker know it is acceptable to override the AI? In no documented deployment is this explicitly designed for — it is a gap across the evidence base. A next adopter who designs an explicit override mechanism (with feedback that returns overrides to the system as training signal) would be ahead of all documented deployments.

How does the government auditor verify what the system said to a user? In no documented deployment is the audit mechanism described. This is a likely regulatory requirement in most jurisdictions and should be designed into the system before deployment, not retrofitted after a compliance request.

## Open Questions

Whether trust, once lost, can be rebuilt within a deployment lifecycle is not documented across any of these cases. Understanding a trust recovery pattern would be valuable.

The field worker override mechanism — which no documented deployment has fully designed — is the most consequential open question for adoption quality. A deployment that gives extension workers visible override capability and uses those overrides as a quality signal would advance the evidence base significantly.

Whether the cooperative trust architecture (Amul's model, where users are owners) transfers to contexts where a cooperative structure does not exist is unresolved.
