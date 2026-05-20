# Dimension 5: Workforce

**One-line:** Who absorbs AI — the frontline people who carry the deployment into daily practice, and what they need to do that.

---

## What this dimension covers

The workforce is where AI meets reality. Field workers, extension officers, farmers, frontline staff — their adoption determines, in practice, whether a deployment works.

- **E1 — Training timing:** When training happens relative to deployment, and whether training is designed as a separate phase or embedded in the system's design. For end users, the best training is use itself. For institutional workforces, structured deliberate training is a different design problem.
- **E2 — Training depth:** What training actually covers — tool operation, or the reasoning behind it. Who trains the trainers? If knowledge stops at the first layer, it will not survive the second posting cycle.
- **E3 — Agency test:** Whether the deployment leaves frontline workers more capable and autonomous, or more dependent on the system. This is the clearest indicator of whether a deployment is genuinely useful or being imposed.

---

## What the wiki currently holds

One foundational source: "The Six Orthogonal Shifts - detailed version 2" (AI Diffusion Pathways initiative). Strongest field evidence from Amul/Sarlaben (E3 agency test, both outcomes), MahaVISTAAR (E1 design-by-use for end users), and Bihar Krishi (E1/E2 institutional workforce training at scale).

---

## Key patterns across pathways

**E1 — Training timing:**
🟡 For end users, the best training is use itself. Farmers in MahaVISTAAR were not trained and then given access. They called a number, asked a question, and got an answer. The natural progression — from simple queries (weather, pest) to complex actions (scheme applications, credit products, grievance tracking) — means each step trains the farmer for the next. Design the system so that use is training.

🟡 For institutional workforces, training is a different design problem — structured, deliberate, scaled. Bihar Krishi trained 15,000+ extension workers across 38 districts. Training timing for the beneficiary and training timing for the institutional workforce require different solutions.

⬜ You cannot bolt training on at the end. What translates technology into actual change is the know-how that allows people to absorb it and apply it in their own context. A fifth-grader who cannot read does not need better content — they need practice delivered in a way that builds confidence. That is a training design problem, not a technology problem.

**E2 — Training depth:**
🟡 In Indian government, extension officers rotate routinely. If knowledge stops at the first layer, it will not survive the second posting cycle. The test: can the system function when every individual who helped build it has moved to a different role?

⬜ "Who trains the trainers?" The rollout plan probably has a line item for "training." But who trains the people who train others? How deep does the understanding go? Can a district official explain to a sceptical colleague why the AI recommended what it did?

⬜ The institutional challenge is not getting people to use the system. It is building enough understanding that the system survives the departure of every individual who helped build it.

**E3 — Agency test:**
🟡 The Amul/Sarlaben deployment documented both sides of the agency test:
- **Positive outcome:** Younger family members who lack 30 years of dairy experience can now access expert knowledge through Sarlaben. Their reported experience: "informed, therefore powerful to make choices; freedom comes from knowing, and nobody can fool me." This is the right outcome: AI as an equaliser that gives the less-experienced person access to what the expert knows, while preserving their autonomy.
- **Risk named explicitly from the same deployment:** "There is skill in the hand that counts for more than information in the head." AI should make the farmer's skill more precise and their choices more informed. It should not replace the skill itself. If a pathway produces people who cannot function when the AI fails, you have built a system that works until it doesn't.

🟡 The test for the agency question: after twelve months on the pathway, can the farmer still function if the AI goes down?

🟡 Agency also has a progression. Farmers in MahaVISTAAR have moved from passive information queries to transactional actions — applying for schemes, tracking grievances, exploring credit. From passive information recipient to active agent using the system to get things done. The pathway should explicitly design for this progression.

⬜ A well-designed simulation serves double duty: training mechanism and proof. When an adopter runs through a simulated deployment, they should emerge with genuine understanding of the trade-offs they face — not just tool operation but the reasoning behind decisions. The simulation builds the capacity to make independent judgments when the AI fails or the context changes.

---

## Key decisions an adopter faces

| Decision | What the evidence shows |
|---|---|
| How to train end users? | Design the system so use is training. Natural progression from simple queries to complex actions. Don't train and then give access — give access and let use be the training. |
| How to train institutional workforce? | Structured, deliberate, scaled. Different design problem from end-user training. Bihar Krishi: 15,000+ extension workers, 38 districts — this is the reference scale. |
| How deep must training go? | Deep enough that the second layer can train the third, and the system can function after the first generation of builders has moved on. Test: can a district official explain why the AI recommended what it did? |
| Does the deployment leave people more capable or more dependent? | Design explicitly for the positive agency outcome. Test after 12 months: can the user function if the AI goes down? |
| How to design for the agency progression? | Build the pathway from information queries → transactional actions → independent decision-making. The end state is an active agent, not a passive recipient. |

---

## Common failure modes

- **Bolting training on at the end.** If training is phase 4 of a 4-phase rollout, it will not produce the capability required. Training is not a phase after deployment — it is embedded in the deployment design.
- **Training only the first layer.** Extension officers who rotate take the knowledge with them. The test: can the system function when everyone who helped build it has moved on? If not, training was insufficient.
- **Creating dependency.** If the extension officer stops exercising professional discretion because the AI provides the answer, the institutional capability the pathway depends on is being hollowed out. Information in the head does not replace skill in the hand.
- **Testing capability with the AI on.** The test of agency (can the user function if the AI goes down?) must be designed into the evaluation framework. Systems that work until they don't are not deployments — they are demos at scale.

---

## Pathways in this dimension

- [mahavistaar](../deployments/mahavistaar.md) — E1 (design-by-use for end users; natural progression from simple to complex); E3 (farmer progression from queries to transactions)
- [bihar-krishi](../deployments/bihar-krishi.md) — E1 (institutional workforce training); E2 (training at scale — 15,000+ extension workers)
- [amul-sarlaben](../deployments/amul-sarlaben.md) — E3 (agency test, both outcomes — positive and risk — documented)

---

## Gaps

- E3 longitudinal data: the agency test requires observation after 12+ months. No current source documents this with rigour — the evidence is early-stage observation, not systematic measurement.
- E2 in environments without staff rotation: all current field evidence for E2 comes from Indian government contexts where extension officer rotation is a structural reality. Different institutional contexts may produce different E2 challenges.
- Training for non-agriculture sectors (health workers, teachers) not documented in current sources.
- The simulation as training mechanism (serving double duty: training + proof) is named but not documented as implemented in any specific deployment.
