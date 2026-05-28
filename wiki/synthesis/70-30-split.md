# The 70/30 Split — Technology and Non-Technology in AI Deployment

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bihar Krishi, Ethiopia ATI, Bharat-VISTAAR
**Last updated:** 2026-05-28

## The Pattern

Across every documented deployment in this wiki, approximately 30% of what determined whether the deployment reached scale was technology, and approximately 70% was non-technology: institutional framing, ecosystem assembly, workforce absorption, and operating model design. This ratio is consistent whether the deployment is government-led (MahaVistaar, Bharat-VISTAAR, Bihar Krishi), cooperative-led (Amul Sarlaben), or civil society-led (Bihar Krishi, Ethiopia ATI). The technology was necessary but not sufficient. The non-technology factors were where deployments failed or succeeded.

This is not an argument that technology does not matter — the MahaVistaar cost reduction from ₹9/question to ₹0.05/question is a directly enabling technology decision. It is an argument about where to invest attention and where the leverage is. A deployer who invests 70% of their problem-solving energy in technology and 30% in everything else is systematically solving for the wrong thing.

## Evidence

### MahaVistaar

MahaVistaar's technology achievements are substantial and well-documented: federated architecture, 180× cost reduction, 94% accuracy on domain evaluation sets, dual-provider inference, moderation layer with 500 adversarial patterns. 🔵 These are not trivial. But the technology worked at the point where it was deployed in November 2024.

What the evidence shows about the non-technology work: assembling 54 organisations across four layers 🟡, negotiating data access across 25+ partner organisations 🟡, establishing extension worker adoption pathways 🟡, building the government approval and funding relationship 🟡, and maintaining multi-channel operations (voice, WhatsApp, app, web) at 440,000 queries/month. 🟡 The documentation of the technology architecture runs to a detailed internal note. The documentation of the ecosystem assembly, workforce integration, and institutional governance that made the technology useful is thinner — not because less was done, but because it was harder to document.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Bihar Krishi

Bihar Krishi's most distinctive feature is not its technology — the specific technical stack is not documented — but its workforce approach: 15,000+ extension workers trained before launch across all 38 districts. 🟡 This is a non-technology investment of significant scale (logistics, training materials, trainer deployment, monitoring across 38 districts). The outcome — 850,000+ registered farmers, 20-25% monthly engagement, 38,000+ scheme applications — reflects the impact of that workforce investment, not a technology advantage.

The awards (ET DigiTech Gold, SKOCH Gold 2025) 🟡 reflect recognition of the deployment as a whole, not specifically its technology. The deployment's evidence of impact is achieved through a 70% non-technology investment that the technology layer enabled.

[See full pathway: Bihar Krishi](../pathways/bihar-krishi.md)

### Amul Sarlaben

Amul Sarlaben's 3.6 million user scale is primarily a function of Amul's existing non-technology infrastructure: 18,500 village societies, the cooperative trust relationship with milk producers, decades of farmer contact, and the financial alignment between cattle health and cooperative income. 🟡 The AI system was deployed into this infrastructure — it did not create the infrastructure. A comparable AI system deployed without Amul's cooperative network would face a fundamentally different adoption challenge.

This is the clearest evidence in the wiki for the 70/30 observation: the technology (AI veterinary advisory) was necessary, but the 70% (cooperative infrastructure, farmer trust, institutional incentives) was what made it reach 3.6 million users. 🟡

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

### Ethiopia ATI

Ethiopia ATI's 3-month launch timeline is presented in available documentation primarily as a technology story (architecture reuse from MahaVistaar). 🟡 But the non-technology preconditions were also in place: ATI's specific institutional mandate for agricultural transformation, government commitment at a level that triggered Fayda DPI integration, and EkStep Foundation's prior relationship with the team. 🟡 Without these non-technology conditions, the technology transfer alone would not have produced a working deployment in 3 months.

[See full pathway: Ethiopia ATI](../pathways/ethiopia-ati.md)

### Bharat-VISTAAR

Bharat-VISTAAR is the most extreme example of the 70/30 split: it is primarily a coordination and governance challenge at this stage, with the technology architecture largely inherited from MahaVistaar. The challenge of aligning 28+ state governments, multiple central ministries, ICAR, IMD, and domain-specific operators around a shared national platform is not a technology problem. Rs 150 crore is allocated. 🟡 The question is whether the institutional and ecosystem conditions (the 70%) will be managed successfully enough for the technology (the 30%) to function at national scale.

[See full pathway: Bharat-VISTAAR](../pathways/bharat-vistaar.md)

## What This Means for a Next Adopter

If your deployment plan spends more than 30% of its pages on technology architecture and less than 70% on institutional framing, ecosystem design, workforce integration, and operating model sustainability, rebalance. This is not an argument for technology minimalism — it is an argument for proportionate attention.

Specifically: do not hire a technology team before you have answered these non-technology questions. Who in your deploying institution has the authority to approve this and sustain funding through three budget cycles? Which partner organisations do you need that you do not currently have relationships with? What is the role of your field workforce, and how will you bring them in before the system goes live? What outcome will you measure to demonstrate value, and how will you collect that data?

If you cannot answer these questions, more time spent on technology architecture is not the bottleneck.

The 70/30 split also reframes the cost conversation. When a government evaluates the total cost of an AI deployment, it tends to evaluate the technology cost (infrastructure, licensing, development) and undercount the non-technology cost (training, ecosystem coordination, governance, change management). A deployer who accurately budgets the 70% will face fewer mid-deployment surprises than one who budgets only for the 30%.

## Open Questions

Whether the 70/30 ratio varies by sector — whether health deployments, with higher safety stakes and more regulatory requirements, might have a different ratio — is not evidenced from this wiki's current base.

Whether the ratio shifts across the deployment lifecycle — whether the technology proportion increases in the sustaining phase as ecosystem and institutional questions are resolved — is an open question.

Whether there is a threshold effect — a minimum technology investment below which no amount of non-technology investment can compensate — is not directly evidenced. The MahaVistaar cost reduction suggests that getting technology cost wrong has a direct impact on sustainability, which implies the technology floor is not zero.
