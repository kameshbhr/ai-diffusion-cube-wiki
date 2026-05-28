# The 70/30 Split — Evidence for the Tech/Non-Tech Resource Ratio

**Type:** Synthesis
**Deployments cited:** MahaVistaar, Amul Sarlaben, Bharat-VISTAAR, Bihar Krishi, Ethiopia ATI
**Last updated:** 2026-05-28

## The Pattern

Across the six dimensions framework, 7 sub-components are technology (Dimension B, plus the technology elements of Dimension A) and 14 are non-technology (Dimensions A, C, D, E, F). This 2:1 ratio in sub-components maps to a documented claim: technology accounts for approximately 30% of the effort and risk in taking an AI deployment from idea to scale. The remaining 70% concentrates in problem framing, institution, ecosystem, workforce, and operating model.

The implication for a next adopter is direct: if your deployment plan allocates 70% of its time and resource to technology and 30% to everything else, you have the ratio inverted, and you are likely to encounter problems in the 70% you are under-planning for.

## Evidence

### Framework

The six orthogonal shifts framework document explicitly states that technology accounts for approximately 30% of deployment effort and risk, with 70% in non-technology dimensions. The sub-component count (7 technology, 14 non-technology) reflects this claim structurally: the framework captures twice as many distinct non-technology decision types as technology decision types, because that is where the complexity and variance actually lives.

### MahaVistaar

MahaVistaar's documented challenges and timeline impacts reflect the 70/30 distribution. The technology challenges — model choice, serving architecture, data integration — are documented and were resolved. The non-technology challenges — inter-departmental data governance requiring a joint secretary-level resolution, ecosystem coordination across 54 named enablers, the institutional framing required to sustain a transformation mandate through administrative cycles — account for the majority of documented effort and timeline impact. The serving architecture migration (a technology challenge) was resolved in a defined engineering effort. The data-sharing blockage (an institutional challenge) required convening authority that took time to arrange.

[See full pathway: MahaVistaar](../pathways/mahavistaar.md)

### Amul Sarlaben

The 3-week deployment compressed the technology build time dramatically through DPG reuse. The remaining questions — what the cooperative workforce needed, how operations are governed post-deployment, what the steady-state cost model looks like — are the non-technology questions that are not yet documented for this deployment. The relative thinness of E-dimension (workforce) and F-dimension (operating model) coverage for Sarlaben compared to its B-dimension coverage may itself reflect the 70/30 pattern: technology documentation is easier to extract and transmit, while non-technology knowledge requires deliberate capture through conversation with the people who held the deployment together.

[See full pathway: Amul Sarlaben](../pathways/amul-sarlaben.md)

## What This Means for a Next Adopter

Before allocating deployment budget and team capacity, divide your planning across the six dimensions and check the ratio. If technology planning (Dimension B, and the technology elements of Dimension A) consumes more than 30% of total planning effort, the non-technology dimensions are under-resourced.

The specific non-technology dimensions that most frequently cause deployment failure are C (institutional framing) and D (ecosystem design). Getting institutional framing wrong — treating the deployment as a project rather than a transformation — changes the funding model, the accountability structure, and the survival probability through political change. Getting ecosystem design wrong — launching without a named network operator, or without mapping the minimum viable ecosystem before launch — creates coordination failures that compound over time.

## Open Questions

The 70/30 split is a framework claim, not yet a precisely quantified empirical finding from these five specific deployments. A future contribution that tracks actual person-hours or budget allocation across dimensions for any of these deployments would sharpen this evidence significantly.

Does the ratio shift over time? Is the 70/30 split more pronounced at scaling than at pilot — does technology become a smaller fraction of the challenge as the system matures? None of the current deployments documents this longitudinally.
