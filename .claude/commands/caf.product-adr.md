# CAF Product — Architecture Decision Record (ADR)

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** ADR practice.

Decision to document: $ARGUMENTS

Read available artifacts:
- `project/principles.md` — check alignment with principles
- `project/architecture-runway.md` — check if this decision relates to an enabler
- Existing ADRs in `technology/adrs/` — check for conflicts or dependencies

---

## Objective

Produce a **CAF Architecture Decision Record** following the full 5-step process: trigger → document → consensus → review → approve.

The CAF ADR practice is grounded in two principles: wait for the last responsible moment to decide, and spend time proportional to the impact of a bad decision (Yip's quadrant). An ADR should be created when the cost of change or rework would be significant.

---

## Output: `technology/adrs/ADR-[NNN]-[short-title].md`

Determine the ADR number by checking existing files in `technology/adrs/`. Use the next available number (ADR-001 if none exist).

The short title should be a 3–5 word kebab-case summary: e.g. `event-driven-order-domain`, `api-gateway-selection`, `customer-identity-shared-kernel`.

---

```markdown
# ADR-[NNN] — [Full decision title]

**Status:** Proposed | Accepted | Superseded | Deprecated
**Date:** [today]
**Deciders:** [names or roles of people involved in this decision]
**Linked enabler:** [EN-XXX from architecture-runway.md, or N/A]
**Linked principle:** [principle number from project/principles.md, or N/A]

---

## Context and problem statement

[2–4 paragraphs describing:]
- The situation that triggered this decision
- Why a decision is needed now (last responsible moment reasoning)
- The constraints that apply (technical, organisational, regulatory)
- What happens if no decision is made

## Decision drivers

List the criteria used to evaluate options. Be explicit — these become the basis for consensus.

- [Driver 1: e.g. "Must support 10,000 concurrent users"]
- [Driver 2: e.g. "Must align with the company's Adopt-level tech radar items"]
- [Driver 3: e.g. "Must be operable by a team of 4 engineers"]
- [...]

## Options considered

### Option A — [Name]

**Description:** [2–3 sentences]

| Driver | Assessment | Evidence |
|---|---|---|
| Driver 1 | Meets / Partially meets / Does not meet | [proof or assumption] |
| Driver 2 | | |
| Driver 3 | | |

**Pros:** [list]
**Cons:** [list]
**PoC needed?** Yes / No — [rationale]

### Option B — [Name]

[Same structure]

### Option C — [Name] (if applicable)

[Same structure]

## Decision

**Chosen option: Option [X] — [Name]**

[2–3 sentences explaining why this option was selected over the others, referencing the decision drivers explicitly.]

**Impact on architecture principles:**
- Principle [N]: [Supports / Neutral / Tension — explain]

## Consequences

**Positive:**
- [What becomes easier or possible]
- [...]

**Negative / trade-offs:**
- [What becomes harder or is given up]
- [...]

**Risks:**
- [Risk 1] — Mitigation: [...]
- [Risk 2] — Mitigation: [...]

## Implementation notes

[Optional: key technical details, migration steps, or constraints the implementing team must know.]

## Consensus and review

**Review method:** Weekly Architecture Meeting | Peer Review | Architecture Kata | CTO sign-off
**Review date:** [date]
**Reviewers:** [names or roles]
**Outcome:** [summary of feedback received and how it was addressed]

## Communication

**Audiences to notify:**
- [ ] Product team(s): [which teams, and what they need to know]
- [ ] Platform team: [if infrastructure impact]
- [ ] Enterprise architecture: [if cross-programme impact]
- [ ] Security / compliance: [if regulatory impact]

**Communication artefact needed?** Yes — [describe format] | No

## Links

- Supersedes: [ADR-XXX, or N/A]
- Superseded by: [ADR-XXX, or N/A — fill if this ADR is later superseded]
- Related: [ADR-XXX, enabler EN-XXX, requirement REQ-XXX]
```

---

## After creating the ADR

1. Add an entry to the ADR index (create `technology/adrs/README.md` if it doesn't exist):

```markdown
| ADR | Title | Status | Date |
|---|---|---|---|
| ADR-001 | [title] | Accepted | [date] |
```

2. If the decision resolves an enabler in `project/architecture-runway.md`, mark the enabler as resolved.

3. If a PoC is needed, create a technical spike entry in `project/architecture-runway.md`.

---

## Quality gates

- [ ] Decision drivers are explicit and measurable
- [ ] At least 2 options were considered
- [ ] Consequences include both positive and negative
- [ ] At least one risk with mitigation is stated
- [ ] Communication plan identifies all impacted audiences
- [ ] ADR index is updated

Save the ADR to `technology/adrs/ADR-[NNN]-[short-title].md`.
