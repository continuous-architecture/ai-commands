# CAF Experience Objectives — Jobs-To-Be-Done Analysis

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** Experience Objectives view.

Project context: $ARGUMENTS

Read available artifacts:
- `project/stakeholders.md`
- `project/requirements.md`
- `enterprise/operating-unit-map.md` (if available — provides customer segment signals)

---

## Objective

Produce a **Jobs-To-Be-Done Analysis** using the CAF Experience Objectives template.

The CAF uses JTBD combined with Design Thinking to understand what customers want *before* defining what to build. As Theodore Levitt observed: understanding the customer should come first, designing the product should follow.

A JTBD is not a feature list. It describes the progress a customer is trying to make in a given circumstance — independent of any solution.

---

## Output: `experience-objectives/jtbd.md`

For each distinct customer segment or job performer identified, produce a complete JTBD entry using the CAF template.

---

### JTBD Entry Template

**Job name:** [A verb phrase — e.g. "Move money", "Onboard a new employee", "Assess credit risk"]

#### Job Performer — Who
The person doing the main job (the end user, not the buyer).
- Role / title:
- Context: what situation are they in when this job arises?
- Level of expertise: novice / intermediate / expert
- Key constraint: what limits their ability to get the job done today?

#### Jobs — What
- **Main job:** The core functional outcome the performer wants to achieve
- **Related jobs:** Adjacent jobs triggered by or enabling the main job
- **Emotional job:** How the performer wants to feel (or avoid feeling) while doing the job
- **Social job:** How the performer wants to be perceived by others while doing the job

#### Stages — How
The steps the performer goes through to get the job done. Use a numbered list. For each stage, note the current pain point if known.

1. [Stage] — pain: [what goes wrong today]
2. [Stage] — pain: [...]
3. ...

#### Needs — Why
The desired outcomes the performer wants to achieve during the process. Frame as "verb + object + context":
- Minimise the time needed to [...]
- Reduce the risk of [...]
- Increase confidence that [...]
- Avoid the situation where [...]

Aim for 4–6 needs per JTBD.

#### Circumstances — When / Where
The context that shapes how the job is done:
- Frequency: how often does this job arise?
- Variability: does the job change significantly by segment, geography, or market?
- Stakes: what happens if the job is done poorly?
- Regulatory or compliance constraints:

---

### Synthesis

After all JTBD entries, produce:

**1. Job map summary**

| Job name | Performer | Main stage count | Top pain point | Priority |
|---|---|---|---|---|

**2. Market segmentation signals**

Based on the JTBD analysis, what customer segment distinctions does the architecture need to support? Feed this into `enterprise/operating-unit-map.md`.

**3. Architecture implications**

For each JTBD, list the architectural capabilities required:

| Job | Required capability | Build / Buy / Reuse | Notes |
|---|---|---|---|

**4. Design Thinking next steps**

- [ ] Validate JTBD hypotheses with user research (interviews, observation)
- [ ] Build prototypes for the highest-priority stages
- [ ] Cross-reference with `/caf.xo-personas` to map performers to personas
- [ ] Feed segment findings into `/caf.ed-operating-unit-map`

---

## Quality gates

- [ ] At least one JTBD per major customer segment identified in stakeholders.md
- [ ] Every JTBD has at least 4 stages and 4 needs
- [ ] Emotional and social jobs are explicit (not left blank)
- [ ] Architecture implications table is populated
- [ ] Market segmentation signals are stated

Save the output to `experience-objectives/jtbd.md`.
