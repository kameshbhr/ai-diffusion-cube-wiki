---
type: pathway
deployment: mahavistaar
dimensions: [ecosystem]
sector: agriculture
geography: Maharashtra, India (reference implementation)
contributor: ekstep-foundation
contributed: 2026-05-20
last-updated: 2026-05-20
times-referenced: 0
---

# Enabler Ecosystem Assembly

**One-line summary:** Identify what already exists before specifying what to build — an agricultural AI deployment does not assemble its ecosystem from scratch; it identifies and connects the 50+ enablers already operating in separate layers.

**Deployment source:** MahaVISTAAR — [[deployments/mahavistaar]]
**Contributor:** EkStep Foundation — [[people-orgs/ai-diffusion-pathways]]
**Contributed:** 2026-05-20
**Last updated:** 2026-05-20
**Times referenced:** 0

## Context

The instinct when planning an AI deployment is to specify what to build. The architecture, the data pipelines, the model, the interface. This instinct produces a construction plan — and construction is the wrong mental model for the kind of deployment this pathway documents.

The 54 enablers that make MahaVISTAAR function were not assembled for MahaVISTAAR. Most of them predate it — government schemes, university publications, weather services, language models, institutional mandates. They existed in separate systems, serving separate purposes, with no shared route to the farmer. "What OAN contributed was a common network layer — one that allowed these systems to be discovered, combined, and delivered as a coherent response to a single query from a field." 🟡

"OpenAgriNet does not build what already exists. It connects it." 🟡

The next adopter approaching their ecosystem design with a blank-slate "what do I need to build?" question is in the situation this pathway addresses. The better question is: what exists in four distinct layers — institutional/governance, technology/AI, structured data, knowledge/documents — and what does connecting it require?

## Shift map

| Shift | Summary | Documented? |
|---|---|---|
| A1 Problem framing | FROM "what should we build?" TO "what exists that can be connected, and under what governance?" — the evaluator task is inventory before specification | ✓ |
| A2 Data posture | Not the primary focus of this pathway | Not documented |
| A3 Existing assets | The 54 enablers are existing assets; the ecosystem assembly task is to identify them layer by layer before building anything | ✓ |
| A4 Proof mechanism | Not the primary focus of this pathway | Not documented |
| B1 Model choice | Technology/AI layer (Layer B) includes the language models and AI research institutions — choosing among them is downstream of knowing what exists in this layer | ✓ |
| B2 Data sovereignty | Data enablers (Layer C) each operate under their own data governance; connection requires understanding each source's governance, not transferring ownership | ✓ |
| B3 Vendor independence | The four-layer taxonomy is itself a vendor independence structure: no single vendor spans all four layers; each layer can evolve independently | ✓ |
| B4 DPG vs instance | Layer D (institutional & governance) and the open network protocol constitute the DPG substrate on which instances run | ✓ |
| C1 Framing | Not the primary focus of this pathway | Not documented |
| C2 Resistance | Not documented for this pathway specifically | Not documented |
| C3 Institutional knowledge | Knowing which enablers exist in each layer, who controls them, and how to initiate contact is institutional knowledge that does not transfer — each new context must conduct its own inventory | ✓ |
| D1 Ecosystem design | The four-layer taxonomy is the ecosystem design framework: A (institutional/governance), B (technology/AI), C (structured data), D (knowledge/documents). Each layer serves a distinct function; the ecosystem is healthy only when all four layers are represented | ✓ |
| D2 Trust source | Layer A (institutional/governance) is the trust layer: funders, government bodies, and orchestrators give the network legitimacy | ✓ |
| D3 Coordination mechanism | The common network layer (OAN protocol, Beckn) is the coordination mechanism: it allows independent enablers to participate without bilateral coordination with every other enabler | ✓ |
| D4 Network operator | The network operator convenes and maintains the relationships across all four layers; without this role, the inventory of enablers does not become a functioning network | ✓ |
| E1 Training timing | Not documented for this pathway | Not documented |
| E2 Training depth | Not documented for this pathway | Not documented |
| E3 Agency test | Not documented for this pathway | Not documented |
| F1 Velocity | Inventory-first accelerates deployment by revealing what does not need to be built; Ethiopia's three-month deployment was faster partly because the evaluators could assess what had already been built | ✓ |
| F2 Governance | Each layer has different governance requirements; institutional/governance layer requires formal agreements; data layer requires API and consent governance; knowledge layer requires content certification | ✓ |
| F3 Sustainability | Enablers in each layer have different sustainability curves; knowledge/document enablers (university publications) are more stable; structured data enablers (live price feeds) require ongoing operational maintenance | ✓ |
| F4 Pilot to deployment | The inventory conducted during pilot reveals which enablers are missing for scale; "the evaluator question shifts from 'can this be built?' to 'what does adapting this require here?'" | ✓ |

## Playbook

### What was done and why

The first evaluator task in every documented deployment was not specification — it was inventory. In Maharashtra, this meant mapping what already existed: state agricultural university knowledge bases, weather services, APMC market data, government scheme portals, farmer registries. The feasibility question was: what can be joined, and under what governance? 🟡

The MahaVISTAAR ecosystem's 54 enablers are structured across four layers, each with distinct function:

**Layer A — Institutional & Governance (13 enablers in MahaVISTAAR)**
Funders, orchestrators, and government bodies that make the system legitimate and sustainable. In MahaVISTAAR: Gates Foundation, World Bank, UNDP, EkStep Foundation (funders/support); EkStep, COSS, Samagra, Artha Global (orchestration/implementation); Department of Agriculture Maharashtra, Department of Livestock, Department of Fisheries, GoI Agri Ministry, DC Nandurbar, Maharashtra DBT (government bodies). Without this layer, the network has no institutional backing. 🟡

**Layer B — Technology & AI (8 enablers in MahaVISTAAR)**
Research institutions, language models, and knowledge contributors that make the system functional. In MahaVISTAAR: IIT Mumbai, IISc, Vassar Labs, India AI Mission (research & development); Bhashini, AI4Bharat, Karya (language & AI models); ICAR Universities/Market Info (knowledge contributors). This layer does not need to be built from scratch; it needs to be connected and integrated. 🟡

**Layer C — Data Enablers (Structured / System-Generated) (8 enablers in MahaVISTAAR)**
Live feeds and system-generated datasets that keep the system current and contextual. In MahaVISTAAR: APMC Price Data, Warehouse Data (WDRA), Custom Hiring Centre (CHC), KVK (Krishi Vigyan Kendra), IMD Forecast Data, Skymet Weather Data, Officer Data, Scheme Details Data. These are not built for the deployment — they are connected to it. 🟡

**Layer D — Knowledge & Document Enablers (25 enablers in MahaVISTAAR)**
Accumulated guidelines, publications, and practice manuals that make responses trustworthy. In MahaVISTAAR: 10 national/state programme guidelines (Nanaji Deshmukh, Digital Agriculture Mission, PMFBY, PMKSY, etc.); crop knowledge (crop PoPs from MPKV, VNMAU, PDKV across wheat, rice, sugarcane, pulses, oilseeds, onion, garlic); livestock & animal husbandry manuals; fisheries & aquaculture guidelines; research & reports (ICAR, university publications, national programme guidelines). The largest layer by count — and the one most likely to already exist in any agricultural context. 🟡

The inventory task maps each of these four layers for the adopter's own context: what exists, who controls it, what governance is required to connect it, what is missing.

### Key decisions

| Decision | Options considered | What was chosen | Why |
|---|---|---|---|
| Inventory sequence | Specify what to build, then inventory what exists; inventory what exists, then specify what to build | Inventory first, always | "Mapping what already exists before specifying what to build" — in every documented deployment, this sequence produced a shorter construction list and faster deployment 🟡 |
| Four-layer vs. flat partner list | List all partners without layer structure; organise partners by function into layers | Four-layer structure (institutional/governance, technology/AI, data, knowledge) | Each layer has different function, governance requirements, and sustainability curve; a flat list makes these differences invisible and makes gaps harder to identify 🟡 |
| Connection vs. construction | Build proprietary data sources; build proprietary knowledge bases; connect existing sources | Connect existing sources where they exist; build only where genuinely absent | "OAN does not build what already exists. It connects it." — construction where connection is possible wastes time, creates duplicate maintenance burden, and may produce worse quality than the authoritative source 🟡 |
| Beckn protocol vs. bilateral integration | Build bilateral API integrations with each enabler; use common open protocol | Common open protocol (Beckn) for discovery and exchange | Bilateral integration scales as n², requiring bilateral renegotiation for each new enabler; open protocol allows any compliant enabler to participate without bilateral arrangement 🟡 |

### What worked

🟡 **54 enablers without building 54 things.** MahaVISTAAR's ecosystem spans weather, market prices, university advisory, government schemes, farmer registries, and veterinary knowledge — none of which was built for MahaVISTAAR. Each existed in its institutional home; the deployment connected them.

🟡 **The inventory revealed the deployment's shape.** In Bihar, "the core design work" was assessing "which institutions hold what data, under what governance can it be accessed, and what consent architecture is required." The result: 850,000+ registered farmers, 50+ schemes, 38 districts — and two national awards.

🟡 **Ethiopia's inventory made a three-month deployment possible.** "Its evaluators could assess what had already been built and determine what needed adaptation rather than construction. The evaluator question shifts from 'can this be built?' to 'what does adapting this require here?'" The inventory methodology, not just the technical assets, was transferable.

🟡 **Open network protocol reduced bilateral coordination cost.** The Beckn protocol allows APMC price data, IMD weather data, and ICAR advisory content to participate in the same query response without each source needing to coordinate bilaterally with every other source.

### What failed or caused friction

⬜ **Layer A is the hardest to assemble and the most consequential if absent.** The institutional/governance layer requires formal agreements, budget alignment, and sustained senior commitment — it cannot be obtained through a vendor relationship or an MOU signed at a launch event. If this layer is thin, the network has no institutional backing, no resolution mechanism for conflicts, and no sustained identity.

⬜ **Layer D (knowledge/documents) requires content certification, not just ingestion.** University publications and programme guidelines must be authorised versions — the most current, the most locally applicable. Ingesting outdated or incorrect knowledge documents produces confident wrong answers. The certification process is institutional, not technical, and it requires ongoing maintenance as guidelines change.

🟡 **Geographic gaps in data sources are a known Layer C problem.** Weather station coverage gaps require fallback routing logic; some APMC feeds are more current than others; some scheme data is more reliably maintained than others. The inventory must assess data freshness and completeness, not just existence.

### What would be done differently

Not documented in this source. The pathway evidence describes the inventory-first approach as established practice.

## Toolkit

| Asset | Type | Description | Available |
|---|---|---|---|
| 54-enabler taxonomy for MahaVISTAAR | Reference | Full list of enablers across four layers as documented in OAN-DiffusionPathway.pdf | raw/OAN-DiffusionPathway.pdf 🟡 |
| Institutional onboarding guides | Governance template | Referenced in OAN tech stack as a reusable building block | OAN open source building blocks 🟡 |
| Data Network Adapters | Technical component | Standardised connectors for common agricultural data sources | OAN open source building blocks 🟡 |
| Beckn protocol | Technical component | Open network protocol for discovery and exchange across Layer C enablers | Open-source 🟡 |
| Collaboration blueprint | Governance model | Institutional arrangements for Layer A; how to establish data-sharing agreements, authorisation frameworks | OAN open source building blocks 🟡 |

## Safety and trust notes

Layer A (institutional/governance) is the safety layer in the ecosystem: it provides the authority chain that determines what the system can and cannot say in whose name. If Layer A is weak or informal, the safety architecture has no institutional backing — there is no one to escalate to when the AI gives advice that causes harm, and no one with authority to correct course.

Layer B (technology/AI) includes the moderation infrastructure — adversarial test sets, prompt injection defence, content safety classification. This is an ecosystem member requirement, not a deployment-by-deployment rebuild. See [[concepts/seven-layer-architecture]] for detail.

## Policy and regulation notes

Layer A enablers include government bodies whose participation may require formal inter-departmental orders, MoU signing, or budget line items. Layer C data enablers may include sources subject to data residency requirements (particularly AgriStack, land records). Layer D knowledge enablers may include copyrighted or restricted publications whose use requires licensing agreements. Each layer's governance requirements must be mapped as part of the inventory, not discovered after deployment. Not documented in further detail in source.

## Related pathways

- [[pathways/federated-data-architecture]] — The data enablers in Layer C are the sources connected in the federated architecture; this pathway identifies them; the federated architecture connects them
- [[pathways/institution-as-authority-trust]] — Layer A (institutional/governance) is the trust source; this pathway shows how to assemble it; institution-as-authority shows what it requires institutionally
- [[pathways/voice-first-access-design]] — The language and AI models in Layer B (Bhashini, AI4Bharat, Karya) are the voice infrastructure enablers

## Related concepts

- [[concepts/network-operator-role]] — The network operator is the role that convenes and sustains relationships across all four layers
- [[concepts/dpi-ai-frame]] — The DPI is the protocol layer (Layer 7 of the system architecture) that makes four-layer ecosystem participation possible without bilateral coordination
- [[concepts/federate-vs-aggregate-data]] — The data enablers in Layer C are connected, not consolidated

## Lineage

No predecessor pathway — this is a first-generation pathway built from MahaVISTAAR as pioneer deployment.
