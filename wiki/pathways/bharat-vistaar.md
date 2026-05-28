# Bharat-VISTAAR — Pathway

**Deployment:** Bharat-VISTAAR (National AI agricultural advisory federation)
**Contributor:** Government of India / EkStep Foundation
**Sector:** Agriculture
**Geography:** India — national
**Actor type:** Government
**Journey stage:** Pilot
**Dimensions covered:** A, B, C, D, F
**Horizontal or vertical:** Horizontal (national DPI layer for agriculture sector)
**Deployment status:** Active
**Last updated:** 2026-05-28

## Summary

Bharat-VISTAAR is the national-scale federated AI agricultural advisory platform targeting India's 120 million farmers. It operates as a hub-and-spoke federation: a central advisory layer connects to state-level deployments (including MahaVistaar) and domain-specific deployments (including Amul Sarlaben), with the central layer integrating national data sources — 10 major central schemes, ICAR, and IMD. Phase 1 is live as of early 2026 with short code 155261 and Rs 150 crore government allocation. This is the most complex institutional and ecosystem challenge in this wiki — a national-scale coordination problem as much as a technology problem.

---

## A — Problem Orientation

*What you build on.*

The problem Bharat-VISTAAR addresses is advisory fragmentation at national scale: 120 million Indian farmers need access to accurate, personalised information about crops, weather, pests, and government schemes, but the existing system is siloed — state advisories, central scheme information, and scientific knowledge exist in separate institutional domains with no integration layer for the farmer. 🟡 The vision is that a farmer should be able to call a single number (155261) and receive advice that draws on all of these knowledge sources, localized to their crop, their agro-climatic zone, and their language.

The non-AI alternative would require physical coordination across dozens of central ministries, state departments, ICAR, and IMD — a bureaucratic integration that has been attempted without AI for decades without success. 🟡 AI provides the integration layer: it can synthesize knowledge from disparate sources into a single conversational response without requiring institutional consolidation.

The specific access constraints of the target user population (120 million farmers — varying literacy, connectivity, language) are not fully documented in available sources beyond what is shared with MahaVistaar's evidence base. The short code 155261 signals that voice-first access is a design constraint, as with all deployments in this wiki.

Whether existing data sources (ICAR, IMD, state Agristack data) were ready for integration at deployment or required significant preparation is not documented. Whether the deployment team's understanding of the problem changed after Phase 1 launch is not documented.

---

## B — Architecture

*What you build with.*

Bharat-VISTAAR uses a hub-and-spoke federation architecture. 🟡 The national hub integrates 10 major central government schemes, ICAR scientific knowledge, and IMD weather data. State-level deployments (such as MahaVistaar) and sector-specific deployments (such as Amul Sarlaben) are spokes. The federation design means each spoke retains its own institutional data sovereignty while the hub provides a coordination and routing layer.

The specific AI models, hosting infrastructure, and cost structure at the national level are not documented. Whether Bharat-VISTAAR reuses the MahaVistaar serving architecture (vLLM + Azure OpenAI dual-provider, federated data access, moderation layer) or deploys a different technical stack is not documented.

The short code 155261 is the primary entry point. Whether there are app, web, or WhatsApp channels at the national level is not documented.

Whether there is a moderation layer at the national hub, how it is configured, and whether it differs from state-level moderation is not documented.

---

## C — Institution

*Who deploys AI.*

Bharat-VISTAAR involves coordination across central government (the deploying institution), state governments (who operate the spokes), ICAR, IMD, and EkStep Foundation. 🟡 Rs 150 crore government allocation is documented — this is the funding instrument that drives Phase 1. Whether this is framed institutionally as a one-time project or a sustained transformation investment is not documented, though the scale and the hub-and-spoke design suggest a long-term infrastructure intent.

The central accountability structure — which ministry or department owns Bharat-VISTAAR, who is the accountable official when something goes wrong — is not documented. This is a consequential gap: at national scale, diffuse accountability is a reliable failure mode.

Whether there was resistance within any central ministry or state government to the deployment, what form it took, and what resolved it is not documented.

How procurement was handled at the central level — whether standard government IT procurement processes applied or a different mechanism was used — is not documented.

What happens to the national hub if the key individual driving the deployment moves roles is not documented.

---

## D — Ecosystem

*Who executes.*

The Bharat-VISTAAR ecosystem spans central government departments, 28+ state governments (each of whom must connect their state deployments to the national hub), ICAR, IMD, EkStep Foundation, telecom operators for the short code, and domain-specific deployment operators (such as Amul). 🟡 This is the largest ecosystem coordination challenge in this wiki.

Who holds the network operator role — who is responsible day-to-day for keeping the spokes connected, the data integrations live, and the 25+ institutional relationships active — is not documented.

How state governments are incentivised or required to connect their state deployments to the national hub — what the governance mechanism is for hub-and-spoke alignment — is not documented.

Whether any spoke has declined to participate or a partnership has not worked out as expected is not documented.

---

## E — Workforce

*Who absorbs AI.*

Not documented. The deployment documentation for Bharat-VISTAAR does not describe the workforce integration layer — how state extension staff, ICAR scientists, and frontline workers are being prepared for or incorporated into the national platform.

---

## F — Operating Model

*What makes it last.*

The Rs 150 crore government allocation provides the funding instrument for Phase 1. 🟡 Whether this covers only build costs, only operational costs, or both, and over what time period, is not documented.

What Bharat-VISTAAR measures to know Phase 1 is working — the metrics framework for the national deployment — is not documented.

Who owns operations after Phase 1, and what the transition structure is from build phase to steady-state operations, is not documented.

Whether there is a compliance or regulatory framework governing a national-scale AI system operating across state jurisdictions, and what audit obligations it creates, is not documented.

---

## Reusable Toolkit

| Asset | Type | What it is useful for | How to access |
|---|---|---|---|
| Hub-and-spoke federation architecture | Architecture pattern | Structuring a national-level AI platform that preserves state autonomy while enabling national knowledge integration | Documented in OAN-DiffusionPathway.pdf (raw/) |

---

## Related Pathways

- [MahaVistaar](mahavistaar.md) — state-level spoke; most thoroughly documented component of the Bharat-VISTAAR federation
- [Amul Sarlaben](amul-sarlaben.md) — sector-specific spoke (cooperative dairy)
- [Bihar Krishi](bihar-krishi.md) — comparable state-level deployment not yet documented as a Bharat-VISTAAR spoke

## Related Entities

- [EkStep Foundation](../entities/ekstep-foundation.md) — technology partner
- [OpenAgriNet](../entities/openagri-net.md) — network coordination layer

## Lineage

Built on [MahaVistaar](mahavistaar.md) — architecture, moderation patterns, and ecosystem design inherited from Maharashtra state deployment.
