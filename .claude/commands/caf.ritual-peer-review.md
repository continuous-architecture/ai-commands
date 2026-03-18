# CAF Ritual — Architecture Peer Review

## Context

You are an enterprise architect requesting, preparing, or documenting an **Architecture Peer Review** — the CAF ritual for getting external feedback on an architecture decision or design before it is committed.

Artefact to review: $ARGUMENTS

Read the artefact being reviewed (ADR, design document, or other) plus:
- `project/principles.md`
- `technology/fitness-functions.md` (if available)

---

## Objective

Produce a **Peer Review Package** — either the preparation materials (request) or the documented feedback (outcome).

In the CAF, the Peer Review is the mechanism for building consensus on significant architecture decisions. It prevents the ivory-tower architecture trap: architects convince through dialogue, not imposition. The review is not a veto process — it is a structured conversation that improves the decision.

---

## Output: `rituals/peer-review-[topic]-[date].md`

### Part A — Review request (author fills before the session)

#### 1. What is being reviewed

**Artefact:** [ADR number + title, or design document name]
**Author(s):** [names / roles]
**Requested reviewers:** [names / roles — aim for 3–5 people with diverse perspectives]
**Review deadline:** [date]
**Review format:** Async (written comments) | Synchronous (1-hour meeting) | Hybrid

#### 2. Context (2 minutes to read)

[1–2 paragraphs: the problem being solved, the decision made, and why this decision was brought to peer review rather than decided unilaterally.]

#### 3. What the author wants from reviewers

Be specific — vague review requests get vague feedback.

- [ ] **Validate**: Does the reasoning hold? Are the options complete?
- [ ] **Challenge**: Is there a better option we haven't considered?
- [ ] **Risk check**: What could go wrong that we haven't anticipated?
- [ ] **Principle alignment**: Does this align with `project/principles.md`?
- [ ] **Cross-team impact**: Does this create problems for other teams not represented?
- [ ] **Completeness**: Is there a gap in the consequences section?

#### 4. Key decisions being made

List the 2–3 most important choices in the artefact so reviewers focus there:

1. [e.g. "We chose event-driven over synchronous API — is this right?"]
2. [e.g. "We are accepting a Shared Kernel with Team B — are the risks understood?"]
3. [e.g. "We deferred the data migration — is this acceptable?"]

#### 5. What the author is NOT asking for

Helps prevent scope creep in the review:
- [e.g. "Not asking for a review of the business requirements — those are fixed"]
- [e.g. "Not asking for a review of the team topology — that's covered by a separate process"]

---

### Part B — Review feedback (reviewers fill; facilitator compiles)

#### 6. Feedback register

For each reviewer, capture their feedback:

**Reviewer:** [name / role]
**Overall assessment:** Approve | Approve with conditions | Request changes | Reject

| Point | Type | Specific comment | Suggested change | Author response |
|---|---|---|---|---|
| [e.g. Risk of Shared Kernel underestimated] | Risk | "The ADR doesn't address how conflicts between teams will be resolved" | "Add a conflict resolution protocol to the consequences section" | [to be filled by author] |
| [e.g. Option C not considered] | Gap | "Have you considered an anticorruption layer instead?" | | |

Types: Risk | Gap | Validation (positive) | Question | Out of scope

#### 7. Consensus summary

After all feedback is collected:

**Points of agreement across reviewers:**
- [...]

**Points of disagreement** (these are the most valuable):
- [e.g. "2 reviewers think the Shared Kernel risk is acceptable; 1 thinks it's critical — record the dissent"]

**Unresolved questions** (need follow-up before approval):
- [question] — Owner: [name] — Due: [date]

#### 8. Decision

**Outcome:** Approved | Approved with conditions | Revised and re-submitted | Rejected

**Conditions (if applicable):**
- [condition 1] — resolved by: [date]
- [condition 2]

**Changes made to the artefact as a result of the review:**
- [change 1]
- [change 2]

#### 9. Dissent log

CAF explicitly values recorded dissent. If a reviewer disagreed with the final decision, document it:

**Dissenting reviewer:** [name / role]
**Position:** [their view, in 1–2 sentences]
**Acknowledgement:** The team heard and considered this view. It was outweighed by [rationale].

This is not a failure of the process — it is intellectual honesty.

#### 10. Next steps

- [ ] Update the reviewed artefact with changes
- [ ] Resolve any conditions before the stated deadline
- [ ] Communicate the decision to affected teams
- [ ] If significant changes were made: consider a second review

---

## Quality gates

- [ ] Review request clearly states what feedback is wanted
- [ ] At least 3 reviewers with different perspectives
- [ ] Every reviewer's feedback is captured in the register
- [ ] Points of disagreement are documented (not smoothed over)
- [ ] Dissent log is completed if any reviewer disagreed with the outcome
- [ ] Changes made to the artefact are documented

Save the output to `rituals/peer-review-[topic]-[YYYY-MM-DD].md`.
