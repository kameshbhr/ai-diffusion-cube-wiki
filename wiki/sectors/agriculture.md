# Agriculture — Pathway Index

AI deployments in agriculture face a structural problem that recurs across every documented context: the extension system cannot scale with the farmer population at human staffing ratios. India's historical baseline was one agriculture field officer for every 2,000 farmers in Bihar; Ethiopia's is comparable. The result is that most smallholder farmers receive no timely, personalised advisory on planting decisions, crop health, scheme access, or market prices — not because the information does not exist, but because the delivery mechanism (human extension officers) cannot reach everyone who needs it. AI advisory at scale is the structural response to this constraint, and the deployments in this sector have collectively proven that voice-first AI in local languages, connected to institutional data sources, can reach farmers at extension-system-impossible ratios.

The distinctive challenges in agriculture AI deployments are: language and access diversity (farmers without smartphones or broadband, speaking dozens of languages and dialects); data federation across multiple institutional owners (agriculture departments, research institutes, meteorological services, market systems); and the trust requirement that farm advisory be attributed to a credible institution, not an anonymous system. The deployments documented here have each addressed these challenges, and their architectures, governance frameworks, and failure mode libraries are available as reusable starting points.

## Pathways in this sector

### [MahaVistaar](../pathways/mahavistaar.md)

**Geography:** India — Maharashtra | **Actor type:** Government | **Status:** Active

The pioneer OAN deployment and the source of the DPG architecture, governance frameworks, and failure mode library that all subsequent deployments reused. The definitive reference for deployers building from scratch in a new state context.

### [Bharat-VISTAAR](/broken/pages/VGFgrEvo55jInllGOyEC)

**Geography:** India — national | **Actor type:** Government | **Status:** Active

India's national digital public infrastructure for agriculture — the hub-and-spoke federation layer that connects state and cooperative platforms to national scheme data, ICAR advisory, and AgriStack. The reference for deployers thinking about national architecture.

### [Amul Sarlaben](/broken/pages/CvkYDreqsGaIAPd4DhZe)

**Geography:** India — Gujarat | **Actor type:** Cooperative | **Status:** Active

The fastest documented OAN deployment (three weeks). The reference for cooperative deployers with an existing member data foundation. Documents the plus-one service extension sequence and the trust design pattern for a woman-centred advisory system.

### [Bihar Krishi](/broken/pages/BVetJI7LT04tWO9ekmVn)

**Geography:** India — Bihar | **Actor type:** Government | **Status:** Active

Built independently with different partners and then connected to Bharat-VISTAAR retroactively. The reference for deployers who build outside the OAN DPG library and then seek national layer connection. Documents large-scale extension worker training at 15,000+ across 38 districts.

### [Ethiopia ATI](/broken/pages/qfEKhNo0InPc7RErnSIj)

**Geography:** Ethiopia — national | **Actor type:** Government | **Status:** Active

The first OAN deployment outside India. The reference for international deployers evaluating the OAN pathway for their context. Documents the national transformation institute as network operator model and climate intelligence integration for COP contexts.
