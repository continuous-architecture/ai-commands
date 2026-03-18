# CAF Technology — Principles Assessment

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** Technology view.

Project context: $ARGUMENTS

Read available artifacts:
- `project/principles.md`
- `project/requirements.md`
- `enterprise/domain-map.md` (if available)
- `project/architecture-runway.md` (if available)

---

## Objective

Produce a **Technology Principles Assessment** — a structured evaluation of the current (or proposed) system architecture against the 4 CAF technology principles.

The 4 CAF technology principles are:
1. Architect for evolutivity and modularity
2. Architect for scalability and resilience
3. Architect for continuous delivery and operability
4. Symbiotic coupling of machines and humans

This assessment is not an audit of past decisions. It is a forward-looking evaluation that identifies where the architecture is strong, where it is at risk, and what to invest in next.

---

## Output: `technology/tech-principles.md`

### 1. Scope and context

- Programme / product in scope:
- Current architecture style (inferred from context): [Monolith / Modular / Microservices / Event-driven / Hybrid / Unknown]
- Assessment date:
- Key constraints: [regulatory, legacy, budget, team skills]

---

### 2. Principle 1 — Evolutivity and modularity

**What CAF says:** Modularity is key. Monoliths impede agility. Increasing isolation between software components enables independent delivery. DDD bounded contexts, event-driven architecture, and microservices are the preferred patterns.

**Current state assessment:**

| Indicator | Current state | Target state | Gap |
|---|---|---|---|
| Module isolation | [Siloed / Partial / Strong] | Strong | [description] |
| Deployment independence | [Coupled / Partial / Independent] | Independent | |
| DDD applied | [None / Partial / Full] | Partial-Full | |
| Event-driven interfaces | [None / Some / Majority] | Majority | |

**RAG status:** Red / Amber / Green
**Key finding:** [1–2 sentences]
**Recommended actions:**
1.
2.

---

### 3. Principle 2 — Scalability and resilience

**What CAF says:** Design for failure as a fact, not a probability. Systems must be Responsive, Resilient, Elastic, and Message-Driven (Reactive Manifesto). Key metrics: MTBF and MTTR. Modularity + redundancy = high availability.

**Current state assessment:**

| Indicator | Current state | Target state | Gap |
|---|---|---|---|
| Failure isolation | [None / Partial / Strong] | Strong | |
| Auto-scaling capability | [None / Manual / Automatic] | Automatic | |
| Observability (logs, metrics, traces) | [None / Partial / Full] | Full | |
| MTTR target defined | [Yes / No] | Yes | |
| Chaos engineering practice | [None / Ad-hoc / Regular] | Regular | |

**RAG status:** Red / Amber / Green
**Key finding:** [1–2 sentences]
**Recommended actions:**
1.
2.

---

### 4. Principle 3 — Continuous delivery and operability

**What CAF says:** Architecture quality correlates directly with CI/CD pipeline performance (State of DevOps, 2017). High-performing teams deploy frequently and recover fast. Build for operability means: testability, deployability, and observability are first-class architecture concerns.

**Current state assessment:**

| Indicator | Current state | Target state | Gap |
|---|---|---|---|
| Deployment frequency | [Annual / Monthly / Weekly / Daily] | Weekly+ | |
| Lead time for change | [Months / Weeks / Days / Hours] | Days | |
| Change failure rate | [High >30% / Medium / Low <5%] | Low | |
| MTTR after incident | [Days / Hours / Minutes] | Hours | |
| Test automation coverage | [<30% / 30–70% / >70%] | >70% | |
| Architecture fitness functions in CI | [None / Some / Comprehensive] | Comprehensive | |

**RAG status:** Red / Amber / Green
**Key finding:** [1–2 sentences]
**Recommended actions:**
1.
2.

---

### 5. Principle 4 — Symbiotic coupling of machines and humans

**What CAF says:** Augment humans with automation and AI; do not replace judgement. Smart automation enhances human capability. AI/ML should improve process intelligence, not just replace headcount.

**Current state assessment:**

| Indicator | Current state | Target state | Gap |
|---|---|---|---|
| Process automation level | [Low / Medium / High] | High for repetitive tasks | |
| AI/ML in production | [None / Experimental / Production] | Production for 1+ use cases | |
| Human oversight mechanisms | [None / Manual / Automated alerts] | Automated with human escalation | |
| Developer experience | [Poor / Acceptable / Good] | Good — internal platform | |

**RAG status:** Red / Amber / Green
**Key finding:** [1–2 sentences]
**Recommended actions:**
1.
2.

---

### 6. Overall assessment

| Principle | RAG | Top action |
|---|---|---|
| 1. Evolutivity and modularity | | |
| 2. Scalability and resilience | | |
| 3. Continuous delivery and operability | | |
| 4. Symbiotic coupling | | |

**Overall architecture health:** Red / Amber / Green

**Priority investment areas** (rank the 3 most impactful actions across all principles):
1.
2.
3.

### 7. Alignment with architecture runway

Map the recommended actions to enablers in `project/architecture-runway.md`:

| Recommended action | Existing enabler | New enabler needed |
|---|---|---|
| | EN-XXX | / |
| | / | Yes — add to runway |

### 8. Next steps

- [ ] Create ADRs for recommended technology choices via `/caf.product-adr`
- [ ] Formalise fitness functions for Principle 3 gaps via `/caf.tech-fitness`
- [ ] Add new enablers to architecture runway via `/caf.product-runway`
- [ ] Schedule architecture review with team to validate assessment

---

## Quality gates

- [ ] All 4 principles assessed with RAG status
- [ ] Every Red finding has at least 2 recommended actions
- [ ] DORA metrics (Principle 3) are estimated even if approximate
- [ ] Recommended actions are mapped to the architecture runway
- [ ] Overall architecture health status is justified

Save the output to `technology/tech-principles.md`.
