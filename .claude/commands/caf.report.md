# CAF Report — Executive Architecture Report

## Context

You are an enterprise architect producing an **Executive Architecture Report** for a non-technical audience.

Project context: $ARGUMENTS

Read ALL available artifacts:
- `project/caf-review-*.md` (most recent — required)
- `project/principles.md`
- `project/architecture-runway.md`
- `technology/fitness-functions.md`
- `organisation/inverse-conway-audit.md`
- `enterprise/operating-unit-map.md`
- Any other artifacts available in the project

If no CAF review exists, run `/caf.review` first.

---

## Objective

Produce a **concise Executive Report** — a 2-page maximum document that communicates the architecture situation to a CTO, Programme Director, or Architecture Review Board.

The report translates architecture findings into business language: risks, investments, decisions needed, and delivery impact. It does not use technical jargon. It uses RAG statuses, plain language, and a clear ask.

---

## Output: `project/executive-report-[YYYY-MM-DD].md`

---

# Architecture Executive Report
**Programme:** [name]
**Date:** [today]
**Prepared by:** [Product Architect / Enterprise Architect]
**Audience:** [CTO / Programme Director / ARB]

---

## Situation in one paragraph

[3–5 sentences answering: where are we, what is working, what is at risk, and what do we need from the audience of this report. Written for a business leader who has 2 minutes to read it.]

---

## Architecture health — at a glance

| Area | Status | Trend | What it means for delivery |
|---|---|---|---|
| User needs (Experience Objectives) | 🟢 / 🟡 / 🔴 | ↑ / → / ↓ | [1 sentence business impact] |
| Product architecture | | | |
| Technology health | | | |
| Operational readiness | | | |
| Team organisation | | | |
| Enterprise structure | | | |

**Legend:** 🟢 On track — 🟡 At risk, managed — 🔴 Blocking, action required

---

## What is working well

Three things the programme is doing well architecturally, stated as business outcomes:

1. **[Strength]** — [1–2 sentences: what this enables for the business]
2. **[Strength]** — [...]
3. **[Strength]** — [...]

---

## Top risks — and what we are doing about them

Present a maximum of 3 risks. Write each as a business risk, not a technical problem.

### Risk 1 — [Name] 🔴 / 🟡

**In plain language:** [What could go wrong, for whom, and when]
**Business impact if unresolved:** [delivery delay / cost / compliance / customer experience]
**What we are doing:** [current mitigation]
**What we need:** [decision, funding, or resource needed from the reader]
**Deadline:** [when the decision is needed to avoid the impact]

### Risk 2 — [Name]

[Same structure]

### Risk 3 — [Name]

[Same structure]

---

## Decisions needed from this audience

Be explicit. The report should generate clear decisions, not vague awareness.

| Decision | Options | Recommendation | Impact of delay | Owner |
|---|---|---|---|---|
| [e.g. Approve investment to decouple Payment domain] | A: Invest now (€X, 3 months) / B: Defer (risk: delivery slowdown in Q3) | A — earlier investment reduces Q3 risk | Feature delivery slows by ~2 sprints per quarter | CTO |
| [e.g. Approve team restructure for Wealth OU] | A: Dedicated team / B: Maintain shared model | A — removes coordination overhead | Ongoing — 20% delivery overhead | Programme Director |

---

## Investment summary

Summarise the architecture investments requested or in progress:

| Investment | Purpose | Size | Timeline | Expected outcome |
|---|---|---|---|---|
| [EN-002: Decouple Order domain] | Remove shared database blocking feature delivery | M (2 sprints) | Q2 | 30% faster feature delivery |
| [Platform team capacity +2] | Reduce cognitive load on stream-aligned teams | Ongoing | From Q3 | Enable 2 new stream-aligned teams |

---

## What happens next

Three concrete next steps with dates:

1. [Action] — [Owner] — [Date]
2. [Action] — [Owner] — [Date]
3. [Action] — [Owner] — [Date]

**Next architecture review:** [date — recommended quarterly]

---

## Appendix — supporting detail

*For readers who want more detail. Not required reading.*

Reference the full artifacts:
- Full CAF cross-view assessment: `project/caf-review-[date].md`
- Architecture debt register: see CAF review section 4
- Fitness function board: `technology/fitness-functions.md`
- Team topology: `organisation/team-design.md`

---

## Quality gates

- [ ] Report is maximum 2 pages (excluding appendix)
- [ ] No unexplained technical acronyms
- [ ] Every 🔴 risk has a "what we need" statement
- [ ] Decisions table has a clear recommendation (not "it depends")
- [ ] Next steps have owners and dates
- [ ] A non-architect reader can understand the report without additional context

Save the output to `project/executive-report-[YYYY-MM-DD].md`.
