# CAF Product — Scoping 360

## Context

You are an enterprise architect facilitating a **Scoping 360** — the CAF practice for assembling a team aligned on a vision and ready to deliver.

Project context: $ARGUMENTS

Read all available artifacts:
- `project/stakeholders.md`
- `project/requirements.md`
- `experience-objectives/jtbd.md`
- `experience-objectives/personas.md`
- `enterprise/operating-unit-map.md`
- `organisation/team-design.md`

---

## Objective

Produce a **Scoping 360 Document** — the complete alignment artefact that a new product team uses to get up to speed and start delivering.

The Scoping 360 is not a spec. It is a structured conversation guide that covers: why (problem / vision), what (product scope), who (team and stakeholders), how (architecture and technical approach), and when (delivery plan).

---

## Output: `product/scoping-360.md`

### 1. Problem framing (Why)

Synthesise from JTBD and requirements:

**Problem statement** (one paragraph, written for a non-technical audience):
> [The problem we are solving, for whom, and why it matters now]

**Success criteria** — how will we know the product is solving the problem?

| Criterion | Measurement | Target | Timeframe |
|---|---|---|---|
| [e.g. Treasurer completes cash forecast in < 10 min] | Task completion time | 10 min | 3 months post-launch |

**Non-goals** — what is explicitly out of scope for this product:
- [Out of scope item 1]
- [Out of scope item 2]

### 2. Product vision (What)

**Elevator pitch** (max 3 sentences):
> For [target user], [product name] is a [product category] that [key benefit]. Unlike [current alternative], our product [key differentiator].

**Product boundaries:**
- In scope: [list of capabilities included]
- Out of scope: [list of capabilities excluded]
- Adjacent: [capabilities that interact but are owned by other teams]

**Lifecycle stage:** Ideation | Alpha | Beta | Growth | Maturity

### 3. Stakeholders and team (Who)

**Stakeholder map:**

| Stakeholder | Role | Interest | Influence | Engagement mode |
|---|---|---|---|---|
| [Name / role] | Product sponsor | Business outcome | High | Monthly steering |
| [Name / role] | End user representative | Usability | Medium | Sprint review |
| [Name / role] | Platform team | Technical dependency | High | Weekly sync |

**Product team composition** (cross-functional, self-organised):

| Role | Name / TBD | % allocation | Key responsibility |
|---|---|---|---|
| Product Owner | | 100% | Backlog prioritisation, user feedback |
| Product Architect | | 50% | Architecture runway, ADRs, fitness functions |
| Lead Engineer | | 100% | Technical delivery, emerging design |
| [Other roles] | | | |

Reference `organisation/team-design.md` if available.

### 4. Architecture approach (How)

**Architecture style:** [Monolith / Modular monolith / Microservices / Event-driven / Hybrid]
**Rationale:** [1–2 sentences — why this style for this product at this stage]

**Key architecture decisions already made:**

| Decision | ADR | Status |
|---|---|---|
| [e.g. Event-driven for order domain] | ADR-001 | Accepted |

**Key decisions still open:**

| Decision | Options under consideration | Target date |
|---|---|---|
| [e.g. API gateway selection] | Kong vs AWS API Gateway | Sprint 3 |

**Dependencies on other teams / platforms:**

| Dependency | Provider team | Nature | Risk |
|---|---|---|---|
| Customer identity | Platform team | X-as-a-Service | Low — stable API |
| Payment execution | Payment Factory | X-as-a-Service | Medium — SLA not yet defined |

### 5. Architecture workshop output

Produce a mini architecture runway for the product (seed for `project/architecture-runway.md`):

**Top 3 architectural risks:**
1.
2.
3.

**First 3 enablers to add to the backlog:**

| Enabler | Why needed | Priority | Effort |
|---|---|---|---|
| | | | |

### 6. Delivery plan (When)

**Milestones:**

| Milestone | Description | Target date | Key dependency |
|---|---|---|---|
| Alpha | First working version with core JTBD supported | | |
| Beta | Full feature set, limited audience | | |
| Live | General availability | | |

**First sprint goal:**
> [One sentence: what will the team have built and validated by the end of sprint 1?]

### 7. Team agreements

Document the working agreements the team makes during the scoping session:

**Architecture governance:**
- ADRs will be reviewed in: [Weekly Architecture Meeting / Peer Review]
- Architecture runway will be reviewed: [frequency]
- Fitness functions will be monitored: [frequency and by whom]

**Definition of Done** (include architecture elements):
- [ ] Code reviewed and merged
- [ ] Unit tests passing
- [ ] Fitness functions passing in CI
- [ ] ADR created for any significant technical decision
- [ ] Documentation updated

### 8. Next steps

- [ ] Finalise team composition and allocation
- [ ] Run `/caf.product-runway` to build the full architecture runway
- [ ] Create first ADR for the most critical open decision via `/caf.product-adr`
- [ ] Schedule first Weekly Architecture Meeting
- [ ] Run `/caf.tech-fitness` to formalise fitness functions

---

## Quality gates

- [ ] Problem statement is written for a non-technical audience
- [ ] Non-goals are explicitly stated
- [ ] Every open architecture decision has a target date
- [ ] Dependencies on other teams are listed with risk assessment
- [ ] First sprint goal is stated
- [ ] Team agreements include architecture governance

Save the output to `product/scoping-360.md`.
