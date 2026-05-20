---
type: pathway
deployment: mahavistaar
dimensions: [institution, ecosystem]
sector: agriculture
geography: Maharashtra, Gujarat, Bihar, Ethiopia, India national
contributor: ekstep-foundation
contributed: 2026-05-20
last-updated: 2026-05-20
times-referenced: 0
---

# Institution-as-Authority Trust Design

**One-line summary:** Design the AI system so the institution is the advisory authority and the AI is only the delivery layer — the trust architecture that drives adoption in populations that trust institutions, not algorithms.

**Deployment source:** MahaVISTAAR (primary evidence) — [[deployments/mahavistaar]]; confirmed across [[deployments/amul-sarlaben]], [[deployments/bharat-vistaar]], [[deployments/ethiopia-ati]], [[deployments/bihar-krishi]]
**Contributor:** EkStep Foundation — [[people-orgs/ai-diffusion-pathways]]
**Contributed:** 2026-05-20
**Last updated:** 2026-05-20
**Times referenced:** 0

## Context

When a farmer calls a number and receives advice about a disease in their crop, they face a question before they follow that advice: who is speaking? Who stands behind this? What happens if it is wrong?

For populations who have relied on extension workers, cooperative officers, and government departments as their advisory authorities, the answer to this question determines whether the advice is followed or dismissed. It determines whether the system is adopted or abandoned.

Nandan Nilekani named the constraint directly: "When the monsoon is delayed, people want to know who stands behind a recommendation. Citizens tend to trust institutions rather than algorithms. For AI to be adopted by a whole population, it must carry the credibility of trusted institutions, with traceable and verifiable authority." 🟡

Most AI advisory deployments assign the AI an identity. The system presents itself — as a brand, a product, a chatbot. This is the default. It is also the design choice that fails with populations who have no reason to trust an algorithm they have never encountered before, from an entity they have no prior relationship with.

The next adopter who is trying to build adoption with a rural population that is sceptical, that has been misled by digital systems before, or that does not know who is accountable for AI-generated advice — is in the situation this pathway addresses.

## Shift map

| Shift | Summary | Documented? |
|---|---|---|
| A1 Problem framing | Not the primary focus of this pathway | Not documented |
| A2 Data posture | Not the primary focus of this pathway | Not documented |
| A3 Existing assets | The institution's existing credibility, established relationships, and authorised knowledge — these are the assets that make the AI trustworthy | ✓ |
| A4 Proof mechanism | Proof that the system works is proof that the institution's knowledge reached the farmer — the institutional brand absorbs the success and must also absorb the failure | ✓ |
| B1 Model choice | Model must cite its source on every claim; model must not assert institutional knowledge it cannot trace to an authorised source | ✓ |
| B2 Data sovereignty | Institutional data stays with institutions — which means the institution's name can legitimately appear on the advice, because the advice genuinely derives from the institution's data | ✓ |
| B3 Vendor independence | AI vendor cannot be the authority — the institution is the authority. Vendor independence is a structural consequence of the authority assignment | ✓ |
| B4 DPG vs instance | Not the primary focus of this pathway | Not documented |
| C1 Framing | FROM "commission a technology product" TO "authorise your institution's knowledge to be made accessible and stand behind what it says" — the system is an expression of institutional commitment, not a vendor product | ✓ |
| C2 Resistance | When the AI is clearly subordinate to the institution — it speaks as the institution, not for itself — internal resistance from staff who fear being replaced is reduced; the AI is positioned as extending the institution's reach, not substituting for it | ✓ |
| C3 Institutional knowledge | The decision about what the AI can and cannot say in the institution's name is institutional knowledge that must be documented and governed; it does not transfer automatically between deployments | ✓ |
| D1 Ecosystem design | Partners must understand their role in the authority chain: they contribute knowledge or data; the institution remains the named authority for whatever the system says | ✓ |
| D2 Trust source | The institution is the D2 trust source — explicitly, by design. Every response names the institution whose knowledge it draws from. The AI is not a trust source; it is the delivery mechanism for the institution's trust | ✓ |
| D3 Coordination mechanism | Not documented for this pathway specifically | Not documented |
| D4 Network operator | The network operator is the institution that says "this runs in my name" — and means it through sustained engagement, not just a contract signature | ✓ |
| E1 Training timing | Not documented for this pathway | Not documented |
| E2 Training depth | Extension officers must understand that the AI speaks as the institution — and be able to explain that to farmers. Without this understanding, they cannot support or correct the system in the field | ✓ |
| E3 Agency test | "Informed, therefore powerful to make choices" — when the farmer knows the institution stands behind the advice, the advice is actionable. The agency test is partly a trust test: does the farmer trust the source enough to act on it? | ✓ |
| F1 Velocity | Institutional alignment — securing authorisation to speak in the institution's name — is a pre-deployment task, not something that can be added after launch | ✓ |
| F2 Governance | What the AI can and cannot say in the institution's name must be governed. This includes: escalation paths when the AI cannot answer; guardrails on advice that could cause harm; review processes when field evidence contradicts the AI's response | ✓ |
| F3 Sustainability | The institution's continued standing behind the system is a sustainability condition; if the institution withdraws its name, the trust architecture collapses regardless of the technology | ✓ |
| F4 Pilot to deployment | The first concrete decision is nominate a named Agri Secretary sponsor and nodal officers across agriculture, IT, and field operations — the institutional commitment must be named, not assumed | ✓ |

## Playbook

### What was done and why

In MahaVISTAAR, the Department of Agriculture, Maharashtra made a design commitment that shaped every subsequent decision: the AI does not become the advisory authority. The institution does. Every response cites the Department of Agriculture and the relevant state agricultural university. The AI's identity is subordinated to the institution's identity. 🟡

This was not a branding decision. It was an accountability decision. The institution — not the technology vendor, not the platform operator, not the AI itself — is responsible for every answer the system gives. The farmer who acts on wrong advice has recourse to the institution that gave it. 🟡

The first concrete action this required: nominating a named Agri Secretary sponsor and nodal officers across agriculture, IT, and field operations. "A pathway cannot emerge from vendor activity alone. It needs named public ownership." 🟡 This is a system leadership decision, and it must happen before deployment, not after.

Amul's Sarlaben named the system to encode the institution's relationship with its intended users. "Sarlaben" is what a dairy cooperative member in Gujarat would call a knowledgeable female relative who helps with practical problems. The name signals: this system is for you, in your language, built on the cooperative's knowledge of your animals. When Sarlaben says something about a farmer's cattle, it draws from the cooperative's 50 years of records — and Amul's institutional standing backs that claim. 🟡

The governance consequence: what the AI can and cannot say in the institution's name must be documented and enforced. The moderation layer (Layer 3 of the system architecture) classifies queries and enforces boundaries — not just for safety, but for institutional appropriateness. "Policy-sensitive" queries are a category that every institution must define for itself. The AI cannot answer a question the institution has not authorised it to answer. 🟡

### Key decisions

| Decision | Options considered | What was chosen | Why |
|---|---|---|---|
| Who is the authority? | AI system as authority; institution as authority | Institution as authority; AI as delivery layer | "Citizens tend to trust institutions rather than algorithms" — the institutional credibility that drove adoption over decades cannot be transferred to a new AI brand overnight 🟡 |
| How is authority signalled? | System brand; vendor branding; institution named in every response | Institution named in every response as the source of every claim | Trust is traceable only if the source is named; unnamed authority is indistinguishable from an AI opinion 🟡 |
| Who nominates institutional ownership? | Vendor nominates; committee nominates; senior official nominates personally | Named Agri Secretary sponsor nominated by the institution, not by the vendor | "A pathway cannot emerge from vendor activity alone. It needs named public ownership." — accountability requires a named person, not a committee 🟡 |
| System naming | Technology product name; government scheme name; name signalling the intended user | Name signalling the intended user and their relationship to the institution (Sarlaben) | Name is the first trust signal the user encounters; it encodes who this is for and who stands behind it 🟡 |
| What happens when the AI cannot answer? | AI generates a best-effort response; AI says it does not know; AI directs to institutional contact | AI says it does not know and provides the institutional contact relevant to the query | Institutional authority requires institutional honesty; a system that confabulates advice damages the institution's credibility, not just the vendor's 🟡 |

### What worked

🟡 **"The farmer trusts the system because the institution stands behind every answer."** Adoption rates (440,000 queries/month in MahaVISTAAR; 3.6 million producers reached in Sarlaben; 97%+ positive feedback rate) are the evidence that institutional backing drove adoption rather than product marketing.

🟡 **PM Modi's endorsement of Bharat-VISTAAR at the India AI Impact Summit.** Political endorsement at the highest level functions as the same mechanism at national scale: the AI is trusted because institutions — in this case the highest levels of government — stand behind it. The mechanism is the same; the scale is different.

🟡 **Institutional credibility survived the technology learning curve.** During the pioneer deployment in Maharashtra, the system absorbed nine months of operational learning — dialect variation, API instability, trust-building with farmers. The institutional authority meant that farmers who encountered early errors attributed them to the system needing improvement, not to a fundamental reason not to trust the institution. The institutional backstop absorbed the technology's early failures.

🟡 **Source citation created an audit mechanism.** When advice is wrong, the institution whose data produced it can be identified. This feedback loop drove data quality improvements that a general-purpose AI system without source attribution could not have produced.

### What failed or caused friction

🟡 **Institutional alignment is pre-deployment work, not concurrent.** The Department of Agriculture's data-sharing authorisations across universities, weather services, market data systems, and scheme delivery platforms were not vendor work — they were system leadership work. This work cannot start after the technology is commissioned. It must complete before the technology is deployed. Adopters who commission the technology first and seek institutional alignment second encounter the delay where it is most costly — just before launch.

⬜ **The authority assignment must be maintained through staff rotation.** In government contexts, the named Agri Secretary sponsor rotates. The institutional authority does not automatically transfer to their replacement. The governance design must survive individual transitions — which means the commitment must be documented in institutional process, not held in the memory of a specific official.

### What would be done differently

Not documented in this source. The pathway evidence suggests the institution-as-authority design is treated as a foundational commitment that was right from the start — specific retrospective reflection is not available here.

## Toolkit

| Asset | Type | Description | Available |
|---|---|---|---|
| Institutional onboarding guides | Governance template | Referenced in OAN tech stack as a building block | Referenced but not linked in source 🟡 |
| Collaboration blueprint | Governance model | Governance model, enabler network, institutional arrangements — the non-technical component of the OAN pathway | OAN open source building blocks 🟡 |
| Moderation layer specification | Technical component | What the moderation layer classifies as valid, non-agricultural, unsafe, or policy-sensitive — each institution must define policy-sensitive for their context | Part of OAN open source building blocks 🟡 |

## Safety and trust notes

The institution-as-authority design creates the highest available accountability structure for an AI advisory system — and therefore the highest obligation to govern what the AI says. The guardrail is specific: no claim can be made without a verifiable institutional source. A system that cannot cite a source must surface the gap, not fill it with inference.

The escalation path — "when the AI cannot answer, direct to institutional contact" — is a safety design, not a quality concession. Farmers who get a confident wrong answer from a system they trust are harmed more than farmers who get "I don't know — here is who to ask." See [[concepts/seven-layer-architecture]] for the moderation layer detail.

## Policy and regulation notes

The question of who authorises an AI to speak in a government institution's name is a governance and potentially a legal question in many jurisdictions. The answer in this pathway's documented deployments: the Agri Secretary or equivalent senior official nominates institutional ownership by name. This nomination should be documented in a formal governance instrument, not left as an informal understanding. Not documented further in source.

## Related pathways

- [[pathways/voice-first-access-design]] — Voice carries institutional identity in a direct and audible way; voice-first and institution-as-authority are mutually reinforcing
- [[pathways/federated-data-architecture]] — Institutional data stays with institutions, which is what makes the institution's name legitimately appear on the advice
- [[pathways/enabler-ecosystem-assembly]] — All 54 enablers operate within an authority hierarchy; this pathway defines the top of that hierarchy

## Related concepts

- [[concepts/network-operator-role]] — The network operator is the entity that plays the D4 role in the institution-as-authority design
- [[concepts/dpi-ai-frame]] — The DPI+AI frame is the architectural expression of institution-as-authority: AI as delivery layer, institution as data and authority source
- [[concepts/proof-types-demonstration-experiential]] — The proof that the institution-as-authority design works is partly experiential — the Amul CEO's conversion when he saw his own data demonstrate what the system could do

## Lineage

No predecessor pathway — this is a first-generation pathway built from MahaVISTAAR as pioneer deployment.
