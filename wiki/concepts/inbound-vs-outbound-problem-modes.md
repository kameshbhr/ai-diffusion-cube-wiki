# Inbound vs. Outbound Problem Modes

**Dimension(s):** A: Problem orientation (A1 Problem framing)
**Type:** Decision / Pattern

## What this is

Problems that an AI advisory system addresses come in two distinct modes, each requiring a different design:

**Inbound:** The end user comes to the system with a question. The system waits. The farmer calls a number, asks about a sick animal or tomorrow's weather, and gets an answer. Design task: respond accurately and helpfully to questions the user has already articulated.

**Outbound:** The system anticipates a need the user has not yet articulated — and reaches out. Pink bollworm detected in your region. Heavy rainfall expected tomorrow. Crop calendar suggests irrigation is due. Design task: frame problems the user hasn't raised yet, using location signals, crop calendar data, and population-level pattern recognition.

The shift from inbound to outbound — from "platform that waits for questions" to "platform that anticipates needs" — is where advisory systems move from useful to indispensable.

## Why it matters

Most AI advisory deployments start with inbound and stay there. This is a design choice, not a technical constraint — and it is a consequential one. Inbound systems serve users who know they have a question and know where to ask it. Outbound systems serve users who may not know what they don't know, or who would not have called at the right moment.

In agriculture, the most valuable interventions are often time-sensitive: pest pressure warnings, weather alerts, soil moisture signals. If the system only answers questions, it will miss the moments when a farmer most needs guidance — because the farmer won't know to call until after the damage is done.

Outbound also requires a different data architecture: the system must have access to location signals, crop calendar data, and regional pattern data, and must have a model of which alerts are relevant to which farmers.

## What the pathways show

🟡 **MahaVISTAAR inbound at scale:** In December 2025, MahaVistaar was receiving over 440,000 categorised queries a month. The largest single category: crop and pest advisory at 205,000 queries. Farmers asked "Leaf curling in chilli — what to do?" and "Can guava be grown on my land?" They asked for the weather in Parbhani tomorrow, for onion prices near Nashik, for the status of their drip-irrigation subsidy application, for the name of the agriculture officer assigned to their village. "These are not abstract needs. They are the actual questions farmers have had, unanswered, for decades."

🟡 **MahaVISTAAR outbound at scale:** A cotton farmer in Vidarbha receives a push notification when pink bollworm is detected in their region: "An infestation has been detected. Please inspect your crop immediately and take control measures." Before the next rains: "Heavy rainfall is expected in your area in the next 24 hours. Please take necessary precautions." Across the crop calendar — from sowing through harvest — the system delivers roughly 15 stage-based advisories proactively, without the farmer needing to ask. 17 lakh farmers receive proactive personalised voice alerts daily.

🟡 The outbound design question for adopters: "How quickly can you shift from pull (farmer calls you) to push (you call the farmer)?" This is framed as a velocity question — shifting quickly to outbound accelerates adoption.

🟡 **What farmers are beginning to do beyond both modes:** Farmers are beginning to contribute as well as receive — describing what they are observing in their fields and adding to the stock of information the system draws on. This is a third mode (participatory/crowdsourced) distinct from both inbound and outbound, documented as "early" but underway.

⬜ The two modes require different problem framing and data infrastructure. For inbound: can you name the specific question the specific person is asking today? ("leaf curling in chilli — what to do?"). For outbound: the system must have access to location signals, crop calendar data, and regional pattern data — and must model which alerts are relevant to which farmers. Without this data architecture, outbound is not feasible.

## Pathways that cover this

- [mahavistaar](../deployments/mahavistaar.md) — Both modes documented; outbound (17 lakh daily alerts) documented

## Related concepts

- [problem-orientation](../dimensions/problem-orientation.md) — Full treatment of A1 problem framing
- [deploy-first-data-posture](deploy-first-data-posture.md) — Outbound requires richer data access (location, crop calendar, regional patterns) than inbound
