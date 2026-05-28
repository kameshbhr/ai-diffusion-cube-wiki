# MahaVistaar — Pathway

**Deployment:** MahaVistaar (Maharashtra AI-powered agricultural advisory system)
**Contributor:** EkStep Foundation / Government of Maharashtra
**Sector:** Agriculture
**Geography:** India — Maharashtra state
**Actor type:** Government
**Journey stage:** Scaling
**Dimensions covered:** A, B, C, D, E, F
**Horizontal or vertical:** Vertical (agriculture sector)
**Deployment status:** Active
**Last updated:** 2026-05-28

## Summary

MahaVistaar is Maharashtra state's AI-powered agricultural advisory platform, providing personalised, multilingual, voice-first advice to farmers across 152 lakh hectares of Kharif cropland. As of December 2025 it had served 342,000+ unique users, answered 1.67 million questions, and delivered 17 lakh daily proactive alerts — at a cost of approximately ₹0.05 per question after switching to self-hosted infrastructure. It is the most thoroughly documented deployment in this wiki and serves as the primary reference for technology architecture, ecosystem assembly, and workforce absorption.

---

## A — Problem Orientation

*What you build on.*

The deployment targeted Maharashtra's farming population — smallholder farmers managing crops across a range of agro-climatic zones, who needed timely, personalised advisory on crop management, pest and disease control, weather events, and government scheme access. The constraint profile of the target user was specific and severe: users were predominantly rural, variable-literacy, often offline, and primary Marathi speakers. 🟡 The deployment team's documentation emphasises that existing advisory infrastructure — one extension officer per several thousand farmers, generic advisories broadcast through radio and TV — could not provide personalised, timely, local answers. The non-AI alternative would have required hiring thousands of additional extension officers, which was not feasible. 🟡

The deployment started with a significant existing data advantage: Maharashtra had pre-existing agricultural datasets, ICAR scientific knowledge, and IMD weather integration that could serve as the knowledge base without requiring data to be built from scratch. 🟡 The knowledge architecture also drew on 10+ years of Agristack data work at the national level, though the specific data assets accessed at state level are not fully itemised in available documentation.

Understanding of the problem did evolve after launch. 🟡 The team discovered that voice was not just a channel preference but a functional necessity — farmers interacting during fieldwork could not read or type. The 155313 voice short code became the highest-volume entry point. This understanding shaped the subsequent decision to invest heavily in voice AI infrastructure. Whether early assumptions about user literacy or connectivity were tested before deployment is not documented.

---

## B — Architecture

*What you build with.*

MahaVistaar is built on a seven-layer federated architecture. 🔵 From the user-facing layer inward: users interact through voice (155313 short code), WhatsApp, a dedicated app, and web. The interface layer handles channel routing. A moderation layer (GPT-OSS Safeguard 20B, fully decoupled from the main LLM) screens every query and response for harmful content, prompt injection, domain relevance, and adversarial patterns — with 500 documented adversarial attack patterns tested. The AI decision engine is a fine-tuned Qwen3.5-27B model (the MahaVistaar LLM) trained specifically on agricultural advisory tasks. This model sits on top of a knowledge and scientific models layer comprising ICAR domain knowledge, crop calendars, and pest databases. Live data sources — IMD weather feeds, market price APIs, state department data — are accessed at query time via API rather than copied centrally. The DPI foundation layer provides authentication and connectivity. 🔵

The critical architectural choice is federated data: raw institutional data stays where it lives. 🔵 Only the prompt is sent to the LLM. No farmer data or institutional database is centralised. This design resolves data sovereignty concerns across the 25+ partner organisations whose data feeds the system without requiring data-sharing agreements that would have taken years to negotiate.

Vendor independence was addressed through dual-provider inference infrastructure. 🔵 vLLM is self-hosted as primary (with automatic spillover between endpoints at a 100-call cap per endpoint). Azure OpenAI serves as fallback. The financial rationale for this architecture is documented precisely: the deployment was paying approximately ₹9 per question on commercial APIs in November 2025 (Azure GPT-4.1), with costs tracking toward ₹6 lakh per day as Voice AI scaled. 🔵 The switch to self-hosted inference on a 4×H100 GPU cluster (Qwen3.5-27B, TP=4, 84K context window) reduced marginal cost to approximately ₹0.05 per question — a 180× reduction. The 4-GPU cluster cost ₹25 lakh actual for six months; the planned 16-GPU expansion is projected at ₹2 crore per year versus ₹18 crore per year on Azure — a 9× annual saving at scale. 🔵 Prefix caching yields an additional 37% compute saving. 🔵

Accuracy on field evaluation sets is 94% for the fine-tuned model versus 91% for commercial APIs — a 3-point improvement alongside the cost reduction. 🔵 The source of this accuracy improvement is the fine-tuning on agricultural domain data rather than a general-purpose model.

The moderation layer catches harmful and out-of-domain responses before they reach farmers. 🔵 Whether there have been specific incidents where the AI gave a wrong or harmful answer to a real user, and what happened as a result, is not documented in available sources.

---

## C — Institution

*Who deploys AI.*

MahaVistaar is a state government deployment with EkStep Foundation as technical partner. 🟡 The Government of Maharashtra is the deploying institution, providing both authority and access to state data. How the deployment was initially approved and funded — whether it was framed as a one-time project or a long-term transformation initiative — is not documented in available sources.

Not documented.

Whether there was internal resistance within the state agriculture department or other Maharashtra government departments, and what changed minds, is not documented.

Whether procurement rules created a barrier to contracting with EkStep or technology providers, and how those barriers were navigated, is not documented.

What the accountability structure was when something went wrong — which individual or department was responsible — is not documented.

Whether the deployment is institutionally resilient to turnover of key individuals driving it is not documented. The deployment's scale (342,000+ users, 17 lakh daily proactive alerts) suggests it has achieved operational momentum, but the governance structure underlying that operation is not described in available sources.

---

## D — Ecosystem

*Who executes.*

MahaVistaar operates through an ecosystem of 25+ organisations assembled across four layers. 🟡 The Institutional and Governance layer includes the Government of Maharashtra (state authority and data custodian), ICAR (Indian Council of Agricultural Research, domain knowledge), IMD (India Meteorological Department, weather data), and national Agristack infrastructure. The Technology and AI layer includes EkStep Foundation (system integration and AI platform), cloud infrastructure providers, and telecom partners enabling the 155313 voice channel. The Structured Data layer includes market information systems, crop advisory databases, and state department datasets. The Knowledge and Documents layer includes extension materials, scheme documentation, and farmer-facing content in Marathi and other regional languages. 🟡

Who held the network operator role — who was ultimately responsible for keeping all 25+ organisations aligned day-to-day — is not documented. This is a significant gap: at this ecosystem scale, coordination failure is one of the highest-probability points of breakdown, and understanding how it was managed is directly actionable for a next adopter.

Whether any partner relationship did not work out as expected, and what happened as a result, is not documented.

How trust was maintained across partners — especially when something went wrong in the field — is not documented.

---

## E — Workforce

*Who absorbs AI.*

The primary workforce absorbing MahaVistaar is Maharashtra's network of Krishi Sahayaks (agricultural extension workers) and other frontline staff who mediate between farmers and the platform. 🟡 17 lakh daily proactive alerts are sent to farmers — the scale of this implies either direct farmer use or a significant field staff intermediation layer, but the documentation does not specify what proportion of usage is direct versus mediated.

The deployment's multi-channel design (voice, WhatsApp, app, web) reflects awareness that different workforce and user segments have different interaction preferences. The short code 155313 specifically targets users who cannot navigate an app interface. 🟡

What training was provided to field staff, when it was provided in the deployment timeline, and what depth was required is not documented. Whether there was resistance from extension staff who may have perceived the platform as a threat to their role is not documented. Whether field staff can still do their job if the system is unavailable — whether dependency has been created — is not documented.

---

## F — Operating Model

*What makes it last.*

MahaVistaar's cost structure is the most thoroughly documented of any deployment in this wiki. 🔵 Build costs are not documented. Operating costs at the infrastructure level are: approximately ₹9/question on Azure GPT-4.1 (November 2025 baseline) → approximately ₹0.05/question on self-hosted vLLM Qwen3.5-27B (post-migration). At 440,000 queries/month (December 2025 throughput), the monthly inference cost on self-hosted infrastructure is approximately ₹22,000 — compared to approximately ₹40 lakh/month at the prior commercial API rate. 🔵 The full operational cost including team, infrastructure maintenance, partner coordination, and content upkeep is not documented.

The deployment measures: unique users (342,000+), total questions answered (1.67M+), sessions (791,000+), monthly query volume (440,000 as of December 2025), and user satisfaction (97%+ positive feedback, 98.5% most recent measurement). 🟡 These are output metrics, not outcome metrics. Whether there is measurement of farmer income change, crop loss reduction, scheme uptake, or other downstream agricultural outcomes is not documented. This is a significant gap for sustainability: output metrics cannot demonstrate the value needed to sustain government funding through successive budget cycles.

Who owned operations after the pilot ended, and how that handover was structured, is not documented.

Whether there was a point at which the deployment nearly stalled — and what got it through — is not documented.

Whether there are compliance, audit, or regulatory requirements shaping operations — such as data protection obligations, CERT-In requirements, or state government IT procurement rules — is not documented.

---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| Seven-layer system architecture | Architecture pattern | Structuring any federated AI advisory deployment — use as planning template for layer-by-layer build | Documented in OAN-DiffusionPathway.pdf (raw/) |
| Federated data architecture | Architecture decision | Bypassing data-sharing negotiation delays while preserving data sovereignty | Documented in OAN-DiffusionPathway.pdf and MahaVistaar Production Serving Architecture note (raw/) |
| 500-pattern adversarial attack test suite | Moderation/safety | Testing AI moderation layer before production deployment | Referenced in MahaVistaar Production Serving Architecture note; not publicly released |
| vLLM + Azure OpenAI dual-provider inference pattern | Infrastructure | Cost and reliability architecture for high-volume inference | Documented in MahaVistaar Production Serving Architecture note (raw/) |
| 54-organisation ecosystem map | Ecosystem design | Planning partner assembly for a comparable multi-stakeholder agricultural AI deployment | Documented in OAN-DiffusionPathway.pdf (raw/) |

---

## Related Pathways

- [Bharat-VISTAAR](bharat-vistaar.md) — national-scale federation that MahaVistaar is intended to connect into
- [Bihar Krishi](bihar-krishi.md) — comparable state-level deployment, different institutional actor (civil society versus state government)
- [Amul Sarlaben](amul-sarlaben.md) — cooperative-sector deployment; parallel voice-first design, different trust architecture

## Related Entities

- [EkStep Foundation](../entities/ekstep-foundation.md) — technology partner and system integrator
- [OpenAgriNet](../entities/openagri-net.md) — network enabling interoperability across agricultural AI deployments

## Lineage

Not documented.
