# Deploy First: The Data Posture Shift

**Dimension(s):** A: Problem orientation (A2 Data posture)
**Type:** Decision / Pattern

## What this is

The data posture shift reverses the conventional sequencing of data work and AI deployment:

**FROM** "Clean the data first, then deploy AI"
**TO** "Deploy first; AI creates the demand for connected, clean data"

The key reframe: the unlock is access, not quality. Large language models are designed to work with messy, unstructured, heterogeneous data from multiple sources. The question an adopter should ask is not "what data do we have and how good is it?" but "what data exists across our silos and can we connect it?"

Once connected, AI reveals what the data actually contains — which creates institutional demand for cleaning and standardisation. The demand follows the deployment, not the other way around.

## Why it matters

Waiting for perfect data before deploying is waiting for a reason that will never arrive on its own. Most deployments that have stalled on data readiness have done so because the wrong question was being asked. The framing of "clean first" guarantees delay. The framing of "connect and deploy" unlocks progress from existing assets.

The inverse is also important: AI does not just use data. It reveals what the data actually is. Officials who have never seen their own data queried together — across departments, across years — are often stunned by what it shows. This is itself an institutional outcome of the deployment, separate from any value to end users.

## What the pathways show

🟡 In MahaVISTAAR (Maharashtra), government departments had APIs that had existed for years but had never been called. Once AI connected them, officials asked "whose data is right?" for the first time. Nobody needed to clean the data first. The connection itself was the intervention.

🟡 Malawi has 67 health databases, all unconnected. The data posture challenge is not quality — it is connection. (This deployment is referenced as a parallel case; no pathway documentation exists for Malawi in this wiki yet.)

⬜ Data flows in both directions: the deployed system returns anonymised, aggregated signals back to institutions — which advisories are being accessed, which crops have insufficient guidance, which regions show stress patterns. AI creates a feedback loop that improves institutional data over time.

## Two decisions within data posture

Adopters must resolve two architectural decisions early:

**1. Federate vs. aggregate**
- **Federate:** Connect at query time. Each institution retains data ownership. The AI accesses data at the moment of query, without copying it. See [[concepts/federate-vs-aggregate-data]] for full treatment.
- **Aggregate:** Copy into a central warehouse. Simpler to query; more complex to govern.

**2. Opt-in / consent-based vs. pre-loaded**
- Opt-in: Data is accessed only when a user consents at query time.
- Pre-loaded: Data is ingested into the system's knowledge base in advance.
Both are data posture questions with governance implications (see F2 governance).

## Pathways that cover this

- [[deployments/mahavistaar]] — APIs connected without prior cleaning
- [[deployments/amul-sarlaben]] — Existing data infrastructure (2 billion transactions) as enabler of 3-week deployment

## Related concepts

- [[concepts/federate-vs-aggregate-data]] — The specific architectural decision within data posture
- [[concepts/compression-sequence]] — Deep data infrastructure is one reason Amul achieved 3-week deployment
