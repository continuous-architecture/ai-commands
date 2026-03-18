# CAF Self-Assessment

## Context

You are an enterprise architect or architecture team lead running a **Continuous Architecture Self-Assessment** — a structured evaluation of how well a team or organisation is practising the CAF.

Assessment context: $ARGUMENTS

This command does not require existing project artifacts. It can be run:
- At the start of a CAF adoption (baseline)
- Every 6 months (progress check)
- Before a professionalization event or Architecture Review Board
- As part of the Team Autonomy Readiness ritual

---

## Objective

Produce a **CAF Self-Assessment Report** — a scored maturity model across all 6 CAF views plus practices and rituals, with a personalised improvement roadmap.

This command directly addresses the community need for a self-assessment tool (toolkit issue #74).

---

## Output: `project/self-assessment-[YYYY-MM-DD].md`

---

## Instructions

For each dimension below, score the current state on a 1–4 scale:

- **1 — Initial**: Ad-hoc or absent. Not consistently practised.
- **2 — Developing**: Started but incomplete. Inconsistently applied.
- **3 — Defined**: Consistently practised. Documented and repeatable.
- **4 — Optimising**: Continuously improved. Others learn from this team.

Ask the user (or infer from context if project artifacts exist) to score each item. If running without user input, score based on available artifacts and note assumptions.

---

## Part 1 — CAF Views Practice

### Experience Objectives

| Practice | Score (1–4) | Evidence / notes |
|---|---|---|
| We start from user problems, not solution assumptions | | |
| We use JTBD to frame what customers are trying to achieve | | |
| We have defined personas with architecture sensitivities | | |
| Our architecture decisions trace back to user needs | | |

**View score:** [average] / 4
**Maturity level:** Initial / Developing / Defined / Optimising

### Product

| Practice | Score (1–4) | Evidence / notes |
|---|---|---|
| We maintain an architecture runway with prioritised enablers | | |
| Enablers are in the product backlog alongside business features | | |
| We use ADRs to document significant architecture decisions | | |
| We wait for the last responsible moment to decide (not upfront) | | |
| We have a clear product vision and defined boundaries | | |

**View score:** [average] / 4

### Technology

| Practice | Score (1–4) | Evidence / notes |
|---|---|---|
| Our system is modular — components can be deployed independently | | |
| We design for failure (redundancy, circuit breakers, graceful degradation) | | |
| We measure DORA metrics (deployment frequency, lead time, MTTR) | | |
| We have active fitness functions protecting architectural characteristics | | |
| We use DDD (bounded contexts, ubiquitous language, event storming) | | |
| We have a tech radar that guides technology choices | | |

**View score:** [average] / 4

### Operations

| Practice | Score (1–4) | Evidence / notes |
|---|---|---|
| We have defined SLIs and SLOs for our key services | | |
| We run post-incident reviews and act on findings | | |
| We have an operational readiness gate before major releases | | |
| We actively automate repetitive operational processes | | |
| We use AI/ML where it augments human judgement | | |

**View score:** [average] / 4

### Organisation

| Practice | Score (1–4) | Evidence / notes |
|---|---|---|
| Teams are organised around products / value streams (not functions) | | |
| Team cognitive load is assessed and managed | | |
| Inter-team interaction modes are explicit (not implicit) | | |
| Team boundaries reflect system boundaries (Conway awareness) | | |
| Teams have genuine autonomy within defined alignment guardrails | | |

**View score:** [average] / 4

### Enterprise Decomposition

| Practice | Score (1–4) | Evidence / notes |
|---|---|---|
| The enterprise is decomposed into explicit Operating Units | | |
| Each OU has a clear mission, client, and product responsibility | | |
| Domain boundaries are documented and respected | | |
| Core vs supporting vs generic domains are identified | | |
| Product portfolio is mapped to OUs with clear ownership | | |

**View score:** [average] / 4

---

## Part 2 — Practices

| Practice | Score (1–4) | Evidence / notes |
|---|---|---|
| **Architecture Decision Records**: we create ADRs for significant decisions | | |
| **Architecture Runway**: we maintain and prioritise the enabler backlog | | |
| **Fitness Functions**: we protect key architectural characteristics with automated checks | | |
| **Scoping 360**: we align teams on vision before starting delivery | | |
| **Team Topologies**: we consciously design team structure and interaction modes | | |
| **Value Proposition Canvas**: we validate value before building | | |

**Practices score:** [average] / 4

---

## Part 3 — Rituals

| Ritual | Frequency | Quality | Score (1–4) |
|---|---|---|---|
| **Weekly Architecture Meeting**: regular, has agenda, generates decisions | | | |
| **Architecture Kata**: quarterly practice sessions with the team | | | |
| **Peer Review**: architecture decisions reviewed before commitment | | | |
| **Scoping 360**: run at the start of each new product or major feature | | | |
| **Team Autonomy Readiness**: periodic team assessment | | | |

**Rituals score:** [average] / 4

---

## Part 4 — Culture and mindset

| Dimension | Score (1–4) | Evidence / notes |
|---|---|---|
| Architects convince rather than impose | | |
| Emergent design is welcomed, not suppressed | | |
| Architecture is a team activity, not an individual's job | | |
| We make decisions at the last responsible moment | | |
| We are comfortable with "good enough now" over "perfect later" | | |
| ALIGNMENT + AUTONOMY > CONTROL is lived, not just stated | | |

**Culture score:** [average] / 4

---

## Summary scorecard

| Area | Score | Maturity |
|---|---|---|
| Experience Objectives | / 4 | |
| Product | / 4 | |
| Technology | / 4 | |
| Operations | / 4 | |
| Organisation | / 4 | |
| Enterprise Decomposition | / 4 | |
| Practices | / 4 | |
| Rituals | / 4 | |
| Culture | / 4 | |
| **Overall** | **/ 4** | |

**Overall maturity:** Initial (1.0–1.9) / Developing (2.0–2.9) / Defined (3.0–3.4) / Optimising (3.5–4.0)

---

## Improvement roadmap

### Quick wins (score 1 → 2, low effort, high visibility)

Identify the 3 items with score = 1 that can be improved quickly:

| Item | Current score | Action | Effort | Owner | Target date |
|---|---|---|---|---|---|
| | 1 | | S | | |

### Strategic investments (score 2 → 3 or 3 → 4, higher effort, high impact)

Identify the 3 items where improvement will have the biggest impact on delivery:

| Item | Current score | Action | Effort | Owner | Target date |
|---|---|---|---|---|---|
| | 2 | | M | | |

### What to NOT try to fix now

Explicitly identify 2–3 items that are low priority given the current context. Improvement is finite — focus matters.

| Item | Why defer | When to revisit |
|---|---|---|
| | | |

---

## Comparison with previous assessment

If a previous self-assessment exists in the project:

| Area | Previous score | Current score | Change |
|---|---|---|---|
| | | | ↑ / → / ↓ |

If this is the first assessment: "Baseline established. Reassess in 6 months."

---

## Quality gates

- [ ] All 9 areas scored
- [ ] Evidence or notes provided for at least 5 items per section
- [ ] Quick wins list is populated (not left blank)
- [ ] At least 2 items explicitly deferred with rationale
- [ ] If previous assessment exists, trend analysis is included

Save the output to `project/self-assessment-[YYYY-MM-DD].md`.
