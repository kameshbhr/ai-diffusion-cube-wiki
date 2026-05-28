# The Six Dimensions Framework

The AI Diffusion Cube framework exists to compress the time, cost, and risk of taking an AI deployment from idea to scale in public-interest sectors. It captures the full surface area of a deployment — not just what you build, but who you are building for, who you are building with, and what has to hold together for it to last. Every source of delay and failure in real deployments traces back to one or more of these six dimensions.

## Why these six dimensions

Field experience across agriculture, health, livelihoods, and education deployments confirms a consistent finding: roughly 30% of what determines whether a deployment reaches scale is technology, and 70% is non-technology. The six dimensions reflect this ratio. Two dimensions (A and B) cover problem framing and technical architecture. Four dimensions (C, D, E, F) cover the institutional, ecosystem, workforce, and operational conditions that determine whether the technology ever reaches the people it was built for.

These six dimensions are the minimum necessary set. A deployment that addresses only some of them will stall at a predictable point — usually within the first six months of pilot. Dimension A alone produces an accurate solution to the wrong problem. Dimension B alone produces a system no institution will sustain. Dimensions C and D alone produce an ecosystem without the workforce capacity to absorb it. The dimensions are orthogonal: they do not duplicate each other, and none can be derived from the others.

## The six dimensions

### A — Problem Orientation
*Question it answers: Where do I start?*

The specific problem being solved, for whom, and what success looks like from the end user's point of view. This dimension covers whether there is existing data to start from or whether data must be built, whether the solution must work for users who are low-literacy, offline, or voice-first, and what proof of impact is required before the deployment can scale. Getting A wrong — solving the wrong problem, building on absent data, designing for a user who is not your actual user — is the most common and most expensive failure in this space.

### B — Architecture
*Question it answers: What do I build with?*

The technology stack — AI models, compute, data choices, interfaces, and system integrations — that keeps the deployment flexible and evolvable. This dimension covers how AI connects to existing data without centralising it, how the deployment avoids lock-in to a single vendor, and how it is protected against harm. A seven-layer system architecture underlies this dimension: user, interface, moderation, AI decision engine, knowledge and scientific models, live data sources, and DPI foundation. The moderation layer is not optional — it is what makes the system safe to deploy at scale.

### C — Institution
*Question it answers: What kind of undertaking is this?*

The deploying institution — its structures, authority, capabilities, and how it secures and sustains funding. This dimension covers whether the deployment is framed as a project or a transformation, whether internal resistance is acknowledged and addressed, whether the institution can outlast the key individuals who drove it, and what happens to accountability when something goes wrong. Institutions that treat an AI deployment as a technology procurement rather than an institutional capability change reliably fail to sustain it beyond the pilot.

### D — Ecosystem
*Question it answers: Who does what, and how do we work together?*

The partners, enablers, and stakeholders assembled around the deployment — who they are, what roles they play, who holds the network together, and how trust is established and maintained. In every documented deployment, the deploying institution was not capable of executing alone: it needed technology partners, domain knowledge providers, civil society intermediaries, and field execution partners. This dimension captures how those relationships are structured, who plays the network operator role, and what breaks when a partnership does not work out as expected.

### E — Workforce
*Question it answers: How do my people absorb this — and stay capable?*

The people — field workers, extension officers, teachers, frontline staff — who carry the deployment into daily practice. The AI system is only as useful as the last-mile human who translates it for the user who needs it. This dimension covers when training happens (too early means it is forgotten; too late means staff are defensive), what depth of training is required, and whether field staff can still do their job if the system goes down. Workforce resistance that is not addressed before rollout is the single most common cause of low adoption.

### F — Operating Model
*Question it answers: What makes this last beyond the pilot?*

How the deployment sustains itself — through team structure, governance, performance tracking, outcome signals, and course correction based on what the field reveals. This dimension covers what the deployment costs to build and to run, how the pilot-to-production handover is structured, and whether there is a mechanism to detect problems before they become irreversible. Deployments that measure outputs (queries answered) but not outcomes (farmer income, crop loss) cannot demonstrate the value needed to sustain funding beyond the first grant cycle.

## The FROM→TO shifts

For the evidence-based shift patterns within each sub-component, see the [Dimension Shifts synthesis page](synthesis/dimension-shifts.md).
