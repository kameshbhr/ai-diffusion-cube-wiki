# Trust Architecture

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bihar Krishi, Bharat-VISTAAR, Ethiopia ATI, Blue Dots AI
**Last updated:** 2026-06-02

## The Pattern

In every documented deployment in this wiki, the AI does not speak as itself — it speaks as an institution the end user already trusts. This is not a branding decision; it is an architectural one. The trust that an AI advisory system requires to be used — and acted upon — is borrowed from an existing institutional relationship, not earned fresh by the AI. Where that institutional relationship is strong (Amul's 50-year cooperative history, the Maharashtra state agriculture department's extension network), uptake is rapid. Where it is weak or absent, uptake stalls regardless of technical quality.

The trust architecture has two levels. The first is institutional attribution: which institution does the AI speak on behalf of, and does that institution have credibility with the end user? The second is voice design: does the AI present itself in a way that signals it is built for this user, in their terms? Both levels matter. Institutional attribution without voice design produces a system users trust in the abstract but do not reach for. Voice design without institutional attribution produces a system that feels personal but carries no authority.

## Evidence

### MahaVistaar — departmental attribution

MahaVistaar speaks as the Department of Agriculture Maharashtra. ICAR provides the advisory authority — national research institution backing for the specific recommendations the system makes. The combination (state government accountability + national research authority) addresses two different trust questions farmers ask: "Who is responsible if this advice is wrong?" and "Does this advice come from someone who knows farming?" The independent moderation layer architecture — a separate AI model reviewing outputs before they reach farmers — is not disclosed as a separate layer; it functions as a quality backstop that the institutional attribution depends on. If outputs were consistently wrong, institutional attribution would damage rather than amplify trust.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Amul Sarlaben — cooperative attribution and named voice persona

Amul Sarlaben speaks as Amul. The cooperative relationship — 50 years of daily milk procurement, twice-daily collection cycles, records on 30 million cattle — means the institutional relationship is not just recognised but daily. Every farmer who calls Sarlaben has had an Amul collector arrive at her farm that morning. The trust is not abstract: it is embedded in the most regular transaction in the farmer's economic life.

The name "Sarlaben" adds a second trust layer. It is a Gujarati woman's name — it signals that this system was built for a woman producer, in her language, on her terms. The system speaks Gujarati on any phone, including a basic landline. The name is reachable at a specific number (08035453545). These design choices are trust architecture: they signal before the first word is spoken that this is a system for the user calling, not a system the user is calling.

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

### Bihar Krishi — state government attribution with national award validation

Bihar Krishi speaks as the Bihar state government agriculture department, backed by the 4th Agriculture Roadmap. The national award recognition — ET DigiTech Gold and SKOCH Gold 2025 — provides an independent quality signal that supplements the institutional attribution. For farmers who are uncertain whether a government platform will actually work, third-party quality recognition provides a different kind of trust signal: not "trust this because the government says so" but "trust this because independent evaluators have verified it works."

[See full pathway: Bihar Krishi](../pathways/bihar-krishi.md)

### Bharat-VISTAAR — ministerial attribution with PM endorsement

Bharat-VISTAAR speaks as the Ministry of Agriculture and Farmers Welfare, Government of India. The national short code 155261 is associated with the national ministry. Prime Minister Modi's endorsement at the India AI Impact Summit 2026 added political visibility that supplements the ministerial attribution — not as a trust mechanism with individual farmers, but as a trust mechanism with state governments and institutional partners considering connection to the national layer. The trust architecture here operates at the institutional level (state governments trusting the national layer) as well as the farmer level.

[See full pathway: Bharat-VISTAAR](../pathways/bharat-vistaar.md)

### Ethiopia ATI — national transformation mandate as trust source

Ethiopia's deployment trust architecture is distinctive because ATI is a national transformation institute rather than a single ministry. The AI speaks as ATI, backed by the Ministry of Agriculture and the Digital Agriculture Roadmap 2025–2032. The advantage of ATI's institutional position over a single ministry is that ATI's mandate spans government functions — its institutional authority is broader and harder to challenge at the sectoral level. The Fayda integration (Ethiopia's national digital ID) adds a personalisation layer: when a farmer is registered with Fayda, the system can speak to them specifically, which strengthens trust by demonstrating that the system knows who is calling.

[See full pathway: Ethiopia ATI](../pathways/ethiopia-ati.md)

### Blue Dots AI — district administration as governance node

Blue Dots AI's trust architecture is different from the agricultural deployments because the beneficiaries — informal workers seeking livelihoods opportunities — have lower baseline trust in government institutions than farmers served by established extension systems. The deployment's response is to place district administration as the governance node (institutional legitimacy) while using NGOs as the trust fabric (relational credibility with workers). District administration provides oversight and accountability; NGOs provide the relationship that makes a worker willing to share their skills profile. Neither alone is sufficient. The combination is the trust architecture.

[See full pathway: Blue Dots AI](../pathways/blue-dots.md)

## What This Means for a Next Adopter

Before deciding what your AI will say, decide whose voice it speaks in. The institutional attribution question is a precondition for the voice design question, and both are preconditions for the architecture question. An AI that gives correct answers in a voice the user does not trust will not be used. An AI that gives correct answers in a trusted institutional voice will be used — and acted upon.

The trust source has to be genuine. Amul's cooperative trust took 50 years to build; it cannot be manufactured for a new deployment. A next adopter in agriculture needs to identify which institution already has credibility with the target farmer population — and that institution needs to be willing to say "this runs in my name" and bear accountability for outputs. Deployers who cannot identify that institution should solve the institutional question before the technology question.

Voice design is trust design. The choice of language, channel, persona name, and access number all signal to the user whether this system was built for them. An AI that speaks Gujarati on any phone, reachable by calling a number that feels like calling a person, carries trust signals that an app requiring a smartphone and a data plan cannot carry. The trust architecture is embedded in the access architecture.

## Open Questions

All documented deployments in this wiki use government or cooperative institutional attribution as the trust source. Whether a market actor (a private company, a platform) can serve as a trust source for AI advisory at scale in a public-interest context is not yet documented. The Blue Dots AI employment platform operates closer to the market end of the spectrum, but it uses district administration and NGOs as the governance layer, not a market actor directly.

The trust architecture evidence is stronger for agricultural deployments than for livelihoods deployments. A livelihoods deployment at comparable scale to MahaVistaar would significantly expand the trust architecture evidence — particularly for the question of whether informal workers in urban and peri-urban contexts respond to the same institutional attribution mechanisms that rural farmers do.
