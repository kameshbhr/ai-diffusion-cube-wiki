# Seven-Layer System Architecture

**Dimension(s):** B: Architecture (B1–B4)
**Type:** Framework

## What this is

The OAN pathway deployments share a common seven-layer system architecture. This is documented in detail from MahaVISTAAR — which is described as "a replica across all OAN instances to a large degree." Understanding these layers is essential for evaluators assessing feasibility and for constructors planning deployment. The B1–B4 sub-components of the Architecture dimension capture the decision logic; this page captures the implementation structure those decisions are translated into. 🟡

The seven layers (from user-facing to infrastructure):

**Layer 1 — User Layer**
The actors the system serves: Farmers (crops, livestock, fisheries), Extension System (field officers and advisors), and Government & Policy (state planning, policy makers, ecosystem actors). This layer defines who the system is accountable to and what kinds of decisions it must support. Not a technical layer — it is the accountability frame. 🟡

**Layer 2 — Interface Layer (Natural Language Agricultural Interface)**
The channels through which users access the system: Push Notifications, Push Telephony, Chat/App, and Phone. In MahaVISTAAR: Marathi, Hindi, Bhili, and English. Text and voice both converge downstream into the same processing pipeline. Hardware considerations: feature phones and basic USSD/IVR phones must work alongside smartphones; telephony gateway hardware (SIP servers, PSTN interconnect) required. 🟡

**Layer 3 — Moderation Layer (Safety, Security & Policy Enforcement)**
The first gate every query must pass. An independent model — fully decoupled from the advisory engine — that performs domain validation, content safety filtering, prompt injection defence, and input sanitisation. Classifies queries as: Valid Agricultural, Non-Agricultural, Unsafe/Harmful, or Policy-Sensitive. In voice, this is embedded within the ASR pipeline. Maintains adversarial test sets of up to 500 attack patterns. The decoupling from the advisory engine is a design requirement: the safety layer must not be the same model as the one that generates answers. 🟡

**Layer 4 — AI Decision Engine (Reasoning, Orchestration & Response)**
The core intelligence layer, composed of three tightly coupled stages:
- *Reasoning Layer*: identifies intent and structures the decision task; maintains session context for follow-up queries
- *Tool Orchestration*: breaks intent into sub-tasks, selects tools, executes API calls in sequence, enforces prescribed flows (Pest → Glossary → Advisory; Weather → Location → Forecast; Market → Location → Mandi Prices). Guardrails: no tool = no answer; no source = no claim
- *Response Generation*: synthesises results into a grounded, source-attributed answer in the farmer's language. Text-to-Speech component for voice output

Hardware: GPU servers required for LLM inference. The team is planning transition from commercial APIs (per-token cost) to self-hosted open-source models, which fundamentally shifts infrastructure to owned/cloud-rented GPU compute. GPU utilisation rate directly determines cost per conversation. 🟡

**Layer 5 — Knowledge & Scientific Models**
Domain-specific advisory knowledge and analytical models accessed by the orchestration layer: Crop Advisory, Livestock Health, Fisheries Models, Weather & Market Analytics. Sourced from ICAR, universities, research institutes. Also houses the bilingual agricultural glossary (MarathiEnglish in MahaVISTAAR) that bridges the language gap without requiring a full corpus translation. Hardware: vector database infrastructure for semantic search and RAG (Retrieval-Augmented Generation); embedding model compute; structured storage for advisory corpus. 🟡

**Layer 6 — Live Data & Institutional Sources**
Real-time and reference data feeds that ground every factual claim. In MahaVISTAAR: IMD & Skymet (weather), AgriStack & Land Records (farmer identity and farm data), MahaDBT & Schemes (subsidies and scheme status), Soil Labs, KVKs & KCC (local extension). Accessed as tools, not pre-loaded into the model. Hardware: API gateway for concurrent outbound calls to multiple external services; caching layer (Redis or equivalent) for frequently accessed data; fallback routing for weather station geographic gaps. 🟡

**Layer 7 — Digital Public Infrastructure (DPI) Foundation**
The interoperability and data exchange backbone: OpenAgriNet, VISTAAR DPI, Government Ecosystem integrations, Data Exchange using open protocols (Beckn). This is what makes the system a piece of public infrastructure rather than a standalone application — it is designed to be plugged into and built upon. Hardware: secure government data exchange infrastructure (dedicated leased lines or VPN tunnels); NIC hosting compliance if government data residency rules apply; load balancers for burst traffic. 🟡

## Why it matters

The seven-layer model resolves a known gap in the B1–B4 dimension framework, which was noted in the wiki's first ingest as "richer than B1–B4 captures." Specifically:

- **Moderation layer (Layer 3) is not captured in B1–B4 at all** — yet it is one of the most consequential safety decisions in a deployment. An independent moderation model, decoupled from the advisory engine, is an architectural choice that should be in every adopter's design checklist.
- **Voice pipeline infrastructure** — ASR, TTS, turn detection — is a distinct implementation concern from model choice (B1) or vendor independence (B3), and requires separate hardware planning.
- **The "no tool = no answer" guardrail** (Layer 4 Tool Orchestration) is a specific design decision that prevents the AI from hallucinating answers when institutional data sources are unavailable. It is not captured elsewhere.

## What the pathways show

🟡 **GPU compute as the primary cost driver:** The transition from commercial APIs to self-hosted open-source models makes GPU capacity planning the most consequential infrastructure decision. Fine-tuned smaller models can outperform larger commercial APIs (94% vs 91% on Amul's evaluation sets), but they require on-premise or cloud GPU for both training runs and serving.

🟡 **Voice imposes the strictest latency requirements:** The model must begin streaming output before the full response is ready, so TTS can start speaking immediately. This is not a general inference latency requirement — it is specific to voice channels and requires dedicated endpoints separate from the main LLM servers.

🟡 **Adversarial robustness is built in, not added later:** Maintaining 500+ adversarial test patterns in the moderation layer is a live operational requirement, not a one-time evaluation. This means the safety infrastructure must be maintained and updated continuously.

## Pathways that cover this

- [[deployments/mahavistaar]] — Reference implementation; all seven layers documented from this deployment

## Related concepts

- [[concepts/dpi-ai-frame]] — Layer 7 is the implementation of the DPI frame; Layers 4-6 are the AI delivery layer
- [[concepts/inclusion-architecture]] — Layer 2 (Interface) and Layer 3 (Moderation) are where inclusion architecture is implemented technically
- [[dimensions/architecture]] — B1–B4 decision framework; this page provides the implementation structure
