# CAF Ritual — Architecture Kata

## Context

You are an enterprise architect facilitating or preparing an **Architecture Kata** — the CAF ritual for collective, team-level architecture practice.

Kata topic or challenge: $ARGUMENTS

Read available artifacts:
- `project/principles.md`
- `project/requirements.md`
- `technology/fitness-functions.md` (if available)

---

## Objective

Produce an **Architecture Kata Package** — the facilitation materials and/or the documented output of a kata session.

In the CAF, the Architecture Kata is a recurring ritual (recommended: quarterly) where the team collectively designs solutions to architecture challenges. It is inspired by coding katas — deliberate practice to build collective muscle memory. The goal is not to produce a final design, but to practice the architectural thinking process together.

---

## Output: `rituals/kata-[topic]-[date].md`

Use today's date in YYYY-MM-DD format for the filename.

### Part A — Facilitation package (prepare before the session)

#### 1. Kata brief

**Challenge statement** (read aloud at the start — 2–3 minutes):
> [A realistic business or technical challenge drawn from $ARGUMENTS or current project context. Written as a problem, not a solution. Example: "Our payment service is processing 10,000 transactions per day. The business wants to grow to 500,000 per day within 18 months. The current architecture is a monolith with a shared database. What would you do?"]

**Constraints** (non-negotiable boundaries):
- [e.g. "Must use the existing PostgreSQL database for at least 12 months — migration budget not approved"]
- [e.g. "Team of 6 engineers, no additional headcount"]
- [e.g. "Must comply with PCI-DSS"]

**Success criteria** (what a good solution looks like — reveal after first round):
- [e.g. "Handles 10x load increase without architectural redesign"]
- [e.g. "Each component can be deployed independently"]
- [e.g. "A new engineer can understand the architecture in < 1 hour"]

#### 2. Kata format

**Duration:** 90 minutes (recommended)
**Participants:** 4–8 people (mix of architects, engineers, product people)
**Rounds:**

| Round | Duration | Activity |
|---|---|---|
| 1 | 20 min | Teams sketch their solution independently (pairs or trios) |
| 2 | 15 min | Each team presents their approach (5 min each) |
| 3 | 10 min | Reveal success criteria — teams assess their own solution |
| 4 | 20 min | Full group: what would you keep from each approach? Build a synthesis |
| 5 | 15 min | Document decisions and learnings |
| 6 | 10 min | Retrospective: what did we learn about how we think about architecture? |

**Facilitation tips:**
- No solution is wrong — the goal is the conversation, not the answer
- Encourage disagreement — unresolved tensions are the most valuable output
- Capture "things we don't know" as explicitly as "things we decided"
- Connect to CAF principles throughout — ask "which principle applies here?"

#### 3. Preparation checklist

- [ ] Kata brief written and reviewed
- [ ] Room booked (whiteboard / Miro board prepared)
- [ ] Participants invited with brief context (not the solution)
- [ ] Timer ready
- [ ] Capture method prepared (photographer, note-taker, or shared Miro)

---

### Part B — Session output (fill during/after the session)

#### 4. Solutions explored

For each approach presented in Round 1–2:

**Approach [A / B / C]** — [Team members]

Architecture sketch summary:
- [Key component 1]
- [Key component 2]
- [Integration approach]

Strengths:
- [...]

Weaknesses / risks:
- [...]

Principle alignment:
- P1 (Modularity): [assessment]
- P2 (Resilience): [assessment]
- P3 (CD/Operability): [assessment]

#### 5. Synthesis — what the group converged on

After Round 4:

**Elements kept from Approach A:**
- [...]

**Elements kept from Approach B:**
- [...]

**Tensions not resolved** (document these explicitly — they are important):
- [e.g. "Team split on event-driven vs synchronous API for X — needs PoC"]
- [e.g. "No consensus on where to put the domain logic — needs ADR"]

#### 6. Decisions and actions

| Decision / action | Owner | Type | Next step |
|---|---|---|---|
| [e.g. Use event-driven pattern for order processing] | Product Architect | Architecture decision | Create ADR via `/caf.product-adr` |
| [e.g. Run PoC on event sourcing for audit trail] | Lead Engineer | Technical spike | Add to architecture runway |
| [e.g. Revisit database strategy in next kata] | Team | Deferred | Schedule next kata |

#### 7. Kata retrospective

**What went well:**
- [...]

**What to improve next time:**
- [...]

**Collective learning** (1–2 sentences: what did the team learn about architecture or about how they work?):
> [...]

#### 8. Next steps

- [ ] Create ADRs for decisions made during the kata
- [ ] Add technical spikes to architecture runway
- [ ] Schedule next kata (recommended: in 3 months, or when a significant new challenge emerges)
- [ ] Share kata output with stakeholders who weren't present

---

## Quality gates

- [ ] Kata brief is a problem statement (not a solution)
- [ ] At least 2 distinct approaches were explored
- [ ] Unresolved tensions are explicitly documented (not smoothed over)
- [ ] At least 1 ADR or technical spike is generated from the kata
- [ ] Retrospective is completed

Save the output to `rituals/kata-[topic]-[YYYY-MM-DD].md`.
