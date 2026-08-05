# The AI Diffusion Pathway Framework

This framework serves two purposes: **(1)** generating a structured pathway document from raw source material, and **(2)** guiding an adopter conversationally toward relevant know-how. Both uses draw on the same underlying structure — dimensions, sub-categories, stages, unit types, and insight forms — just applied in different directions: generation *extracts* units from raw text into this structure; adopter guidance *retrieves* units from this structure to answer a live question.

---

## 1. The core structure

### The four dimensions

| Dimension | Central question | Sub-categories |
| --- | --- | --- |
| **Persona** | Are we solving the right problem for the right person? | A. Problem and Persona · B. Current Journey and Friction · C. Outcome and Success · D. Scope, Inclusion, and Trust |
| **Solution** | Are we building the right system to solve it? | A. AI Fit and Comparative Advantage · B. UX, Channel, and Integration · C. Model, Architecture, and Infrastructure · D. Data and Knowledge Readiness · E. Performance, Reliability, and Scale |
| **Institution** | Can the institution own, absorb, govern, and sustain it? | A. Mandate, Ownership, and Decision Rights · B. Workforce and Change · C. Governance, Safety, and Redress · D. Accountability, Liability, and Compliance · E. Data Stewardship · F. Operating Model and Sustainability · G. Institutionalisation and Continuous Improvement |
| **Ecosystem** | Can the required network of actors execute and support it? | A. Partner Architecture and Roles · B. External Data and Infrastructure Dependencies · C. Delivery, Distribution, and Trust · D. Coordination, Procurement, and Incentives · E. Resilience, Portability, and Contingencies · F. Ecosystem Learning and Diffusion |

**30/70 thesis**: Persona + Solution = defining and building the right thing. Institution + Ecosystem = the larger work of enabling adoption, accountability, and sustainability. Not four equal shares of effort.

### Cross-cutting concerns

**Data**
- Persona — evidence for problem/population/outcome
- Solution — is data usable/reliable/current
- Institution — who owns/authorises/corrects it
- Ecosystem — external sources, agreements, SLAs

**Trust**
- Persona — does the excluded user trust this channel enough to use it
- Solution — is trust conveyed through channel/UX choices — tone, disclosure, voice vs. text
- Institution — accountability: who the user blames when it's wrong, who stands behind the answer
- Ecosystem — trust in delivery partners and distribution channels, independent of the institution itself

### The four adopter stages

| Stage | Central question | Done when... |
| --- | --- | --- |
| **Explore** | Is AI appropriate, and what would it take? | Precise excluded-user definition. Honest comparison with alternatives. Order-of-magnitude cost sense. |
| **Define** | What must be true before building? | Named data owners. Named mandate holder. Architecture posture chosen. Safety boundaries designed. |
| **Pilot** | What breaks with real users and real institutional conditions? | Failure taxonomy. Named institutional response to first public failure. Real cost-per-interaction data. |
| **Scale** | Can the institution own, sustain, and continuously improve it? | Budget line. Named operational owner. Monitoring mechanism. Operating model written down. |

### The five unit types

| Type | Definition | What makes it reusable |
| --- | --- | --- |
| **Strategic Decision** | A framing, governance, or design decision that shaped what got built. Usually invisible in the final product. | The condition tag — when does this apply, when doesn't it? |
| **Tactical Decision** | A stack, sequence, cost, or implementation decision specific enough to reuse. | A before→after: what changed because of this decision. |
| **Failure and Fix** | Something that broke, the fix, and what the fix revealed about the system. | The fix reveals the structural insight — not the failure alone. |
| **Playbook** | A genuine multi-step, gated sequence for a recurring situation. | Actionable: "if X, do Y before Z." |
| **Toolkit Asset** | A reusable technical component, template, or governance artefact. | Another adopter can lift and adapt it without rebuilding. |

**Tag every unit:** Dimension + Sub-category + Stage + Type + Condition tag.

---

## 2. The question bank — insight forms and stage-weighting

### EXPLORE — Is AI the right answer, and what would it take?

| Dimension | Core question | Listening for | Insight form | Corpus example |
| --- | --- | --- | --- | --- |
| **Persona** | Who specifically is excluded from this service today — and what do they do instead? | The workaround is the data. It reveals the real replacement baseline. | Excluded user + named barrier + current workaround | MahaVISTAAR: women farmers receiving contradictory advice from fertiliser sellers. No trusted official source in their language. |
| **Solution** | What channel or system are you replacing, what does it fail at, and is AI actually the right tool for that failure? | Two human callers, paper forms, nothing — plus honest reasoning on AI-fit vs simpler fixes. | Current channel + failure mode + AI-fit justification | Lend A Hand: two human callers couldn't collect fortnightly feedback from thousands of dispersed interns. |
| **Institution** | Who inside the institution has to personally want this to work — and do they know yet? | Not procurement sign-off. The person whose professional stake is tied to success. | Named champion + their specific stake | MahaVISTAAR: Commissioner-level ownership required before any department would authorise data connections. |
| **Ecosystem** | Who else has tried to solve this for this population, and what happened? | Precedent deployments, failed attempts, adjacent tools. Who do they trust as a reference peer? | Named precedent + what transferred + what didn't | Ethiopia ATI drew on MahaVISTAAR: 9 months → 3 months. Architecture transferred. Farmer-trust mechanics needed local adaptation. |

### DEFINE — What are the irreversible decisions?

| Dimension | Core question | Listening for | Insight form | Corpus example |
| --- | --- | --- | --- | --- |
| **Persona** | What is the one question a user will ask that this system must answer, or the pilot fails? | Forces scope to its minimum. Shapes data model, prompt design, safety boundaries. | Single critical use case + binary success definition | MahaVISTAAR: "What should I spray this week in my village?" Required live mandi data, weather API, pest calendar, conversational Marathi. |
| **Solution** | Which architecture choices, if wrong, would take six months to undo — and is every data source named, with an accountable owner for each? | Residency, vendor lock-in, sovereignty, orchestration ownership. Not "government data" — ICAR, IMD, APMC, named humans. | Irreversible decisions list + data source registry (source × owner × cadence × accountability) | MahaVISTAAR: four named data owners before launch, each connected via API — AI layer consumes but doesn't own the data. |
| **Institution** | Who approves what the system says, have they agreed to own that, and what testing/timeline has the institution committed to before real users? | Content authority, not technical sign-off. Staged testing with named gate criteria. | Content authority + approval process + testing progression | Voice AI: the bot speaks in the department's name. The department must own every answer — including wrong ones. |
| **Ecosystem** | Which parts can you not build yourselves — and do you have a named partner for each? | Data owners, language models, telephony partners, integrators, field networks. Unnamed dependencies are unmanaged risk. | Dependency map: component × build-or-source × named partner | Bhili: eight distinct ecosystem roles, all named before model work. Project stalled when the linguist role was unnamed for three months. |

### PILOT — Live with real users. What's breaking?

| Dimension | Core question | Listening for | Insight form | Corpus example |
| --- | --- | --- | --- | --- |
| **Persona** | Which user interactions are failing — is that a scope problem or a quality problem? | Scope = outside mandate. Quality = mandate questions answered badly. Different fixes. | Failure taxonomy: scope vs quality vs experience | Voice AI: out-of-mandate answers = institutional boundary crossing. Required explicit refusal design, not better prompting. |
| **Solution** | Which component is causing the most pain, is it replaceable, and which data source is going stale or wrong? | Bundled-vs-unbundled plays out here. Data quality failures at Pilot look like AI failures to users. | Component failure + replaceability + data quality issue + owner response time | MahaVISTAAR: mandi price 48hr lag caused wrong harvest-timing advice. Fix: governance call with APMC to 6-hr cadence — not a technical fix. |
| **Institution** | What has the institution seen fail publicly — and did they own it or disown it? | How the institution responds to the first failure is the strongest signal about whether this scales. | First public failure + institutional response (own vs disown) | Voice AI: bot answered outside mandate. Department tightened refusal boundaries — didn't shut down. Ownership held. |
| **Ecosystem** | Which partner is underperforming — and do you have an alternative? | Mid-pilot switching is painful but possible. Post-scale switching requires a rebuild. | Partner performance log + contingency plan | Voice AI: parallel vendor testing recommended precisely because mid-pilot switching is possible. |

### SCALE — Expanding to population. Can the institution own this without the founding team?

| Dimension | Core question | Listening for | Insight form | Corpus example |
| --- | --- | --- | --- | --- |
| **Persona** | Are new user segments arriving that the pilot wasn't designed for? | Scale reveals "the user" was multiple users — feature phone vs smartphone, dialect A vs B. | User segment expansion map + design change required per segment | Voice AI: multilingual demand discovered post-launch. Retrofit significantly harder than designing for it. Preventable. |
| **Solution** | Which components are you now unbundling, what triggered it — and which data sources are breaking under scale, do formal SLAs exist? | Cost/control arguments become concrete numbers at scale. | Unbundling decision (component × trigger × gain) + data SLA map | Bharat-VISTAAR: required formal data SLAs with 12 state agriculture departments. Each became an accountable node. |
| **Institution** | Has the institution absorbed this — budget line, named owner, review cadence — and does the system leave people more capable or more dependent? | Absorption vs "still the project team's problem." Workforce agency outcome. | Absorption indicators (budget + owner + review cadence) + agency outcome (capability vs dependency) | Voice AI: shift from "project" to "service" is the signal. Departmental adoption requires owning voice as a service. |
| **Ecosystem** | What from your deployment could the next adopter reuse — with what conditions? | Not "we did X." "X works when Y is true, fails when Z is true." | Transferable unit + condition tag (applies when / fails when) | MahaVISTAAR → Ethiopia ATI: architecture and trust-framing transferred. Specific data partnerships didn't — condition: government credibility as trust mechanism. |

### Stage-weighting of sub-categories

Primary = ask/check directly this stage. Secondary = ask only if relevant or if the core question surfaces it. Dormant = don't initiate; only follow if raised unprompted.

**Persona**

| Sub-category | Explore | Define | Pilot | Scale |
| --- | --- | --- | --- | --- |
| A. Problem and Persona | Primary | Secondary | Dormant | Secondary |
| B. Current Journey and Friction | Primary | Secondary | Dormant | Dormant |
| C. Outcome and Success | Secondary | Primary | Primary | Primary |
| D. Scope, Inclusion, and Trust | Secondary | Primary | Primary | Primary |

**Solution**

| Sub-category | Explore | Define | Pilot | Scale |
| --- | --- | --- | --- | --- |
| A. AI Fit and Comparative Advantage | Primary | Secondary | Dormant | Dormant |
| B. UX, Channel, and Integration | Secondary | Primary | Primary | Secondary |
| C. Model, Architecture, and Infrastructure | Secondary | Primary | Primary | Primary |
| D. Data and Knowledge Readiness | Secondary | Primary | Primary | Primary |
| E. Performance, Reliability, and Scale | Dormant | Secondary | Primary | Primary |

**Institution**

| Sub-category | Explore | Define | Pilot | Scale |
| --- | --- | --- | --- | --- |
| A. Mandate, Ownership, and Decision Rights | Primary | Primary | Secondary | Secondary |
| B. Workforce and Change | Secondary | Primary | Primary | Primary |
| C. Governance, Safety, and Redress | Dormant | Primary | Primary | Secondary |
| D. Accountability, Liability, and Compliance | Dormant | Secondary | Secondary | Primary |
| E. Data Stewardship | Dormant | Primary | Secondary | Primary |
| F. Operating Model and Sustainability | Secondary | Primary | Secondary | Primary |
| G. Institutionalisation and Continuous Improvement | Dormant | Dormant | Secondary | Primary |

**Ecosystem**

| Sub-category | Explore | Define | Pilot | Scale |
| --- | --- | --- | --- | --- |
| A. Partner Architecture and Roles | Secondary | Primary | Secondary | Secondary |
| B. External Data and Infrastructure Dependencies | Secondary | Primary | Secondary | Primary |
| C. Delivery, Distribution, and Trust | Dormant | Secondary | Secondary | Secondary |
| D. Coordination, Procurement, and Incentives | Dormant | Secondary | Secondary | Secondary |
| E. Resilience, Portability, and Contingencies | Dormant | Dormant | Primary | Primary |
| F. Ecosystem Learning and Diffusion | Dormant | Dormant | Secondary | Primary |

**Using it for generation:** check raw content against the relevant cell's insight form before tagging a unit — not by how the content *sounds*, but by whether it actually contains the insight form's components. Cross-check the Primary sub-categories: a dimension×stage cell can have units in it and still miss the stage's real concern if none of those units satisfy a Primary sub-category.

**Using it for adopter guidance:** the core question per dimension×stage is the agent's opening probe with a live adopter. If a Primary sub-category for their current stage is unaddressed, that's what the agent asks about next — surfacing relevant corpus units as it goes.

---

## 3. The pathway document — output structure

A pathway document is not a case study. A case study documents what was built. A pathway document is written for the next adopter — what they would need to decide, the alternatives they would consider, the conditions under which different choices are correct.

*Physical analogy: a pathway is not the route the pioneer took. It is the marked trail they left for the next traveller.*

| # | Section | Purpose | Contents |
| --- | --- | --- | --- |
| 0 | **Reading guide** | Orients the adopter | What a pathway is. How retrieval works. Where reusable value concentrates. How to navigate by dimension/stage. |
| 1 | **Pathway identity** | Names the deployment for retrieval | Deployment name, sector, geography, population served, stage reached, contributing organisation, key dates, 2-sentence summary. Scale/impact achieved — headline usage and outcome numbers, as-of date. Cost anchor — setup + run-rate cost order of magnitude, as-of date. Build effort — time, team size, partner count to reach current stage. Known downstream adopters / reuse record — who has since built on this pathway, and how much faster. Scope / does-not-transfer-when. |
| 2 | **The 4×4 grid** | Shows where knowledge is dense and where gaps remain | Coverage map: 4 dimensions × 4 stages, density symbols (●●● / ●● / ● / ○). Empty/thin cells checked against Primary sub-categories, not raw count. |
| 3 | **Micro-innovations** | The core reusable content | Tagged units organised by dimension, then stage. Each unit: decision, alternative considered, condition tag (applies when / fails when), before→after outcome. |
| 4 | **Toolkits and playbooks** | Reusable artefacts and process knowledge | Technical templates, governance frameworks, testing protocols, prompt patterns, vendor criteria — each tagged with conditions for reuse. |
| 5 | **Problem→solution patterns** | Maps recurring problems to known fixes | Problem → root cause → solution → result → condition. Built from Failure-and-Fix units and other clear problem→fix patterns across deployments. |
| 6 | **Retrieval guide** | Helps the next adopter find what's relevant fast | Organised by adopter intent (e.g. "I need to avoid vendor lock-in at Define stage") → points to relevant units and toolkit assets. |
| — | **Provenance appendix** *(contributor-only — never adopter-facing)* | Traces what was used to build the pathway, for future reconciliation | Table keyed by source file → which Sections/fields/units it covers, and whether it's primary or confirms-only. |

Sections 0–6 are adopter-facing — this is what the AI layer reads and surfaces in any adopter-facing response. The Provenance appendix is contributor-facing only, never surfaced in adopter-facing output. It is not "Section 7" and must not be numbered as a continuation of 0–6. The word "Framework" (or any reference to it, or to the generation process, as such) must never appear in Sections 0–6.

### Worked example — a single micro-innovation unit

> **Failure:** Direct hardwiring of the AI layer to the ICAR database — a backend change required an AI-layer rebuild.
> **Fix:** Separated the AI layer from the data layer using a standardised API gateway. The AI system retrieves data but does not own it.
> **Insight:** At scale with multiple data sources, this is the difference between a maintainable system and a fragile one.
> **Condition — applies when:** Multiple data sources with different owners and update cadences; government deployment where data accountability must remain with named departments.
> **Condition — fails when:** Single, stable, internally-owned data source with no requirement for departmental accountability separation.
> **Before → After:** Before: data errors required rebuilding the bot prompt architecture. After: data errors are fixed by the data owner without touching the AI layer.

### Section-by-section generation notes

**Section 1 — Pathway identity.** Populate every field, including the impact/cost/effort/reuse fields. Tag each with an as-of date where the source gives one. Where the source doesn't support a field, write "Not documented in the source" rather than leaving it blank or inventing a plausible number.

**Section 2 — Coverage grid and gaps.** Density counts (●●● / ●● / ● / ○) are driven only by each unit's Stage (origin) — never by its "Also relevant at" tag. Apply the four gap-survival tests before including any gap — **concreteness**, **non-fabrication**, **boundary-restatement**, **existing-coverage** — and default toward dropping a candidate gap over reframing it. Ground every surviving gap in this pathway's own vocabulary and cite the specific unit number(s) it relates to. The gap list should never be padded to match every empty grid cell.

**Section 3 — Micro-innovations.** Organise by dimension (use the dimension names as subheadings), and within each dimension, order units by Stage (Explore → Define → Pilot → Scale). Each unit:
- Plain sequential number across the whole document (1, 2, 3...) — never a composite ID code
- Bold title line: `**N. Short decision-oriented title**`
- A bulleted tag block immediately below the title:
  - `Dimension: ...`
  - `Stage: ...` — where the evidence was discovered. This is what the Section 2 grid counts.
  - `Also relevant at: ...` — optional. Other stages where this unit is genuinely useful, even though the evidence originated elsewhere. Never counted in the grid. Omit for genuinely single-stage units.
  - `Type: ...` (Strategic Decision / Tactical Decision / Failure and Fix / Playbook / Toolkit Asset)
  - `Relevant to: ...` — optional, include only when the source material itself differentiates by audience. Don't add as decoration.
- Then bulleted content fields, matched to the type:
  - **Strategic/Tactical Decision:** Decision, Alternative considered, Condition — applies when, Condition — fails when (if stated), Before → After (or "Not documented in the source")
  - **Failure and Fix:** Failure, Fix, Insight, Condition — applies when
  - **Playbook:** Playbook (the actual sequence, stated as steps), Note (if there's a common failure mode of skipping steps), Condition — applies when, Before → After (if available)
  - **Toolkit Asset:** Toolkit asset (what it actually is), Reusable as-is (what makes it liftable), Condition — applies when

**Section 4 — Toolkits and playbooks.** Table listing every unit tagged Toolkit Asset or Playbook, cross-referenced by unit number, with a one-line reuse condition each.

**Section 5 — Problem→solution patterns.** Table: Problem | Root cause | Solution | Result | Condition. Populate from Failure-and-Fix units and any other clear problem→fix pattern in the source material — don't force entries that aren't genuinely there.

**Section 6 — Retrieval guide.** Flat list of realistic questions a future adopter might type, each mapped to the relevant unit number(s): `"question in their words" → Unit N, Unit M`. Use both a unit's Stage and its "Also relevant at" tags when deciding which questions a unit should answer. Cover the range of dimensions, not just the most obvious ones.

### Provenance appendix — spec

Place after Section 6, visually and structurally separated from it (a clear divider and a heading that does not read as "Section 7"). **The AI layer must never surface this appendix's content in an adopter-facing response, in any mode.**

A table keyed by **source file**, not by unit or field:

| Source file | Covers | Notes |
| --- | --- | --- |
| [filename/doc title, as-of date] | [Section numbers, field names, and/or unit ranges populated from it] | [Primary source / confirms only, doesn't add / superseded, etc.] |

Rules:
- Key by raw source file — one row per file, not one row per content item. Must cover everything drawn from raw material: Pathway Identity fields, Section 3 units, the toolkits table, and the problem→solution patterns — not units alone.
- "Covers" cites actual Section numbers, field names, and unit ranges — not vague descriptions like "background info."
- When a file is derivative of another (a condensed summary, an earlier draft of the same material), say so explicitly and mark it "confirms, doesn't add" rather than listing it as an independent source for content it merely restates.
- If a source file contributed nothing that made it into the final document, don't list it — this appendix records what was actually used, not everything attached.

---

## 4. Extracting units from raw material

Whether the raw material is an interview transcript or a document dump, the same discipline applies before anything gets treated as a unit:

| Step | What it means |
| --- | --- |
| **Tag every unit** | Dimension + Sub-category + Stage + Type + Condition tag. No untagged units enter the corpus. `Also relevant at: [Stage, Stage]` — optional. Captures where a unit is *useful* beyond its stage of origin. **Does not count toward the Section 2 coverage grid** — grid density is driven by Stage (origin) alone, so gap-detection stays honest. This field feeds only the Section 6 retrieval guide and adopter-facing navigation. Stage reflects where the evidence was **discovered** (counted in the grid). "Also relevant at" reflects where it's **useful** (not counted, used for retrieval only). Never merge the two. |
| **Write the before→after** | Every tactical/strategic unit needs an outcome statement. Without it, it's a lesson, not a finding. |
| **Name the failure specifically** | "It didn't work" is not a unit. Name the failure, the fix, and the threshold or insight the fix revealed. |
| **Flag the gaps** | Check against Primary sub-categories per stage, not raw cell density — a filled cell can still miss its stage's real concern. |
| **Don't fabricate** | If a before→after, a named individual, or a condition isn't in the source, write "Not documented in the source" rather than inventing it. |

**The synthesis test:** could someone who never saw the raw material make a different decision because of this unit? If yes, it's a real unit. If it just describes what happened, it isn't.

---

## 5. Classification rules

Apply these before finalizing any unit's tags:

1. **Check content against the cell's insight form, not just intuition.** For each dimension×stage combination, the question bank defines what that cell is actually supposed to capture (e.g. Institution/Define wants "content authority + approval and escalation process"; Institution/Pilot wants "first public failure + institutional response"). Check which insight form the content actually satisfies — don't tag by how it *sounds*.
2. **Re-check every axis when you move a unit, not just the one that prompted the move.** If you're correcting a unit's stage, also re-verify its dimension and type are still right — errors compound across axes, not just within one.
3. **Playbook requires a genuine multi-step, gated sequence** — "do X, then don't proceed to Y until X clears, then Z." A single decision that merely sounds procedural is not a playbook, even if it uses words like "process" or "steps." If it's one decision, tag it Strategic or Tactical Decision instead.
4. **Toolkit Asset requires an actual reusable artifact** — a checklist, template, schema, or built tool someone else can lift and adapt without rebuilding. A decision about *how* to structure something is a Decision, not a Toolkit Asset.
5. **Stage (origin) reflects where the evidence was discovered, never where it's most useful.** Use "Also relevant at" for usefulness elsewhere — don't relabel Stage itself.
6. **A cell with 1–2 units is not automatically "covered."** Check whether the existing unit(s) actually satisfy that cell's insight form. If they don't, that's still an open question for Section 2, even though the grid shows a filled cell.
7. **Don't fabricate what isn't in the source.** If a before→after, a named individual, a condition, or an alternative-considered isn't stated or reasonably inferable, write "Not documented in the source" or omit the field rather than inventing plausible-sounding content.
8. **Coordination and sign-off — Institution vs. Ecosystem.** Before tagging, check whether the counterpart sits inside the contributing organisation's own chain of command. If it required a separate negotiated agreement, MOU, or incentive alignment with an organizationally distinct actor, tag Ecosystem — even when that actor is itself state-affiliated. Org-chart independence is the test, not government affiliation.
9. **Benchmark numbers need a real decision behind them.** Before creating a Decision unit around a quantitative figure, confirm a genuine alternative was considered and there's a before/after to report. If the number is a standalone fact about the deployment as a whole with no specific alternative behind it, it belongs in Section 1 — not manufactured into a Section 3 unit.
10. **When the source states both a general principle and a specific illustrating case, the Decision field is the principle, not the case.** Use the specific case in Before→After or as supporting detail. A unit whose "Decision" just restates the example is under-generalized — a different adopter can't reuse someone else's staffing ratio, but they can reuse a sizing method.

---

## 6. Formatting and tone rules

- Never mention this framework by name, never explain classification reasoning, never leave notes about reclassification history, anywhere in Sections 0–6.
- Use "Dimension," never "Shift."
- Use plain sequential numbers for units, never composite ID codes.
- Every cross-reference (toolkit table, retrieval guide, gap notes, Provenance appendix) must use the same unit numbers as Section 3 — check all of them after any renumbering.
- Keep Sections 0–6 consistent in tense and voice — written for the next adopter, not for whoever assembled it. The Provenance appendix is the one exception: it's written for the contributor, not the adopter, and is never numbered as part of the 0–6 sequence.

---

## 7. Generation self-check

Before finalizing a pathway document, confirm:

- [ ] Every unit's Dimension, Stage, and Type were checked against this framework's own definitions, not assumed from wording.
- [ ] No unit has a default `Source` field; `Origin deployment` appears only where this is a horizontal pathway and the unit's origin differs from the primary deployment.
- [ ] Every Playbook and Toolkit Asset genuinely meets the stricter bar (multi-step+gated / genuinely reusable artifact), not just "sounds procedural."
- [ ] The coverage grid's counts match the actual number of units in Section 3, cell by cell, counted by Stage (origin) only — "Also relevant at" tags were not counted.
- [ ] Every gap question in Section 2 passed all four tests (concreteness, non-fabrication, boundary-restatement, existing-coverage) — not just "the cell was empty."
- [ ] The gap list is not padded to match every empty grid cell.
- [ ] Every surviving gap uses this pathway's own vocabulary and cites specific unit numbers where relevant.
- [ ] All cross-references (Section 4 table, Section 6 retrieval guide, Provenance appendix) point to correct, current unit numbers.
- [ ] Every quantitative benchmark is either evidence inside a Decision unit's Before→After, or lifted to Section 1 — none invented a fake "alternative considered" just to house a number.
- [ ] Coordination-related units were checked against the chain-of-command test (Rule 8) before tagging Institution vs. Ecosystem.
- [ ] Section 1 includes scale, cost anchor, build effort, downstream reuse, and scope/non-transfer fields where the source material supports them.
- [ ] The Provenance appendix is keyed by source file, covers Sections 1, 3, 4, and 5 (not units alone), correctly flags any derivative/confirms-only files, and is not numbered as "Section 7."
- [ ] No framework references, meta-commentary, or reclassification history remain anywhere in Sections 0–6.
