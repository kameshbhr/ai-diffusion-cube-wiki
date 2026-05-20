# Dimension 4: Ecosystem

**One-line:** Who executes — the partners, enablers, and stakeholders assembled, and how coordination and trust work across them.

---

## What this dimension covers

No AI deployment at scale is executed by a single organisation. The ecosystem dimension maps who is in the room, what roles they play, who holds the network together, and how trust is established across actors who may have different incentives, languages, and timelines.

- **D1 — Ecosystem design:** Who the partners are, what roles they play, how the ecosystem was assembled. A four-layer taxonomy helps inventory: institutional/governance (funders, orchestrators, government bodies), technology/AI (R&D, language models, knowledge contributors), structured data (live feeds), and knowledge/documents (guidelines, publications, research).
- **D2 — Trust source:** Where trust in the deployment originates. In public-sector deployments, trust flows from a specific institution, individual, or community structure — not from the technology itself.
- **D3 — Coordination mechanism:** How partners coordinate. The traditional approach requires full consensus before work begins; AI enables coordination before full consensus exists.
- **D4 — Network operator:** Who holds the network together — who says "this runs in my name." See [[concepts/network-operator-role]] for full treatment.

---

## What the wiki currently holds

One foundational source: "The Six Orthogonal Shifts - detailed version 2" (AI Diffusion Pathways initiative). Strong field evidence on D1 (from MahaVISTAAR's 54-enabler ecosystem), D2 (trust source in farmer-facing deployments), D4 (network operator documented across four institutional types). D3 (coordination mechanism) has strong pattern-level documentation.

---

## Key patterns across pathways

**D1 — Ecosystem design:**
🟡 MahaVISTAAR required 25+ organisations across government departments, model providers, voice partners, funders, data providers, and domain experts. 54 enablers mapped across four layers. The composition varies — Maharashtra needed 25+ organisations, Amul needed fewer because it brought its own cooperative infrastructure, Ethiopia needed different partners entirely — but the four-layer structure holds constant.

⬜ A four-layer taxonomy helps any adopter inventory their ecosystem:
1. Institutional and governance: funders, orchestrators, government bodies
2. Technology and AI: R&D, language models, knowledge contributors
3. Structured data: live feeds
4. Knowledge and documents: guidelines, publications, research

⬜ The pathway ecosystem requires an incentive structure: those who contribute their decomposed experience get access to the full knowledge base, visibility at global summits, and early access to funding opportunities. Those who do not contribute lose access. The currency is knowledge, not money.

⬜ Dead ends must be managed: when a contributor's deployment stops working, that node must be flagged — not deleted. The failure itself is valuable knowledge. Flag it so future adopters are routed around it with appropriate warnings.

**D2 — Trust source:**
🟡 Trust cannot be bought. In one deployment (not named), conversations alone took 18 months before serious work could begin. There are no shortcuts.

🟡 A company with 25 lakh farmers can have all the right information and still not be trusted — because the farmer distinguishes between information and trusted information. The same advice from a commercial seller sounds like a sales pitch; from a university or government extension service, it sits as certain.

🟡 The AI must not speak as itself — it must speak as the institution. MahaVISTAAR cites the Department of Agriculture and state universities in every response. Sarlaben is named to signal that it's built for the woman producer. Every response carries institutional attribution. The AI's identity must be subordinated to the institution's identity.

🟡 Voice carries trust in a way text often does not. A Marathi-speaking farmer hearing advice in Marathi, from a number associated with the state agriculture department, trusts it differently from the same advice as English text on a website. Trust source and channel choice are deeply connected at the user's end, even when they are separable at the design level.

**D3 — Coordination mechanism:**
⬜ The traditional approach — requiring all stakeholders to agree on data formats, metrics, and governance structures before work begins — is what creates 18-month pre-work timelines.

⬜ AI offers a different mechanism: it can work with unstructured, heterogeneous inputs from multiple actors and create shared representations without requiring everyone to first agree. This requires a shared language — not shared metrics or formats, but a common way of seeing the problem. When multiple actors decompose their experiences against the same six-shift framework, they create a shared language without having to agree on standards.

🟡 The Bharat-VISTAAR model — a national layer with MahaVISTAAR, Amul, Bihar Krishi, and Ethiopia as nodes — shows hub-and-spoke federation in practice. Each node retains local specificity; the national layer provides shared knowledge base, scheme connectivity, and integration.

⬜ Open standards like Beckn provide a coordination substrate: standardised discovery and interaction across independent providers without requiring everyone to agree on data formats first.

**D4 — Network operator:**
🟡 An ecosystem without a committed network operator is a coalition without a spine. Without it, partners default to overreach or blame. In one project (deployment not named), the same institution that accused its operational partner of rubber-stamping vendor decisions also refused to participate in the steering committee that was supposed to govern those decisions. Accusation and abdication from the same source.

🟡 "The hunter and the farmer have different roles. The mistake is asking farmers to hunt and hunters to farm."

🟡 The network operator role has been played by four different institutional types:
- State government department (MahaVISTAAR)
- National ministry (Bharat-VISTAAR)
- Cooperative (Amul)
- National transformation institute (Ethiopia/ATI)

⬜ Any entity that can say "this runs in my name" and has institutional standing to back that claim can play this role. What matters is not the type of entity but the commitment.

---

## Key decisions an adopter faces

| Decision | What the evidence shows |
|---|---|
| Who should be in the ecosystem? | Use the four-layer taxonomy to inventory. Do not build what the ecosystem can provide. Identify what you provide and who is accountable if it fails. |
| How is trust established for end users? | Trust flows from the institution, not the technology. The AI must speak as the institution. Channel choice (voice vs text) affects trust as much as content does. |
| How to coordinate without requiring full consensus first? | Use a shared framework as shared language. Start working together and let consensus emerge from collaboration, rather than requiring it as a prerequisite. |
| Who is the network operator? | Identify before deployment begins. Any entity with institutional standing that will say "this runs in my name" can play this role. If no one will say this, the ecosystem has no spine. |

---

## Common failure modes

- **Building everything yourself.** You are one part among many. The complexity of the ecosystem can be simplified: paid services, free services, and the deploying government. Map your role and your accountability — not everyone else's.
- **Waiting for trust before starting.** Trust cannot be bought and cannot be forced. But the trust-building process must begin early — 18 months was the timeline in one documented case. This is not a parallel track to the technical work; it is part of the deployment timeline.
- **Requiring consensus before coordination.** The traditional approach guarantees 18-month delays. AI enables coordination before consensus. Use a shared language first.
- **Diffuse accountability.** "It's everyone's responsibility" means it is nobody's. Without a named network operator, the first serious conflict produces accusation and abdication — and the deployment stalls.
- **Deleting failed nodes.** When a deployment in the ecosystem fails, flag it — don't delete it. The failure is valuable knowledge. Future adopters need to be warned, not left to discover the same dead end.

---

## Pathways in this dimension

- [[deployments/mahavistaar]] — D1 (54 enablers, four-layer ecosystem); D2 (trust via DoA attribution, voice-first)
- [[deployments/bharat-vistaar]] — D3 (hub-and-spoke federation); D4 (national ministry as network operator)
- [[deployments/amul-sarlaben]] — D4 (cooperative as network operator)
- [[deployments/ethiopia-ati]] — D4 (ATI as network operator)

---

## Gaps

- D1: the process of assembling the ecosystem (how partners were identified and recruited) is not documented for any deployment.
- D2: the 18-month trust-building timeline is documented but the specific steps taken during that period are not.
- D3: the Beckn protocol use is referenced but not documented in practice for any specific deployment.
- D4: the failure case (accusation + abdication) is documented without naming the deployment. Field evidence with named examples would strengthen this gap significantly.
