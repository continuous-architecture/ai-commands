# CAF Product — Architecture Runway

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** Architecture Runway practice.

Project context: $ARGUMENTS

Read all available artifacts:
- `project/principles.md`
- `project/requirements.md`
- `experience-objectives/jtbd.md` (if available)
- `technology/fitness-functions.md` (if available)
- `enterprise/domain-map.md` (if available)

---

## Objective

Produce an **Architecture Runway** — the backlog of technical enablers needed to support near-term product features without excessive redesign.

The CAF runway is the dialog zone between intentional architecture (what architects propose) and emergent design (what teams discover). It is not a constraint document — it is a conversation starter that architects use to convince rather than impose.

The runway has 5 steps: collect intentional inputs → analyse backlog → define technology framework → identify enablers → consolidate into product backlog.

---

## Output: `project/architecture-runway.md`

### 1. Intentional inputs

Summarise the architectural intentions that constrain or guide the product:

**Business ambitions**
- What are the top 3 product objectives for the next 6–12 months? (infer from requirements.md or context)

**Organisational standards**
- Reference architecture constraints: [list any known technology standards]
- Forbidden technologies: [list if known]
- Mandatory compliance frameworks: [e.g. GDPR, PCI-DSS, SOC2]

**Tech radar snapshot** (populate from project context)

| Item | Category | Status | Notes |
|---|---|---|---|
| Kafka | Platform | Adopt | Standard for event-driven architecture |
| GraphQL | Technique | Trial | Assess for internal APIs |
| [technology] | [Tools / Languages / Techniques / Platforms] | [Assess / Trial / Adopt / Hold] | |

Add at least 5 items based on the project context. For each "Hold" item, explain the risk.

### 2. Backlog analysis

Identify the user stories or features in the current product backlog that have significant architecture implications.

For each architecturally significant item:

| Backlog item | Architecture concern | Impact if not addressed | Sprint / MVP target |
|---|---|---|---|
| [Feature X] | Requires new data model | Delivery blocked | MVP 2 |
| [Feature Y] | Cross-domain API contract | Integration risk | Sprint 8 |

Flag any item where the architecture concern is not yet resolved as a blocker.

### 3. Fitness functions identified

List the architectural characteristics that must be preserved as the product evolves. For each:

| Characteristic | Why protect it | Measurement | Threshold | Automation |
|---|---|---|---|---|
| API latency | User experience | p95 response time | < 500ms | CI pipeline test |
| Coupling | Maintainability | Number of cross-domain calls | < 3 per feature | Architecture test |

Feed this table into `technology/fitness-functions.md` via `/caf.tech-fitness`.

### 4. Enablers backlog

Combine the backlog analysis and fitness functions to produce the enabler list. Classify and prioritise each:

| ID | Enabler | Type | Linked feature | Priority | Effort | Sprint target |
|---|---|---|---|---|---|---|
| EN-001 | Define event schema for Order domain | Technical spike | Feature X, Y | High | S | Sprint 5 |
| EN-002 | Extract Customer service from monolith | Implementation | Feature Z | High | L | MVP 2 |
| EN-003 | Set up API gateway | Infrastructure | All external APIs | Medium | M | Sprint 7 |

Enabler types: Technical spike (PoC / decision research) | Implementation (build the enabler) | Refactoring (reduce debt) | Infrastructure (platform / tooling)

Priority: High (blocks near-term delivery) | Medium (needed within 2 MVPs) | Low (strategic, deferred)
Effort: S < 1 sprint | M 1–3 sprints | L programme-level

**Minimum 5 enablers.** If fewer than 5 can be identified, flag that the backlog analysis is incomplete.

### 5. Consolidated roadmap view

Show how enablers and features interleave across the next 3 MVPs or quarters:

| Sprint / MVP | Business features | Architecture enablers | Fitness function added |
|---|---|---|---|
| Sprint 5–6 | Feature A | EN-001: Event schema | API latency monitor |
| MVP 2 | Feature B, C | EN-002: Customer service | Coupling test |
| MVP 3 | Feature D | EN-003: API gateway | Security scan |

### 6. Communication kit

Produce a one-page summary suitable for sharing with stakeholders and other teams:

**Runway summary — [Product name]**
- Horizon: [timeframe]
- Key architectural bets: [2–3 sentences on the major technical choices being made]
- Top enablers: [list EN-001, EN-002, EN-003 with one-line descriptions]
- Risks if enablers are deprioritised: [be explicit — "Feature X will be delayed by N sprints"]
- Next runway review: [recommended date — align with SAFe PI boundary or 3-month cycle]

### 7. Next steps

- [ ] Present enabler priorities to product owner — negotiate backlog slots
- [ ] Create ADRs for each "Adopt" decision on the tech radar via `/caf.practice-adr`
- [ ] Schedule runway review (recommended: every PI or every 3 months)
- [ ] Run `/caf.tech-fitness` to formalise fitness functions

---

## Quality gates

- [ ] Tech radar has at least 5 items with statuses
- [ ] At least 5 enablers identified and prioritised
- [ ] Every High-priority enabler has a sprint target
- [ ] Fitness functions are identified (even if not yet formalised)
- [ ] Communication kit is complete and jargon-free

Save the output to `project/architecture-runway.md`.
