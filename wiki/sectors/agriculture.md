# Agriculture — Pathway Index

Agricultural AI deployments in this wiki focus on the advisory challenge: connecting smallholder farmers to personalised, timely information about crop management, pest control, weather, market prices, and scheme access. The common access constraint across deployments is language and connectivity — farmers are predominantly voice-reliant, without reliable data connectivity, and communicate in regional languages (Marathi, Gujarati, Hindi, Amharic). The common actor pattern is a government agricultural department or cooperative deploying voice-telephony AI over existing institutional channels with a pre-established trust relationship with farmers. What makes agriculture distinctive as a sector is the combination of real-time data dependency (weather, pest alerts, mandi prices that change daily) with significant knowledge depth requirements (crop variety, soil type, pest identification, scheme eligibility), and the presence of a mature digital public goods layer (OAN) that dramatically compresses deployment timelines for new entrants.

## Pathways in this sector

### [MahaVistaar](../pathways/mahavistaar.md)
**Geography:** Maharashtra, India | **Actor type:** Government | **Status:** Active
The anchor OAN deployment; the most detailed documentation of architecture, cost, and ecosystem design in this wiki. Essential reading for any government agricultural advisory deployment — especially the LLM cost migration, the 54-enabler ecosystem map, and the inter-departmental data governance experience.

### [Amul Sarlaben](../pathways/amul-sarlaben.md)
**Geography:** Gujarat, India | **Actor type:** Cooperative | **Status:** Active
Demonstrates DPG reuse compressing deployment to 3 weeks, and shows how the cooperative deployer model differs from government in procurement speed, data ownership, and trust architecture. Read alongside MahaVistaar to understand what changes when the deployer is a cooperative rather than a government department.

### [Bharat-VISTAAR](../pathways/bharat-vistaar.md)
**Geography:** India (national) | **Actor type:** Government | **Status:** Active
National-level deployment by ICAR; demonstrates how a research institution becomes an AI advisory deployer and how national research knowledge repositories integrate into a conversational system. Useful for national-scale or research-institution planning.

### [Bihar Krishi](../pathways/bihar-krishi.md)
**Geography:** Bihar, India | **Actor type:** Government | **Status:** Active
Independent deployment not using the OAN DPG layer; comparison case for understanding what DPG reuse saves in time and cost. Documentation is thin — a priority for future gap-filling contributions.

### [Ethiopia ATI](../pathways/ethiopia-ati.md)
**Geography:** Ethiopia | **Actor type:** Government | **Status:** Active
First international OAN deployment; demonstrates cross-border DPG portability across language family and national DPI foundation. Includes Fayda digital ID integration. Essential reading for African or non-Indian agricultural advisory deployment planning.
