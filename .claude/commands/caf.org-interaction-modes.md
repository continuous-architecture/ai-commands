# CAF Organisation — Interaction Modes & Team API

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** Organisation view.

Project context: $ARGUMENTS

Read the following artifacts before starting:
- `organisation/team-design.md` ← **required**: team structure must exist first
- `project/requirements.md`
- `project/principles.md`

If `organisation/team-design.md` does not exist, halt and instruct the user to run `/arckit.caf-team-design` first.

---

## Objective

Produce an **Interaction Modes & Team API Document** that formalises how teams collaborate in a large-group IS context. This document is the operational contract between teams — it prevents implicit coupling and Conway's Law accidents.

---

## Output: `organisation/interaction-modes.md`

### 1. Interaction Mode Register

For every team-to-team interaction identified in `organisation/team-design.md`, produce a full entry:

#### Template per interaction

**Interaction ID:** IM-XXX
**From team:** [name]
**To team:** [name]
**Mode:** Collaboration | X-as-a-Service | Facilitating
**Duration:** [time-boxed for Collaboration / ongoing for XaaS / campaign for Facilitating]
**Trigger:** What initiates this interaction?
**Expected outcome:** What does the consuming team receive?
**Interface contract:** API endpoint / event topic / shared service / knowledge transfer artefact
**Escalation path:** Who resolves disputes or SLA breaches?
**Review date:** When will this mode be reassessed?

---

### 2. Team API Cards

For each **Platform** and **Enabling** team, produce a Team API card:

#### Template — Team API Card

```
Team: [name]
Type: Platform | Enabling
Mission: [one sentence]

WHAT WE PROVIDE
---------------
Service / Capability    | SLA / Availability  | Interface
------------------------|---------------------|-------------------
[e.g. Identity service] | 99.9% / 24x7        | REST API + SDK
[e.g. CI/CD pipeline]   | Best effort         | GitHub Actions

WHAT WE NEED FROM YOU
----------------------
Input / Artefact        | Frequency           | Format
------------------------|---------------------|-------------------
[e.g. Release schedule] | Sprint -2           | Confluence page

ENGAGEMENT MODEL
----------------
For new requests:   [e.g. raise Jira ticket in PLAT project]
For incidents:      [e.g. Slack #platform-incidents, P1 = 15min SLA]
For roadmap input:  [e.g. quarterly platform forum]

THINGS WE DON'T DO
------------------
[List explicit out-of-scope items to prevent scope creep]
```

---

### 3. Collaboration Radar

Produce a summary table assessing the health of each interaction mode:

| Interaction ID | Mode | Risk of coupling drift | Risk of under-collaboration | Recommended action |
|---|---|---|---|---|
| IM-001 | XaaS | Low | Medium | Quarterly API review |
| IM-002 | Collaboration | High | Low | Time-box to 6 sprints max |
| ... | | | | |

Flag any interaction where:
- Collaboration mode has no defined end date (→ coupling risk)
- XaaS has no SLA defined (→ invisible dependency risk)
- Two Stream-aligned teams interact directly without Platform mediation (→ assess if warranted)

### 4. Conway's Law Alignment Check

For each interaction:
- Does the team boundary reflect the system's module boundary?
- Is there a mismatch that will generate implicit coupling in the codebase?
- Recommend architecture changes OR team structure changes to correct mismatches

Present as a short table:

| Interaction | System boundary matches? | Risk | Recommended adjustment |
|---|---|---|---|

### 5. Transition Plan (for large groups with existing team structures)

If the project involves reorganising existing teams:
- Current state: describe existing team topology (if inferable from artifacts)
- Target state: proposed topology from `team-design.md`
- Transition steps: phased approach to avoid delivery disruption
- Decision points: what triggers moving to next phase?

### 6. Links to CAF Rituals

Map each interaction mode to the relevant CAF ritual:

| CAF Ritual | Relevant teams | Cadence |
|---|---|---|
| Architecture Kata | All Stream-aligned teams | Per quarter |
| Weekly Architecture Meeting | Tech leads of all teams | Weekly |
| Architecture Peer Review | Stream-aligned → Platform | Per major feature |
| Team Autonomy Readiness | Each team individually | Per 6 months |

---

## Quality Gates

Before saving, verify:
- [ ] Every team-to-team dependency in `team-design.md` has a corresponding IM entry
- [ ] Every Platform and Enabling team has a Team API card
- [ ] No Collaboration mode is open-ended (all have duration or review date)
- [ ] Conway's Law alignment check is completed for at least the highest-risk interactions

Save the output to `organisation/interaction-modes.md`.
