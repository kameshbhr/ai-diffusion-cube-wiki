# MahaVISTAAR

**Organisation:** Department of Agriculture, Government of Maharashtra
**Sector:** Agriculture
**Geography:** Maharashtra state, India
**Scale:** 342,000+ unique users 🟡; 1.67 million+ farmer questions answered 🟡; 791,000+ sessions 🟡; 17 lakh farmers reached via proactive voice alerts daily 🟡; 440,000 total categorised queries/month (December 2025) 🟡; 205,000 of those crop/pest queries 🟡; 97%+ positive feedback rate (98.5% most recent measurement) 🟡
**Period:** Pioneer deployment; active as of December 2025 (start year not documented in source)
**Contact / network:** [[people-orgs/ai-diffusion-pathways]]
**Access:** Short code 155313 (voice call, any phone) 🟡

## One-paragraph summary

MahaVISTAAR is the pioneer deployment of the AI diffusion pathway for agricultural advisory — the reference case from which all subsequent deployments have drawn transferable assets. The Department of Agriculture, Maharashtra deployed an AI system that connected existing but siloed databases (APIs that had existed for years but had never been called) to deliver agricultural advice in Marathi via voice interface. The system speaks as the institution — every response cites the Department of Agriculture and state universities. It started with inbound queries (farmers calling with questions) and added outbound proactive alerts (17 lakh farmers daily via proactive personalised voice alerts; 15 stage-based advisories proactively across the crop calendar). It took 9 months to deploy as a pioneer, establishing the architecture, governance frameworks, and failure-mode library that made Ethiopia's deployment possible in 3 months and Amul's in 3 weeks.

## Pathways from this deployment

- [[pathways/voice-first-access-design]] — Voice as structural inclusion solution; short code 155313; ASR/TTS architecture; trust through institutional voice
- [[pathways/federated-data-architecture]] — Connecting APIs that existed but had never been called; "no tool = no answer"; data stays with institutions
- [[pathways/institution-as-authority-trust]] — Agri Secretary sponsor named; every response cites institutional source; AI subordinate to institution's identity
- [[pathways/enabler-ecosystem-assembly]] — 54 enablers across four layers; inventory before specification; OAN connects, not builds

## Key facts for adopters

- **System speaks as the institution, not as itself.** Every response cites the Department of Agriculture and state universities. The AI's identity is subordinated to the institution's identity. 🟡
- **Data connection, not data cleaning, was the intervention.** Maharashtra had APIs that existed for years but had never been called. Departments had never queried their own data together. The moment AI connected them, officials asked "whose data is right?" for the first time. No data cleaning was required to start. 🟡
- **Scale came from right-level problem framing.** 440,000 total categorised queries/month (December 2025), with 205,000 of those crop/pest queries. When the problem is framed at the right granularity ("leaf curling in chilli — what to do?" vs "we want to use AI in agriculture"), adoption takes care of itself. 🟡
- **25+ organisations, 54 enablers across four layers.** Ecosystem composition: institutional/governance layer (funders, orchestrators, government bodies), technology/AI layer (research institutions, language models, knowledge contributors), structured data layer (APMC prices, weather, scheme data), knowledge/documents layer (crop PoPs, veterinary manuals, programme guidelines). 🟡
- **Proactive push reaches users who would not call.** Shift from pull (farmer calls) to push (system calls farmer) — 17 lakh daily proactive voice alerts; 15 stage-based advisories proactively across the crop calendar from sowing through harvest. This is where advisory systems move from useful to indispensable. 🟡
- **Farmer progression from simple to complex queries is by design.** Weather and pest queries → scheme applications, credit products, grievance tracking, and contributing field observations. Each step trains the farmer for the next. 🟡
- **System spans the full advisory stack.** Weather, pest advisory, mandi prices, 40+ government schemes (via MahaDBT), 307 APMCs, 4 state agricultural universities, 203 warehouses — all accessible via short code 155313. 🟡
- **System feedback rate sustained.** 97%+ positive feedback rate throughout; 98.5% in most recent measurement period. 🟡
- **9 months as pioneer.** This compressed to 3 months (Ethiopia) and 3 weeks (Amul) as transferable assets accumulated. 🟡

## Dimensions covered

| Dimension | Coverage in source | Notes |
|---|---|---|
| A: Problem orientation | Strong | Inbound/outbound distinction; 205k query evidence; problem framing at right granularity |
| B: Architecture | Strong | Data sovereignty model (only prompt goes to LLM); independent moderation layer; no data cleaning required |
| C: Institution | Strong | DoA authorised its advisory corpus; institutional knowledge claim; C3 well-evidenced |
| D: Ecosystem | Strong | 54 enablers; four-layer taxonomy; trust source (speaking as DoA); D4 not explicitly named |
| E: Workforce | Moderate | Farmer progression (E1/E3); institutional workforce training not documented for MahaVISTAAR specifically |
| F: Operating model | Moderate | F1 velocity (proactive push); governance model partially documented; sustainability costs not Maharashtra-specific |

## Gaps

- Who played the D4 (network operator) role within Maharashtra is not named in this source (Department of Agriculture plays the role, but the individual/unit not identified)
- Training model for extension workers in Maharashtra is not documented (Bihar Krishi has stronger E2 evidence)
- Exact governance structure (F2) and procurement path not documented
- Sustainability model (F3) post-pilot not documented
- Year of deployment start not recorded in any source; system confirmed active December 2025
