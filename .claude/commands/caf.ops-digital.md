# CAF Operations — Digital Operating Model

## Context

You are an enterprise architect designing or assessing the **Digital Operating Model** for an Operating Unit, applying the CAF Operations view.

Project context: $ARGUMENTS

Read available artifacts:
- `operations/capabilities.md`
- `enterprise/operating-unit-map.md`
- `technology/tech-principles.md`

---

## Objective

Produce a **Digital Operating Model** — the blueprint for how the OU will use digital technology to deliver its capabilities at scale.

The CAF identifies 3 digital operations levers: process automation (replacing humans with software), intelligence augmentation (AI/ML improving decisions), and self-care / shift-left (moving activities to customers or third parties). This command produces the strategy and roadmap for all three.

---

## Output: `operations/digital-operating-model.md`

### 1. Digital ambition statement

One paragraph: what does "digital" mean for this OU's operating model in 3 years?
Frame it as: who does what, how, and what that enables for clients and employees.

### 2. Current vs target operating model

| Activity | Who does it today | How (manual / automated / AI) | Who should do it | How (target) | Value of change |
|---|---|---|---|---|---|
| [e.g. KYC document check] | Operations agent | Manual review | AI system + agent exception handling | ML classification + human review for edge cases | 60% cost reduction, 4h → 15min |
| [e.g. Cash flow forecast] | Treasurer (Excel) | Manual, monthly | Treasurer (self-service) | Automated daily forecast with AI | Better decisions, less analyst time |
| [e.g. IT infrastructure provisioning] | IT team | Ticket, 5-day lead time | Product team (self-service) | Infrastructure as code, < 1 hour | Speed, autonomy |

### 3. Automation roadmap

**Tier 1 — High-volume, rule-based processes** (highest ROI for automation)

| Process | Volume | Current cost | Automation approach | Expected saving | Priority |
|---|---|---|---|---|---|
| [e.g. Payment validation] | 500k/day | €X per transaction | Rules engine + exception queue | 80% cost reduction | High |

**Tier 2 — Judgment-intensive processes** (AI augmentation)

| Process | Human judgment needed | AI augmentation approach | Human role after AI | Maturity needed |
|---|---|---|---|---|
| [e.g. Credit risk scoring] | Yes — complex cases | ML model for standard cases | Expert review for edge cases and model drift | ML platform in production |

**Tier 3 — Client-facing activities** (shift-left to self-care)

| Activity | Currently done by | Shift to | Channel | Dependencies |
|---|---|---|---|---|
| [e.g. Account balance check] | Call centre | Customer (self-service) | Mobile app | API readiness, UX design |

### 4. AI/ML investment plan

For each AI/ML use case planned or in progress:

| Use case | Business value | Data readiness | Model approach | Build / Buy / Partner | Status | ROI estimate |
|---|---|---|---|---|---|---|
| [e.g. Fraud detection] | High — €2M/year fraud prevented | High — 3 years of labelled data | Supervised classification | Build (internal data advantage) | In production | Positive |
| [e.g. Churn prediction] | Medium | Medium | Unsupervised clustering + regression | Buy (SaaS vendor) | Pilot | TBD |

**AI governance requirements:**
- Model explainability needed? Yes / No — [regulatory driver]
- Human oversight mechanism: [describe]
- Model drift monitoring: [approach]
- Ethical AI review: [required for which use cases]

### 5. Developer experience and internal platform

In the CAF, digital operations includes the operating model for technology teams themselves. A strong internal platform reduces cognitive load and enables speed.

| Capability | Current state | Target state | Investment needed |
|---|---|---|---|
| Self-service infrastructure | Ticket-driven, 5-day lead | IaC, same-day provisioning | Platform team capacity |
| Shared observability | Per-team, inconsistent | Centralised, standardised | Tooling + adoption |
| Internal API catalogue | None / partial | Discoverable catalogue with SLAs | Developer portal |
| Security as code | Manual security reviews | Automated SAST/DAST in pipeline | Tooling + training |

### 6. Digital operations KPIs

Define the KPIs that will measure the success of the digital operating model:

| KPI | Current | 12-month target | Owner |
|---|---|---|---|
| % of transactions fully automated | [x%] | [y%] | Operations lead |
| AI/ML models in production | [N] | [M] | Data/AI lead |
| Self-service adoption rate | [x%] | [y%] | Product owner |
| Infrastructure provisioning lead time | [N days] | [M hours] | Platform team |
| Developer deployment frequency | [weekly] | [daily] | Engineering lead |

### 7. Risks and dependencies

| Risk | Impact | Likelihood | Mitigation |
|---|---|---|---|
| Data quality insufficient for ML models | High | Medium | Data quality programme before model development |
| Automation displacing roles without transition plan | High | Medium | Change management programme |
| Vendor lock-in for AI/ML platform | Medium | Low | Open standards, portable model formats |

### 8. Next steps

- [ ] Validate automation roadmap with operations lead and product owner
- [ ] Identify quick wins (Tier 1 automation that can start immediately)
- [ ] Define AI governance policy for use cases requiring it
- [ ] Add platform investments to `project/architecture-runway.md`
- [ ] Run `/caf.ops-readiness` for near-term delivery items

---

## Quality gates

- [ ] All 3 digital levers addressed (automation, AI/ML, self-care)
- [ ] At least 3 AI/ML use cases assessed with build/buy/partner recommendation
- [ ] Developer experience platform assessed
- [ ] KPIs defined for each digital lever
- [ ] Risks identified with mitigations

Save the output to `operations/digital-operating-model.md`.
