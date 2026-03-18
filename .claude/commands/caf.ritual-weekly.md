# CAF Ritual — Weekly Architecture Meeting

## Context

You are an enterprise architect preparing or documenting a **Weekly Architecture Meeting** — the CAF recurring ritual for collective architecture governance at the team level.

Meeting context: $ARGUMENTS

Read available artifacts to populate the agenda:
- `technology/fitness-functions.md` — check function status
- `project/architecture-runway.md` — check enabler progress
- `technology/adrs/README.md` — check pending decisions
- Any files modified in the last 7 days (signals of active work)

---

## Objective

Produce a **Weekly Architecture Meeting Package** — either the agenda (prepare before) or the minutes (document after).

In the CAF, the Weekly Architecture Meeting is the heartbeat of collective architecture practice. It is the primary venue for: reviewing fitness function health, progressing pending ADRs, unblocking architecture decisions, and maintaining the runway. It is NOT a status meeting — it is a working session.

**Duration:** 45–60 minutes
**Participants:** All engineers on the team + Product Architect (mandatory) + Product Owner (optional, for backlog alignment)
**Cadence:** Weekly, fixed slot

---

## Output: `rituals/weekly-arch-[YYYY-MM-DD].md`

### Part A — Agenda (prepare 24h before)

#### 1. Standing items (15 min)

**Fitness function board review**
Read `technology/fitness-functions.md` and produce the current board snapshot:

| FF | Name | Status | Trend | Action needed |
|---|---|---|---|---|
| FF-001 | [name] | Passing / Warning / Failing | Stable / Improving / Degrading | |

Flag any Failing or newly Warning function — this is the first priority of the meeting.

**Architecture runway check**
Read `project/architecture-runway.md` and list:
- Enablers in progress this sprint: [list]
- Enablers blocked or at risk: [list — these get meeting time]
- New items to add to the runway: [if any emerged this week]

**Pending ADRs**
Read `technology/adrs/README.md`:
- ADRs in Proposed status: [list — any older than 2 weeks need action]

#### 2. Main topics (20–30 min)

Based on the standing items, identify 1–3 topics that need working discussion. For each:

**Topic [N]: [Title]**
- Context: [2 sentences — what's the situation]
- Question to answer: [the specific decision or unblocking needed]
- Time allocated: [X min]
- Facilitator: [name / role]
- Pre-read: [link to ADR, design doc, or other artefact if applicable]

#### 3. Emerging design space (10 min)

Time for engineers to bring up architectural observations from the week:
- "I noticed that [observation] — should we do something about it?"
- "I built X this way — does anyone see a risk?"
- "I'm about to build Y — any architecture input before I start?"

This is the intentional architecture ↔ emergent design dialog zone. Facilitate it explicitly.

#### 4. Upcoming (5 min)

- What architecture work is planned for next week?
- Any reviews, katas, or scoping sessions coming up?
- Any external dependencies to flag?

---

### Part B — Minutes (fill during/after the meeting)

#### 5. Attendance

| Name | Role | Present |
|---|---|---|

#### 6. Fitness function review outcome

| FF | Status change | Action taken |
|---|---|---|
| FF-002 | Warning → Failing | Opened blocker ticket, assigned to [name], target: Sprint N+1 |

#### 7. Decisions made

| Decision | Context | Owner | ADR needed? |
|---|---|---|---|
| [e.g. Adopt k6 for performance testing] | FF-001 tooling | [name] | Yes — `/caf.product-adr k6 adoption` |
| [e.g. Defer database migration to Q3] | Runway re-prioritisation | Product Owner | No — noted in runway |

#### 8. Actions

| Action | Owner | Due date |
|---|---|---|
| Create ADR for k6 adoption | [name] | [date] |
| Update EN-002 status in runway | [name] | Next meeting |
| Prepare kata brief on event sourcing | [name] | [date] |

#### 9. Emerging design observations

Document any emergent design signals raised by engineers:

| Observation | Raised by | Action |
|---|---|---|
| [e.g. "Noticed we have 3 different patterns for error handling across services"] | [engineer] | Add to next kata agenda |

#### 10. Next meeting

**Date:** [next week, same slot]
**Pre-reads:** [list any artefacts to review before next meeting]
**Topics carried forward:** [any items not completed this week]

---

## Quality gates (for the meeting itself)

- [ ] Fitness function board reviewed at every meeting — no exceptions
- [ ] Architecture runway checked — blockers identified
- [ ] No meeting ends without explicit action owners and due dates
- [ ] Emerging design space is given time (not cut for time pressure)
- [ ] Minutes are published within 24h of the meeting

Save the output to `rituals/weekly-arch-[YYYY-MM-DD].md`.
