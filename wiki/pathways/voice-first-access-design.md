---
type: pathway
deployment: mahavistaar
dimensions: [problem-orientation, architecture, ecosystem]
sector: agriculture
geography: Maharashtra, Gujarat, Bihar, Ethiopia, India national
contributor: ekstep-foundation
contributed: 2026-05-20
last-updated: 2026-05-20
times-referenced: 0
---

# Voice-First Access Design

**One-line summary:** Design voice as the primary access channel — not a feature added to a text-first system — and every structural barrier to inclusion (literacy, device type, language, navigation) dissolves simultaneously.

**Deployment source:** MahaVISTAAR (reference implementation) — [mahavistaar](../deployments/mahavistaar.md); confirmed across [amul-sarlaben](../deployments/amul-sarlaben.md), [bharat-vistaar](../deployments/bharat-vistaar.md), [ethiopia-ati](../deployments/ethiopia-ati.md)
**Contributor:** EkStep Foundation — [ai-diffusion-pathways](../people-orgs/ai-diffusion-pathways.md)
**Contributed:** 2026-05-20
**Last updated:** 2026-05-20
**Times referenced:** 0

## Context

The people most likely to benefit from an agricultural AI advisory system are often the people least able to use the channels designed to hold it. A smallholder farmer in rural Maharashtra or Oromia typically does not have reliable internet. Many do not have smartphones — they have basic feature phones. Many cannot read the language the portal is in, or cannot read at all. The government websites that hold agricultural guidance require navigation, registration, login, scrolling, decoding of government terminology, and the ability to triangulate across multiple sources. Even farmers who try encounter a cascade of barriers before reaching anything useful. They search. They land on the wrong page. They cannot read the PDF. The portal asks them to register. Registration requires documents. The advisory is in Hindi. They give up. 🟡

This is not occasional. It is structural. Digital proliferation has produced an abundance of information that flows to those who are already connected, literate, resourced, and fluent — and stops at the edge of that circle. "The farmer is not failing to include themselves. The system is failing to reach them." 🟡

The next adopter who recognises this pattern in their own context — an advisory system that technically exists but practically excludes the majority of its intended users — is in the situation this pathway addresses.

What made this challenge recognisable across all five documented deployments was a shared structural gap: knowledge existed in institutional databases; the people who needed it most could not reach it through the channels that held it. Voice was the response. "Voice is not a feature of the OAN pathway. It is the architectural response to the inclusion problem." 🟡

## Shift map

| Shift | Summary | Documented? |
|---|---|---|
| A1 Problem framing | Reframe from "build an AI system for farmers" to "build for the farmer who cannot read, does not have a smartphone, and does not speak the portal's language" | ✓ |
| A2 Data posture | Not documented for this pathway | Not documented |
| A3 Existing assets | Telephony infrastructure (basic phones, PSTN networks) as existing asset; does not require smartphone penetration | ✓ |
| A4 Proof mechanism | Voice adoption rate (440k queries/month in MahaVISTAAR; 3.6M producers reached in Sarlaben) as proof | ✓ |
| B1 Model choice | LLM choice constrained by voice pipeline latency requirements; model must begin streaming output before full response is ready for TTS to start speaking | ✓ |
| B2 Data sovereignty | Not the focus of this pathway | Not documented |
| B3 Vendor independence | Voice pipeline (ASR/TTS/telephony) is a distinct vendor set from the LLM layer; must be treated independently | ✓ |
| B4 DPG vs instance | Not the focus of this pathway | Not documented |
| C1 Framing | Naming the system signals who it is for: "Sarlaben" encodes that it is designed for the woman dairy producer, in her language, on her terms | ✓ |
| C2 Resistance | Not documented for voice-first specifically | Not documented |
| C3 Institutional knowledge | Building the language glossary (bilingual agricultural terminology) is institutional knowledge that does not transfer automatically to new deployments | ✓ |
| D1 Ecosystem design | Telephony gateway providers, ASR/TTS model suppliers, language model contributors (Bhashini, AI4Bharat) as distinct ecosystem members required for voice | ✓ |
| D2 Trust source | Voice carries trust that text on a portal does not: hearing advice in Marathi from a number associated with the state agriculture department, in the farmer's own language, carries institutional credibility | ✓ |
| D3 Coordination mechanism | Not documented for voice-first specifically | Not documented |
| D4 Network operator | Network operator must authorise the AI to speak in the institution's name via voice — a more exposed accountability commitment than text | ✓ |
| E1 Training timing | Not documented for this pathway | Not documented |
| E2 Training depth | Not documented for this pathway | Not documented |
| E3 Agency test | "Informed, therefore powerful to make choices; freedom comes from knowing, and nobody can fool me." (Amul dairy producer) — voice access as agency enabler | ✓ |
| F1 Velocity | Voice-first deployment does not require waiting for smartphone penetration to increase | ✓ |
| F2 Governance | Not documented for this pathway | Not documented |
| F3 Sustainability | Voice telephony costs (PSTN, IVR, cloud telephony) must be planned separately from API costs | ✓ |
| F4 Pilot to deployment | Language glossary and voice pipeline methodology are transferable; Ethiopia built on methodology established in Maharashtra | ✓ |

## Playbook

### What was done and why

In MahaVISTAAR, Maharashtra's short code 155313 was made accessible from any phone including basic feature phones — not as an add-on to an existing web or app interface, but as the primary access channel. The decision: voice-first is an architectural requirement, not a feature. 🟡

The voice pipeline was built as a distinct technical layer (separate from the AI advisory engine): ASR converts farmer speech to text; turn detection determines when the farmer has finished speaking; TTS converts advisory text back to natural-sounding speech in the local language. This pipeline is latency-sensitive in a way general inference is not — the model must begin streaming output before the full response is ready, so TTS can start speaking immediately. Real-time voice calls require dedicated inference endpoints separate from the main LLM servers. 🟡

Language infrastructure — a bilingual agricultural glossary bridging MarathiEnglish terminology — was built as a core component, not derived post-hoc. Without this glossary, the system cannot reliably interpret crop and pest terminology spoken by farmers in regional dialects. 🟡

Amul's Sarlaben was named deliberately: "Sarlaben" signals to the woman dairy producer in Gujarat's 18,500+ villages that this system is built for her, in her language (Gujarati), accessible at 08035453545 from any phone. The naming decision is not cosmetic — it is a trust-design decision. The same principle: voice-first as primary, not supplementary. 🟡

Bharat-VISTAAR built in feature phone access from the national architecture (155261, Hindi and English). Ethiopia built voice-first in local languages for farmers without smartphones or broadband. Each deployment independently arrived at the same architectural commitment, not as imitation but as response to the same structural inclusion problem. ⬜

### Key decisions

| Decision | Options considered | What was chosen | Why |
|---|---|---|---|
| Voice as primary or secondary channel | Voice as supplementary to app; voice as equal channel; voice as primary | Voice as primary — designed for feature phone as the primary device | App-first design excludes the majority of target users; voice dissolves all structural barriers simultaneously 🟡 |
| Language strategy | English first, add local languages later; local language from launch | Local language from launch, English secondary | Advisory in a language the farmer does not speak is not advisory — it is inaccessible information 🟡 |
| System naming | Technical/functional name; name of institution; name signalling the intended user | Name signalling the intended user (Sarlaben) | Trust carried through name recognition; signals accountability and audience 🟡 |
| Voice pipeline architecture | Integrated with LLM (single model handles voice + advisory); separated (dedicated ASR/TTS layer) | Separated: dedicated ASR/TTS pipeline, independent from advisory engine | Latency requirements for voice differ from advisory generation; separation enables optimisation of each independently 🟡 |
| Short code design | App download + registration required; USSD code; toll-free short code | Toll-free short code accessible from any phone | No barrier to entry — no app, no registration, no data connection required 🟡 |

### What worked

🟡 **Volume validates the design.** 440,000 categorised queries per month in MahaVISTAAR (December 2025); 205,000 of those crop/pest advisory queries. 97%+ positive feedback sustained at 98.5% most recently. These numbers would not be achievable from a smartphone-only channel in rural Maharashtra.

🟡 **Reach validates the design.** 3.6 million milk producers reached through Sarlaben in Gujarat. For women dairy producers with no smartphone and limited literacy, voice was the only channel that could reach them.

🟡 **Nandan Nilekani's statement of the outcome:** "Using a basic feature phone, a Marathi-speaking farmer can now consult a chatbot for advice on soil, seeds and irrigation, and receive guidance in their own language. When the monsoon is delayed, people want to know who stands behind a recommendation. Citizens tend to trust institutions rather than algorithms. For AI to be adopted by a whole population, it must carry the credibility of trusted institutions, with traceable and verifiable authority. Voice-first access built on verified institutional data is how both conditions — reach and trust — are met simultaneously." 🟡

🟡 **Language glossary as foundational asset.** The bilingual MarathiEnglish agricultural terminology glossary built for MahaVISTAAR transferred as a methodology (not the glossary itself) to Ethiopia — significantly reducing the language pipeline effort for a new deployment context.

🟡 **Compression evidence.** Ethiopia built comparable voice-first capability in 3 months compared to MahaVISTAAR's 9 months — partly because the language pipeline methodology was a transferable asset. "The methodology for building it transferred from MahaVISTAAR, significantly reducing the effort." 🟡

### What failed or caused friction

🟡 **Regional accent variation in ASR.** Maharashtra absorbed "dialect variation" as operational learning during the pioneer deployment. ASR models trained on standard Marathi perform less well on regional accents. This is an ongoing calibration problem, not a solved one — and it is the kind of friction that does not appear in deployment announcements.

🟡 **Rural connectivity gaps affect voice quality.** Telephony gateways must handle intermittent connectivity; packet loss affects call quality. The system must be designed to tolerate this rather than assuming stable rural connectivity.

⬜ **Latency vs. quality trade-off.** The requirement that TTS begins before the full response is generated creates a tension: starting speech early reduces latency but means the pacing of the spoken response must be pre-structured. The future direction — unified speech-to-speech models — addresses this but requires larger GPU hardware.

### What would be done differently

Not documented in this source. The source describes the system as operational and working — specific retrospective reflection from deployers is not available here.

## Toolkit

| Asset | Type | Description | Available |
|---|---|---|---|
| Voice pipeline methodology | Methodology | Approach for building ASR/TTS pipeline for a new language, including agricultural glossary construction | Yes — in OAN open source building blocks 🟡 |
| Bilingual agricultural glossary (MarathiEnglish) | Technical component | Bidirectional agricultural terminology bridge used in MahaVISTAAR | Available in MahaVISTAAR deployment 🟡 |
| Short code setup guides | Operational template | Institutional onboarding guides referenced in OAN tech stack | Referenced but not linked in source 🟡 |
| Bhashini / AI4Bharat integration | Technical component | Language models and translation infrastructure used for Indian language voice | Open-source; accessible 🟡 |

## Safety and trust notes

Voice carries the institution's identity in a direct and audible way. The farmer hears the voice of the system they are calling, in their language, from a number they associate with the state or cooperative. This creates both the highest trust signal available to the system — and the highest accountability obligation. If the voice system gives incorrect advice, the institutional credibility attached to that advice amplifies the harm. 🟡

The moderation layer (Layer 3 of the seven-layer architecture) is embedded within the ASR pipeline for voice, not as a separate call. This means safety filtering must be designed into the voice pipeline from the beginning — it cannot be layered on after the fact. See [seven-layer-architecture](../concepts/seven-layer-architecture.md).

## Policy and regulation notes

Cloud telephony providers (Exotel, Tata Tele) require regulatory compliance for IVR/PSTN interconnection. Short code assignment in India requires telecom regulatory approval. Government data residency rules (NIC hosting requirements) may apply to the data flowing through voice channels. Not documented in detail in source.

## Related pathways

- [institution-as-authority-trust](institution-as-authority-trust.md) — Voice-first and institution-as-authority are complementary: voice carries trust when it speaks as the institution, not as itself
- [federated-data-architecture](federated-data-architecture.md) — The data the voice system draws from must be accessible in the federated model; voice is the interface layer on top of the federated data infrastructure

## Related concepts

- [inclusion-architecture](../concepts/inclusion-architecture.md) — This pathway is the implementation guide for the inclusion architecture concept
- [seven-layer-architecture](../concepts/seven-layer-architecture.md) — Layer 2 (Interface) and Layer 3 (Moderation/ASR) and the Voice Pipeline detail
- [dpi-ai-frame](../concepts/dpi-ai-frame.md) — Voice-first is one of three design commitments that follow from the DPI+AI frame

## Lineage

No predecessor pathway — this is a first-generation pathway built from MahaVISTAAR as pioneer deployment.
