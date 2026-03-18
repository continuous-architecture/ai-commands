# CAF Technology — Fitness Functions

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** Fitness Functions practice.

Project context: $ARGUMENTS

Read available artifacts:
- `project/principles.md`
- `project/architecture-runway.md`
- `technology/tech-principles.md` (if available — provides gap analysis)
- `experience-objectives/personas.md` (if available — provides NFR signals)

---

## Objective

Produce a **Fitness Functions Register** — the set of measurable checks that protect architectural characteristics over time.

In the CAF, fitness functions are the mechanism by which architects embed their intentions into the delivery pipeline. They make architectural degradation visible before it reaches production.

A fitness function answers 3 questions: what to measure, how to measure it, when to measure it.

The CAF recommends starting with 3 fitness functions and growing to 5–6 as the team matures. More than 6 is noise.

---

## Output: `technology/fitness-functions.md`

### 1. Architectural characteristics to protect

Before defining fitness functions, identify which architectural characteristics are critical for this product. Select from this list (add others as needed):

| Characteristic | Priority for this product | Rationale |
|---|---|---|
| Performance (latency) | High / Medium / Low | |
| Scalability | | |
| Reliability / availability | | |
| Security | | |
| Maintainability (coupling, complexity) | | |
| Deployability (pipeline speed) | | |
| Data consistency | | |
| Compliance / auditability | | |
| Accessibility | | |

Select the **top 3–6** characteristics to protect. Document the selection rationale.

### 2. Fitness function definitions

For each selected characteristic, define 1–2 fitness functions.

Use this template per function:

---

**FF-[NNN] — [Short name]**

| Field | Value |
|---|---|
| **Characteristic protected** | [e.g. Performance] |
| **Type** | Atomic / Holistic |
| **Trigger** | Triggered / Continual |
| **Nature** | Static / Dynamic |
| **Automation** | Automated / Manual |
| **What to measure** | [Precise metric — e.g. "p95 API response time for /orders endpoint"] |
| **Baseline** | [Current measured value, or "unknown — measure in sprint N"] |
| **Target** | [Acceptable value — e.g. "< 500ms"] |
| **Failure threshold** | [Value that triggers action — e.g. "> 800ms for 3 consecutive minutes"] |
| **How to measure** | [Tool / method — e.g. "k6 load test in CI pipeline", "Datadog monitor", "ArchUnit test"] |
| **When to measure** | [e.g. "Every PR merge", "Every deployment", "Continuously in production"] |
| **Owner** | [Role or team responsible for keeping this function healthy] |
| **Action on failure** | [What happens when threshold is breached — e.g. "Build fails", "Alert to #arch-alerts Slack", "PagerDuty P2"] |

---

Define at minimum 3 fitness functions. Flag each one's implementation readiness:
- **Ready**: tooling in place, can be activated immediately
- **Needs tooling**: tool exists but not configured
- **Needs PoC**: approach unclear, spike needed first

### 3. Fitness function board

Produce a summary board — this is the artefact the team reviews every week:

| ID | Name | Characteristic | Status | Last measured | Trend | Action needed |
|---|---|---|---|---|---|---|
| FF-001 | API latency p95 | Performance | Passing | [date] | Stable | None |
| FF-002 | Cross-domain coupling | Maintainability | Failing | [date] | Degrading | EN-004: Decouple Order service |
| FF-003 | Deployment pipeline < 15min | Deployability | Warning | [date] | Stable | Investigate test suite speed |

Status: Passing / Warning / Failing / Not yet active
Trend: Improving / Stable / Degrading / Unknown

### 4. Implementation roadmap

For functions that are not yet active, plan their activation:

| FF | Readiness | What's needed | Sprint target |
|---|---|---|---|
| FF-001 | Needs tooling | Configure k6 in CI | Sprint 3 |
| FF-002 | Needs PoC | Evaluate ArchUnit for Java | Sprint 4 |

### 5. Connection to architecture runway

For each fitness function, ensure it appears as an enabler in `project/architecture-runway.md`:

| FF | Linked enabler | Status |
|---|---|---|
| FF-001 | EN-002: Set up performance testing | In backlog |
| FF-002 | EN-005: Enforce domain boundary tests | New — add to runway |

### 6. Next steps

- [ ] Activate Ready functions immediately
- [ ] Add "Needs tooling" items to the architecture runway
- [ ] Schedule weekly fitness function board review (15 min in Weekly Architecture Meeting)
- [ ] Review function set at next architecture runway cycle (recommended: every PI or 3 months)

---

## Quality gates

- [ ] At least 3 fitness functions defined
- [ ] No more than 6 (flag if team is taking on too many)
- [ ] Every function has a measurable threshold (not vague like "good performance")
- [ ] Every function has an owner
- [ ] Every failing function has a linked action or enabler
- [ ] Board is ready to be presented in a Weekly Architecture Meeting

Save the output to `technology/fitness-functions.md`.
