# CAF Operations — Capability Assessment (VCAP)

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** Operations view.

Project context: $ARGUMENTS

Read available artifacts:
- `project/principles.md`
- `project/requirements.md`
- `enterprise/operating-unit-map.md` (if available)
- `experience-objectives/jtbd.md` (if available)

---

## Objective

Produce a **Operations Capability Assessment** grounded in the CAF VCAP framework (Values, Capabilities, Assets, Processes).

The CAF Operations view shapes the enterprise's resources and processes to build competitive capabilities. It answers: what can our operating system do, what should it be able to do, and what is the gap?

---

## Output: `operations/capabilities.md`

### 1. Operating Unit in scope

State the Operating Unit (from `enterprise/operating-unit-map.md`) or programme being assessed.
If no OU map exists, describe the business perimeter.

### 2. Values assessment

Values are the standards by which employees set priorities and behave. They determine what the operating system can and cannot do as much as assets and processes.

| Value | Current expression | Desired expression | Gap |
|---|---|---|---|
| [e.g. Customer autonomy] | Employees follow procedures blindly | Employees empowered to solve customer problems | Training, authority matrix |
| [e.g. Speed over perfection] | Multi-layer approval for changes | Decentralised decision-making | Governance reform |
| [e.g. Data-driven decisions] | Gut-feel prioritisation | Metrics-led product decisions | Analytics platform |

Identify 3–5 values relevant to the OU's mission. For each, assess the gap between current and desired expression.

### 3. Capability map

For each major capability the OU needs to deliver its products:

| Capability | Type | Maturity | Strategic importance | Gap |
|---|---|---|---|---|
| [e.g. Real-time payment processing] | Digital | Developing | Core differentiator | Latency > target |
| [e.g. Customer onboarding] | Hybrid | Managed | Important | Partially manual |
| [e.g. Fraud detection] | Digital / AI | Initial | Core differentiator | No ML model in production |
| [e.g. Regulatory reporting] | Process | Optimising | Compliance | Automated but fragile |

Capability types: Digital | Manual process | Hybrid | AI-assisted
Maturity levels: Initial → Developing → Defined → Managed → Optimising

### 4. Classical operations dimensions

Assess the 4 classical operations dimensions for this OU:

**Cost efficiency**
- Current cost structure: [describe]
- Target: [e.g. "Reduce processing cost per transaction by 20%"]
- Key lever: [e.g. automation, offshore, platform sharing]

**Lead time**
- Current lead time for key process: [e.g. "Account opening: 5 days"]
- Target: [e.g. "2 days"]
- Constraint: [e.g. regulatory verification step]

**Quality**
- Current defect / error rate: [e.g. "2% payment errors"]
- Target: [e.g. "< 0.1%"]
- Key quality risk: [e.g. manual data entry]

**Flexibility**
- Can the OU absorb demand spikes? [Yes / No / Partially]
- Peak capacity vs average load ratio: [e.g. "3x at month-end"]
- Current mechanism: [e.g. manual overtime / cloud auto-scaling]

### 5. Digital operations assessment

Assess the 3 digital operations levers:

**Process automation**

| Process | Automation level | Improvement opportunity | Effort |
|---|---|---|---|
| [e.g. Payment validation] | 80% automated | Full automation with ML | M |
| [e.g. Reconciliation] | 30% automated | RPA + exception handling | L |

**AI / ML in production**

| Use case | Status | Impact | Next step |
|---|---|---|---|
| [e.g. Fraud scoring] | In production | High — 40% fraud reduction | Improve model accuracy |
| [e.g. Cash flow forecasting] | Proof of concept | Medium | Deploy to production |
| [e.g. Document classification] | Not started | Medium | Spike in Q3 |

**Self-care and shift-left**

Which activities can be shifted from employees to customers or third parties?
- [e.g. "Account opening — move to customer self-service portal"]
- [e.g. "Payment status — push notifications replacing call centre"]

### 6. Asset inventory (key digital assets)

| Asset | Type | Age | Fitness | Action needed |
|---|---|---|---|---|
| [e.g. Core banking system] | Legacy application | 15 years | Low — monolith, hard to change | Decomposition plan |
| [e.g. Customer portal] | Web application | 3 years | High | Maintain |
| [e.g. Data warehouse] | Data platform | 8 years | Medium | Migrate to real-time |

### 7. Operations strategy

Based on the assessment, state the operations strategy for the next 12–18 months:

**Strategic intent:** [1 paragraph — where is the OU investing in operational capability?]

**Top 3 capability investments:**
1. [Capability] — [rationale] — [investment type: Build / Buy / Partner / Automate]
2.
3.

**Capabilities to maintain (no major investment):**
- [list]

**Capabilities to retire or outsource:**
- [list]

### 8. Next steps

- [ ] Validate capability map with OU lead and operations team
- [ ] Run `/caf.ops-readiness` to assess operational readiness for near-term delivery
- [ ] Add capability investment items to `project/architecture-runway.md`
- [ ] Cross-reference AI/ML use cases with Technology view (`/caf.tech-principles`)

---

## Quality gates

- [ ] At least 5 capabilities assessed with maturity level
- [ ] All 4 classical operations dimensions assessed
- [ ] Digital operations levers addressed (automation, AI, self-care)
- [ ] Top 3 capability investments stated with rationale
- [ ] Asset inventory includes at least the most critical systems

Save the output to `operations/capabilities.md`.
