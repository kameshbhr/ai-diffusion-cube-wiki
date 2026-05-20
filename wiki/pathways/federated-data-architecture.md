---
type: pathway
deployment: mahavistaar
dimensions: [architecture]
sector: agriculture
geography: Maharashtra, Gujarat, India national
contributor: ekstep-foundation
contributed: 2026-05-20
last-updated: 2026-05-20
times-referenced: 0
---

# Federated Data Architecture

**One-line summary:** Connect institutional data sources at query time rather than copying them centrally — enabling AI advisory without requiring data ownership transfer, and making deployment possible before any data cleaning has happened.

**Deployment source:** MahaVISTAAR (reference implementation) — [mahavistaar](../deployments/mahavistaar.md); [amul-sarlaben](../deployments/amul-sarlaben.md)
**Contributor:** EkStep Foundation — [ai-diffusion-pathways](../people-orgs/ai-diffusion-pathways.md)
**Contributed:** 2026-05-20
**Last updated:** 2026-05-20
**Times referenced:** 0

## Context

The most common institutional barrier to deploying AI advisory systems is data. Institutions say: our data is not clean enough, our data cannot be shared, we would need to consolidate data before we could do anything with it. Each of these is a version of the same incorrect assumption: that centralised data is a prerequisite.

The MahaVISTAAR deployment found the opposite. Maharashtra had agricultural university knowledge bases, weather services from IMD, market data from 307 APMCs, 40+ government schemes in MahaDBT, and farmer registries in AgriStack. None of these talked to each other. Departments had never queried their own data together. The question was not "how do we clean and consolidate this data?" The question was: "what can be joined, and under what governance?" 🟡

"Data connection, not data cleaning, was the intervention." 🟡

The next adopter who hears "we can't use AI until we fix our data" is in the situation this pathway addresses. The federated architecture is the response.

## Shift map

| Shift | Summary | Documented? |
|---|---|---|
| A1 Problem framing | Not the focus of this pathway | Not documented |
| A2 Data posture | FROM "we need clean, consolidated data before we can start" TO "deploy first; AI creates the demand signal that reveals which data connections matter" | ✓ |
| A3 Existing assets | APIs that existed but had never been called; institutional databases as existing assets requiring connection, not construction | ✓ |
| A4 Proof mechanism | "Departments asked 'whose data is right?' for the first time" — the act of connecting revealed contradictions that had always existed; connection created its own proof of value | ✓ |
| B1 Model choice | LLM must be structured to call tools and await their results before generating a response; "no tool = no answer" design requirement | ✓ |
| B2 Data sovereignty | Data does not move. Each institution retains ownership of its own data. The AI connects to data sources at the moment of query, with the farmer's consent, and returns results that cite their institutional origin | ✓ |
| B3 Vendor independence | AI layer sits above institutional data layer; because data stays with institutions, swapping or upgrading the AI model does not require renegotiating data ownership arrangements | ✓ |
| B4 DPG vs instance | The federated architecture is the DPG — the open protocol layer (Beckn) that allows institutions to participate without surrendering their data | ✓ |
| C1 Framing | Not the focus of this pathway | Not documented |
| C2 Resistance | Departments that had never shared data before were willing to expose APIs when they retained ownership; data sovereignty commitment reduced institutional resistance to sharing | ✓ |
| C3 Institutional knowledge | The governance of which institutions expose which APIs, under what consent architecture, is institutional knowledge that does not transfer automatically | ✓ |
| D1 Ecosystem design | Each data source is an ecosystem member; the ecosystem is not just implementation partners but also data providers | ✓ |
| D2 Trust source | Farmer receives institutional knowledge (cited to its source) delivered through AI interface — not an AI opinion; source citation is a design requirement | ✓ |
| D3 Coordination mechanism | Not documented for this pathway specifically | Not documented |
| D4 Network operator | Network operator authorises data-sharing agreements; without this role, cross-institutional API access cannot be governed | ✓ |
| E1 Training timing | Not documented for this pathway | Not documented |
| E2 Training depth | Not documented for this pathway | Not documented |
| E3 Agency test | Not documented for this pathway | Not documented |
| F1 Velocity | Because data does not need to be cleaned or consolidated first, deployment can begin with whatever data is currently accessible via API | ✓ |
| F2 Governance | Governance of the data access layer (consent architecture, API agreements, data residency compliance) is a separate governance task from governance of the AI layer | ✓ |
| F3 Sustainability | Institutional data sources remain stable as the AI model changes; infrastructure beneath the AI layer has a different cost and lifecycle curve from the AI layer itself | ✓ |
| F4 Pilot to deployment | The data connector approach and API integration methodology transfer across deployments; Ethiopia's evaluators assessed "what needed adaptation rather than construction" | ✓ |

## Playbook

### What was done and why

The foundational architectural decision in MahaVISTAAR: data stays with its legitimate owner. The AI does not copy institutional data into a central repository. It connects to data through APIs, with farmer consent, at the moment of query. 🟡

This was not a data-minimisation choice made for compliance reasons. It was an enabling choice made for speed and institutional alignment: "which institutions hold what data, under what governance can it be accessed, and what consent architecture is required" — these questions could be answered institution by institution, API by API, without requiring a pre-deployment data integration project. 🟡

The result was a two-way signal: institutional data reaches the farmer at the moment of decision; anonymised, aggregated usage signals return to institutions (which advisories are being accessed, which crops have insufficient guidance, which regions show stress patterns). Neither direction requires data to live anywhere other than where it already lives. 🟡

In Amul's Sarlaben, the same architecture operated on a cooperative's proprietary data: 2 billion milk procurement transactions, records on 30 million cattle, 1,200+ veterinary doctor records. This data had existed for 50 years and had never spoken back to the farmer who generated it. The federated architecture made it accessible without moving it anywhere. "The cooperative's institutional data remains in the cooperative's systems. The AI reaches it, assembles the answer, and delivers it in Gujarati through a voice call to a feature phone. The institution did not change. The farmer's access to what the institution knew did." 🟡

The data access layer has specific infrastructure: an API gateway to handle concurrent outbound calls to multiple external services with timeout and fallback logic; a caching layer (Redis or equivalent) for frequently accessed data like weather forecasts and mandi prices; fallback routing for data sources with geographic gaps (e.g., weather station coverage). Every claim flows through a verified tool call — the guardrail is architectural: "no tool = no answer; no source = no claim." 🟡

### Key decisions

| Decision | Options considered | What was chosen | Why |
|---|---|---|---|
| Central repository vs. federated connection | Copy institutional data into central warehouse; connect to institutional data at query time | Connect at query time; data stays with institutions | Institutions refused to transfer data ownership; federated approach removed this barrier entirely; also produces more up-to-date answers (live feeds vs. stale copies) 🟡 |
| Data quality prerequisite | Require data cleaning before deployment; deploy without cleaning | Deploy without cleaning; let AI create demand for data improvement | "Data connection, not data cleaning, was the intervention" — connecting data revealed contradictions that motivated cleaning; cleaning without deployment motivation stalls 🟡 |
| Consent architecture | System uses data without explicit farmer consent; farmer consents once at registration; farmer consents per query | Farmer consent at query time, with each data source cited in the response | Each institution must be visible to the farmer as the source of the data it holds; trust and accountability require traceable provenance 🟡 |
| AI model as data custodian | AI model holds advisory data internally (fine-tuned); AI model calls external tools for data | AI model calls external tools; internal knowledge limited to reasoning and orchestration | Institutions must remain the source of truth; model fine-tuning would make institutional data invisible inside the model and untraceable in the response 🟡 |
| Source attribution | AI responses without source citation; AI responses cite institutional sources | Every claim cites its institutional source | "The farmer does not receive an AI opinion — they receive institutional knowledge, delivered through an AI interface" — source citation is the trust architecture 🟡 |

### What worked

🟡 **Removing the data prerequisite unlocked deployment.** Maharashtra had APIs that existed for years but had never been called. No data cleaning was required to start. The first connection revealed contradictions departments had not previously been forced to confront — and created internal motivation to address them.

🟡 **Institutional alignment improved after deployment, not before.** "When AI connected them, officials asked 'whose data is right?' for the first time." Connection created the institutional dialogue that cleaning programmes had failed to create. The sequence was: connect first, discover the discrepancies, then resolve them.

🟡 **Data sovereignty commitment reduced resistance.** Departments and institutions that had historically refused to share data were willing to expose APIs when they retained ownership. The federated model converted a barrier into a route.

🟡 **Amul's 50 years of cooperative data became an asset overnight.** Two billion milk procurement transactions and records on 30 million cattle — data that had existed for decades and had never reached the farmer — became the foundation of a personalised advisory system in three weeks. The architecture that made this possible was the same architecture: connect at query time, data stays in cooperative systems.

🟡 **Model replaceability.** Because data stays with institutions, the AI layer can be upgraded or replaced without renegotiating data relationships. "AI models change rapidly; institutional data systems must remain stable."

### What failed or caused friction

🟡 **Geographic gaps in data sources required fallback logic.** Weather station coverage has geographic gaps in rural Maharashtra. The system expanded search radii and built graceful fallbacks — which requires intelligent routing logic and must be designed in, not added after users complain about missing weather data.

🟡 **Concurrent API calls require careful capacity planning.** When a farmer calls and the system simultaneously queries IMD (weather), APMC (mandi prices), and the agricultural university (advisory), the API gateway must handle this concurrently with timeout logic. Latency spikes when any one source is slow.

⬜ **The "whose data is right?" problem surfaces in production.** When institutional data sources contradict each other (different prices from different APMC feeds, advisory that conflicts with another institution's advisory), the system must resolve or present the contradiction. How this is governed in practice — which institution's data takes precedence — is not documented in this source.

### What would be done differently

Not documented in this source. The source presents the federated approach as established practice, not as something the deployers reflect on retrospectively.

## Toolkit

| Asset | Type | Description | Available |
|---|---|---|---|
| Data Network Adapters | Technical component | OAN open source building block; standardised connectors for common agricultural data sources | OAN open source building blocks 🟡 |
| Beckn protocol implementation | Technical component | Open network protocol for data discovery and exchange across institutional boundaries | Open-source 🟡 |
| API gateway configuration | Technical component | Timeout, fallback, and concurrent call management for multi-source queries | Referenced in architecture documentation 🟡 |
| Caching layer templates | Technical component | Redis or equivalent configuration for high-frequency data (weather, mandi prices) | Referenced but not linked in source 🟡 |
| Consent architecture framework | Governance template | How to structure farmer consent for multi-source data access | Part of OAN collaboration blueprint; referenced but not linked 🟡 |

## Safety and trust notes

The guardrail "no tool = no answer; no source = no claim" is an architectural safety requirement, not a quality preference. If a data source is unavailable, the system must surface that gap rather than generate an answer from internal knowledge. Advisory given without a cited institutional source is an AI opinion, not institutional knowledge — and it may be wrong in ways that are harmful to the farmer. 🟡

Source attribution also creates auditability: when an advisory is wrong, the institution whose data produced it can be identified and the error corrected. Without source attribution, there is no audit trail and no correction mechanism.

## Policy and regulation notes

Government data residency rules (NIC hosting requirements) may apply to data flowing through the API gateway, particularly for sensitive data (land records, scheme eligibility). Dedicated leased lines or VPN tunnels may be required for secure government data exchange. Not documented in detail in source.

## Related pathways

- [voice-first-access-design](voice-first-access-design.md) — Voice is the interface layer delivered on top of the federated data infrastructure
- [institution-as-authority-trust](institution-as-authority-trust.md) — Source attribution and institutional data ownership are the technical implementation of the institution-as-authority design
- [enabler-ecosystem-assembly](enabler-ecosystem-assembly.md) — Each data enabler in the ecosystem is a node in the federated network; this pathway describes how to identify and connect them

## Related concepts

- [federate-vs-aggregate-data](../concepts/federate-vs-aggregate-data.md) — Concept-level treatment of this decision
- [dpi-ai-frame](../concepts/dpi-ai-frame.md) — The federated data model is the practical expression of the DPI+AI frame
- [seven-layer-architecture](../concepts/seven-layer-architecture.md) — Layers 6 (Live Data Sources) and 7 (DPI Foundation) are the implementation of this architecture
- [deploy-first-data-posture](../concepts/deploy-first-data-posture.md) — The data posture shift that enables federation: deploy first, clean later

## Lineage

No predecessor pathway — this is a first-generation pathway built from MahaVISTAAR as pioneer deployment.
