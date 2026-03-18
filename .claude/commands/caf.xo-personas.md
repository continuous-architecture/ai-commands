# CAF Experience Objectives — Personas & Experience Map

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** Experience Objectives view.

Project context: $ARGUMENTS

Read the following artifacts:
- `experience-objectives/jtbd.md` ← **required**: JTBD must exist first
- `project/stakeholders.md`
- `enterprise/operating-unit-map.md` (if available)

If `experience-objectives/jtbd.md` does not exist, halt and instruct the user to run `/caf.xo-jtbd` first.

---

## Objective

Produce **Personas and an Experience Map** that make the JTBD analysis tangible for architecture and product decisions.

Personas in the CAF are not marketing tools. They are architecture instruments — they make visible the diversity of user needs that the system must accommodate, and they prevent the "average user" fallacy that produces mediocre systems.

---

## Output: `experience-objectives/personas.md`

### 1. Persona cards

For each Job Performer identified in `experience-objectives/jtbd.md`, produce a persona card.

---

**Persona name:** [A realistic first name + role — e.g. "Sofia, Corporate Treasurer"]
**Linked JTBD:** [job name from jtbd.md]
**Operating Unit / segment:** [from enterprise/operating-unit-map.md if available]

**Profile**
- Role and seniority:
- Organisation type:
- Digital literacy: Low / Medium / High
- Key tools used today:

**Goals** (what success looks like for them)
1.
2.
3.

**Frustrations** (what blocks them today)
1.
2.
3.

**Quote** (a representative statement in their own voice)
> "[...]"

**Architecture sensitivity** — what system characteristics matter most to this persona:
- Performance: [critical / important / low priority]
- Reliability: [critical / important / low priority]
- Usability: [critical / important / low priority]
- Data privacy: [critical / important / low priority]
- Auditability: [critical / important / low priority]

---

Produce one card per distinct Job Performer. Aim for 3–5 personas. Flag if two JTBD performers could be collapsed (same needs, same context).

### 2. Experience map

For the highest-priority persona, produce a full experience map across the stages of their primary JTBD.

Structure as a table:

| Stage | Action | Thought | Feeling | Pain point | Opportunity |
|---|---|---|---|---|---|
| 1. Forecast cash flows | Downloads spreadsheet from ERP | "Is this data up to date?" | Anxious | Manual export, stale data | Real-time cash position API |
| 2. Initiate transaction | Enters payment in banking portal | "Will this clear in time?" | Uncertain | No confirmation of settlement time | Predictive settlement engine |
| ... | | | | | |

For each stage:
- **Action**: what the persona physically does
- **Thought**: what they are thinking (in their voice)
- **Feeling**: emotional state (use a single word)
- **Pain point**: what goes wrong or creates friction today
- **Opportunity**: the architectural or product capability that would resolve it

### 3. Persona-to-architecture matrix

Map each persona's architecture sensitivities to specific system quality attributes:

| Persona | Top sensitivity | Implied non-functional requirement | Fitness function candidate |
|---|---|---|---|
| Sofia, Corporate Treasurer | Reliability | 99.9% uptime during business hours | Availability monitor — alert if SLA breached |
| Marco, Branch Advisor | Usability | Response time < 2s for customer lookup | Latency test in CI pipeline |

Feed the "Fitness function candidate" column into `/caf.tech-fitness`.

### 4. Segment architecture implications

Based on the personas, what architectural decisions does the diversity of users require?

| Decision needed | Driven by | Options | Recommendation |
|---|---|---|---|
| Multi-language support | International persona | i18n framework vs multiple builds | i18n framework — single codebase |
| Offline mode | Low-connectivity persona | PWA vs native app | PWA — lower maintenance cost |

### 5. Next steps

- [ ] Validate personas with actual users or domain experts
- [ ] Feed experience map opportunities into `project/architecture-runway.md` as enablers
- [ ] Feed fitness function candidates into `/caf.tech-fitness`
- [ ] Cross-reference persona segments with OU boundaries in `enterprise/operating-unit-map.md`

---

## Quality gates

- [ ] One persona per Job Performer in jtbd.md
- [ ] Every persona has explicit architecture sensitivities
- [ ] Experience map covers all stages of the primary JTBD
- [ ] Pain points and opportunities are specific (not generic)
- [ ] At least 2 fitness function candidates are identified

Save the output to `experience-objectives/personas.md`.
