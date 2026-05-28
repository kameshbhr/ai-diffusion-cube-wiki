# Trust Architecture — How Trust Is Built and Maintained Across Deployments

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bharat-VISTAAR, Ethiopia ATI
**Last updated:** 2026-05-28

## The Pattern

Trust in AI advisory systems in public interest sectors is not primarily trust in the AI. It is trust in the institution that deploys it. Across OAN deployments, the trust source is consistently the deploying institution — the Maharashtra government, the Amul cooperative, ICAR, ATI Ethiopia — not the AI system itself. The AI is delivered under the deployer's brand, through the deployer's channel (short codes, voice telephony), in the deployer's language. When a farmer calls 155313 in Maharashtra, they are calling the government of Maharashtra's agricultural advisory line; the fact that the response is AI-generated is secondary to the fact that it is the government's system.

This has direct consequences for how you design trust into a deployment: trust infrastructure is not technical — it is institutional.

## Evidence

### MahaVistaar

The Maharashtra government's Commissioner of Agriculture is the named deployer. The short code (155313) is a government telephone number. Responses are attributed to the state agricultural advisory system. Farmers in Maharashtra have a pre-existing relationship with government agricultural services — the AI deployment inherits that institutional trust rather than needing to build trust in an unfamiliar AI system from zero.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Amul Sarlaben

Amul's cooperative trust model differs from government trust but is equally pre-established. Gujarat's dairy farmers are member-owners of the Amul cooperative; they have a long-standing relationship with Amul as their milk procurer and primary agricultural service provider. Sarlaben is delivered as an Amul service, accessed via an Amul number (08035453545). Trust is inherited from the cooperative membership relationship, not built through AI performance alone.

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

### Bharat-VISTAAR

ICAR is India's apex agricultural research institution — its brand carries authority on agricultural knowledge questions. Bharat-VISTAAR is delivered as an ICAR service on short code 155261, inheriting ICAR's research credibility with farmers who understand the ICAR brand.

[See full pathway: Bharat-VISTAAR](../pathways/bharat-vistaar.md)

### Ethiopia ATI

ATI is Ethiopia's designated government body for agricultural transformation. Its institutional mandate provides the trust source for the Ethiopia deployment. The Fayda digital ID integration adds a further trust signal — the system can identify the farmer and deliver personalised advice, with farmer identity anchored to the national identity system rather than an unknown AI service.

[See full pathway: Ethiopia ATI](../pathways/ethiopia-ati.md)

## What This Means for a Next Adopter

The trust architecture implication is direct: deploy under an institution farmers already trust, through a channel they already use. Do not launch a new brand for your AI advisory system — building trust in an unknown brand requires time and marketing investment that you almost certainly do not have. Instead, integrate the AI into an existing trusted delivery channel: an extension advisory line, a cooperative member service, a government scheme helpline.

The dual-model safety architecture (primary LLM plus independent safeguard model) in the OAN deployments is also a trust-maintenance mechanism, not just a technical safety measure. Preventing harmful outputs from reaching users preserves the institutional trust that the system is deployed under — a single widely-shared harmful answer from the "Commissioner of Agriculture's system" would damage institutional credibility in ways the technology team could not repair.

Trust architecture is inseparable from the institution's broader credibility management. If the deploying institution loses public trust (through a policy failure, a widely shared wrong answer, or a political event), the AI advisory system's trust is damaged regardless of technical performance.

## Open Questions

How does institutional trust hold when the AI gives a factually wrong but not harmful answer? The safeguard model prevents dangerous outputs but not incorrect ones. The escalation and public response process when users call back to complain about bad advice is not documented for any deployment.

Does farmer awareness that the system is AI-powered affect trust? None of the current deployments documents whether farmers are informed they are speaking to an AI, and whether disclosure affects adoption or trust levels.
