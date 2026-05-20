# Inclusion Architecture (Open Question — Potential A5)

**Dimension(s):** A: Problem orientation (potential A5); B: Architecture; D: Ecosystem (D2 Trust source)
**Type:** Framework / Open Question

## What this is

Inclusion architecture is the design commitment that a system must work for the person with the least access — and that this requirement shapes the entire technology stack. It is not a feature to add later. It is a foundational architectural choice.

The sharpest available statement of this principle, from the OAN-DiffusionPathway document: **"Voice is not a feature of the OAN pathway. It is the architectural response to the inclusion problem."** 🟡

The most concrete expression in documented deployments: the system must work on a basic feature phone through a voice call. This requirement drives choices in ASR (automatic speech recognition), TTS (text-to-speech), turn detection, telephony gateway hardware, and latency budgets. These are specific, consequential technical constraints that flow from a single design commitment. The result: literacy, device type, navigation complexity, language, and portal registration all become irrelevant. The farmer speaks their question in their language, on the phone they already own.

**Voice dissolves the specific barriers, one by one** 🟡:
- Literacy barrier: a farmer who cannot read does not need to read
- Device barrier: a farmer who does not have a smartphone can call a number
- Language barrier: a farmer whose primary language is Marathi, Gujarati, or Oromo does not need to translate
- Navigation barrier: no portal to log into, no app to download, no form to fill

**This concept sits at an intersection that the current six-dimension framework handles imperfectly.** Voice-first design is not a model choice (B1), a data sovereignty decision (B2), a vendor independence decision (B3), or a DPG vs. instance decision (B4). It is not purely a problem framing question (A1) either. It sits at the intersection of A1 (who the problem is framed for), B (what the architecture must support), and D2 (trust — voice carries trust in a way text often does not for low-literacy users).

The framework document proposes this as a potential **A5 — Inclusion design**: FROM "build for smartphone users and hope others catch up" TO "build for the person with the least access and let that design serve everyone."

## Why it matters

The people most likely to benefit from AI advisory systems — smallholder farmers, frontline health workers in rural areas, first-generation beneficiaries of government schemes — are often the people least able to access smartphone-and-data-connection-dependent systems. A deployment designed for the median user will systematically exclude the users with the greatest need.

Voice-first is not the only inclusion architecture, but it is the most documented in this wiki's current sources. The design principle generalises: identify the person with the least access relevant to your deployment, and build for them. The design that works for the least-access user almost always works for all users; the reverse is not true.

## What the pathways show

🟡 **MahaVISTAAR (Maharashtra):** Short code 155313. Delivers advice via voice call in Marathi — accessible without smartphone, data connection, or literacy. 17 lakh farmers reached daily via proactive voice alerts; 440,000 categorised queries/month. The voice interface is the primary trust channel: hearing advice in Marathi, from a number associated with the state agriculture department, carries trust differently from the same advice as English text on a website. The Nandan Nilekani quote: "using a basic feature phone, a Marathi-speaking farmer can now consult a chatbot for advice on soil, seeds and irrigation, and receive guidance in their own language." 🟡

🟡 **Amul/Sarlaben (Gujarat):** Short code 08035453545. For the women dairy producers in Amul's 18,500+ villages — predominantly rural, lower digital literacy — voice is not a channel option. It is the only channel that works. "They have never had a smartphone. They may not read with ease. The expert knowledge that could help them manage their animals has existed, but has not been reachable. They are now reaching it." Younger family members without 30 years of dairy experience access expert knowledge via voice: "informed, therefore powerful to make choices; freedom comes from knowing, and nobody can fool me." 🟡

🟡 **Bharat-VISTAAR (national India):** Short code 155261 in Hindi and English. Feature phone access designed in from the start of the national architecture. 🟡

🟡 **Ethiopia:** Voice-first in local languages for farmers without smartphones or broadband. Climate intelligence — a particularly time-sensitive advisory — delivered via voice. 🟡

⬜ **The trust dimension of voice**: Nandan Nilekani named both requirements simultaneously: "When the monsoon is delayed, people want to know who stands behind a recommendation. Citizens tend to trust institutions rather than algorithms. For AI to be adopted by a whole population, it must carry the credibility of trusted institutions, with traceable and verifiable authority." Voice-first access built on verified institutional data is how both conditions — reach and trust — are met simultaneously.

⬜ The test for orthogonality (whether this deserves to be a separate sub-component from A1-A4): can you vary your inclusion design independently of problem framing, data posture, existing assets, and proof? Evidence suggests yes: you could frame the right problem (A1), have the right data posture (A2), start with existing assets (A3), and have proof (A4) — and still build a system that only reaches smartphone-literate users in areas with data connectivity.

## Flag for wiki users

This concept represents an unresolved framework question. The current wiki treats it as a concept page pending further field evidence. If subsequent pathway documentation consistently shows inclusion architecture as a decision made independently of A1-A4, this page should be elevated and the six-dimension framework updated to reflect A5.

## Pathways that cover this

- [mahavistaar](../deployments/mahavistaar.md) — Voice-first as primary access channel; short code 155313; 440k queries/month; 17 lakh proactive alerts
- [amul-sarlaben](../deployments/amul-sarlaben.md) — Voice-first for dairy cooperative members; short code 08035453545; women producers as primary beneficiary
- [bharat-vistaar](../deployments/bharat-vistaar.md) — National voice access; short code 155261
- [ethiopia-ati](../deployments/ethiopia-ati.md) — Voice-first in local languages; climate advisory via voice

## Related concepts

- [problem-orientation](../dimensions/problem-orientation.md) — A1 problem framing (the closest existing home for this concept)
- [architecture](../dimensions/architecture.md) — B1-B4 (where voice infrastructure choices partially sit); see also [seven-layer-architecture](seven-layer-architecture.md) for the ASR/TTS/telephony layer detail
- [dpi-ai-frame](dpi-ai-frame.md) — Institutional authority + AI delivery layer is the frame within which voice-first inclusion operates
