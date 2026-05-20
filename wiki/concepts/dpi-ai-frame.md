# DPI+AI Frame

**Dimension(s):** B: Architecture (B2 Data sovereignty, B3 Vendor independence, B4 DPG vs instance); C: Institution (C1 Framing)
**Type:** Framework

## What this is

DPI+AI is a specific architectural frame — not simply an AI application built for a sector, but something structurally different. Understanding the distinction matters for both deployers and evaluators, because it determines how the system should be governed, how trust is established, and how it sustains itself when models change.

**What DPI is:**

Digital Public Infrastructure is shared, foundational digital infrastructure — built as reusable building blocks for public benefit, operating on open standards, designed to be interoperable across institutions and contexts. The analogy: roads do not tell vehicles where to go. They create the common foundation on which many vehicles can travel without each needing to lay their own road. DPI is the digital equivalent: shared rails on which many services can run, rather than each service building its own track. India's Aadhaar (1 billion+ people, 164 billion authentications) and UPI (20 billion transactions/month, world's largest real-time payment system) are the reference cases. 🟡

Agricultural DPI extends the logic into the agriculture sector: foundational layers (national identity, payments, data exchange) extended with sector-specific building blocks (farmer registries, farm registries, crop-sown registries, soil health data, market data, institutional advisory databases). Each building block is infrastructure — modular, interoperable, designed to be combined in different configurations — not a product. 🟡

**What AI adds:**

AI does not replace the DPI frame. It operates within it, as a layer above it. The distinction is precise and important. Institutions — agricultural universities, state agriculture departments, cooperatives, national research institutes — remain the source of truth. They generate authoritative data. They certify advisories. They run schemes. That institutional authority does not transfer to the AI system. It stays where it belongs. 🟡

What AI provides is the interface, coordination, and delivery layer: the capability to receive a farmer's voice query in their language, interpret intent, reach across multiple institutional data sources simultaneously, assemble an answer, and return it in the farmer's language within seconds. AI scales what institutions already know. It does not substitute for what institutions know. 🟡

## Why it matters

The DPI+AI frame has three design consequences that determine whether a deployment is an isolated application or a piece of public infrastructure:

**1. Federated data, not centralised:** Data does not move into a single repository. Each institution retains ownership. The AI connects to data sources at the moment of query, with the farmer's consent, and returns results that cite their institutional origin. The farmer receives institutional knowledge delivered through an AI interface — not an AI opinion. 🟡

**2. Voice-first as architectural requirement:** The inclusion commitment is structural, not optional. See [[concepts/inclusion-architecture]].

**3. Modular and replaceable AI layer:** No AI model is permanent. The infrastructure beneath — institutional data sources, open network protocols, farmer registries — remains stable as models evolve, are replaced, or upgraded. This preserves institutional continuity while enabling continuous AI improvement. It means the system does not lock the institution into a single vendor or model. 🟡

## What the pathways show

🟡 **MahaVISTAAR as DPI+AI in practice:** Maharashtra had all the components — agricultural university knowledge bases, IMD weather services, 307 APMC market data sources, 40+ government schemes in MahaDBT, farmer registries in AgriStack. None talked to each other. MahaVistaar is the open network — built on OAN's open source building blocks — that places all of these on shared rails. The AI agentic orchestrator sits above those rails: it receives the farmer's voice query in Marathi, understands intent, reaches simultaneously to the university advisory database, the IMD weather API, and the APMC price feed, assembles the answer, cites its institutional sources, and speaks back. The state agricultural university did not become an AI organisation. It continued certifying advisories. The AI made those advisories reachable by a farmer in Kihim village on a basic phone. 🟡

🟡 **Amul/Sarlaben as DPI+AI in practice:** Amul had fifty years of its own data — 2 billion milk procurement transactions, records on 30 million cattle, 1,200+ veterinary doctor records. This data existed and had never spoken back to the farmer who generated it. Sarlaben is the AI layer placed on top of that cooperative data infrastructure. When a woman dairy producer calls with a question about her cattle, the system draws from her specific animal's records — not from a generic livestock database — and returns personalised guidance. The cooperative's institutional data remains in the cooperative's systems. The AI reaches it, assembles the answer, and delivers it in Gujarati through a voice call to a feature phone. The institution did not change. The farmer's access to what the institution knew did. 🟡

🟡 **The two-way signal:** The system is not one-directional. It brings trusted data and advisories to farmers at the moment of decision — and it returns signals (anonymised, aggregated) back to institutions: which advisories are being accessed, which crops have insufficient guidance, which regions are showing stress patterns. Institutions listening at population scale, continuously learning from real field interactions — something no previous system of agricultural extension could achieve. 🟡

## The governance implication for deployers

A commitment to the DPI+AI frame is a commitment to three things simultaneously:
1. Your institution's data must be made accessible via API (you become a data provider in the network, not just a commissioner of a product)
2. You authorise the AI to speak in your name — and must govern what it says and what it cannot say
3. You accept that the AI layer is replaceable; your governance must not be tied to a specific model or vendor

These are not technical decisions. They are institutional decisions — and they are the system leadership decisions that determine whether a deployment takes root or remains a pilot. 🟡

## Pathways that cover this

- [[deployments/mahavistaar]] — The reference implementation of DPI+AI in agriculture
- [[deployments/amul-sarlaben]] — Cooperative data commons as DPI+AI
- [[deployments/bharat-vistaar]] — National DPI rail; the coordination layer that makes the frame operate at national scale
- [[deployments/ethiopia-ati]] — DPI+AI adapted to a new country context

## Related concepts

- [[concepts/federate-vs-aggregate-data]] — The data architecture decision that is the practical expression of this frame
- [[concepts/inclusion-architecture]] — The voice-first commitment that flows from the DPI+AI design principles
- [[concepts/seven-layer-architecture]] — The technical implementation of DPI+AI across seven layers
- [[concepts/network-operator-role]] — The institutional role that governs the whole
