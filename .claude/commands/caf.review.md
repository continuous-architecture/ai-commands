# CAF Review — Cross-View Architecture Health Check

## Context

You are an enterprise architect running a **CAF Cross-View Review** — a structured assessment of the programme's architecture health across all 6 CAF views.

Project context: $ARGUMENTS

Read ALL available artifacts in the project:
- `project/principles.md`
- `project/architecture-runway.md`
- `experience-objectives/jtbd.md`, `experience-objectives/personas.md`
- `product/` (all files)
- `technology/tech-principles.md`, `technology/fitness-functions.md`, `technology/adrs/README.md`
- `operations/capabilities.md`, `operations/readiness.md`
- `organisation/team-design.md`, `organisation/interaction-modes.md`, `organisation/inverse-conway-audit.md`
- `enterprise/operating-unit-map.md`, `enterprise/product-portfolio-map.md`, `enterprise/domain-map.md`

---

## Objective

Produce a **CAF Architecture Health Report** — a RAG assessment of the programme across all 6 views, with cross-view tensions, key risks, and a prioritised action plan.

This is the primary artefact for an Architecture Review Board or programme steering committee.

---

## Output: `project/caf-review-[YYYY-MM-DD].md`

### 1. Executive summary

**Programme:** [name]
**Review date:** [today]
**Overall architecture health:** Red / Amber / Green

[3–5 sentences: what is the overall state of the architecture, the top 2 strengths, and the top 2 critical risks.]

### 2. Per-view RAG assessment

For each CAF view, assess the current state:

| View | RAG | Coverage | Top strength | Top risk |
|---|---|---|---|---|
| Experience Objectives | | [% of artifacts complete] | | |
| Product | | | | |
| Technology | | | | |
| Operations | | | | |
| Organisation | | | | |
| Enterprise Decomposition | | | | |

Coverage = what % of the expected artifacts for this view have been produced and are current.

#### Experience Objectives

**RAG:** [Red / Amber / Green]
**Key finding:** [1 paragraph]
- JTBD analysis: [done / partial / missing]
- Personas: [done / partial / missing]
- Architecture implications documented: [yes / no]

#### Product

**RAG:** [Red / Amber / Green]
**Key finding:** [1 paragraph]
- Architecture runway: [current / stale / missing]
- ADR coverage: [N ADRs, N pending, N stale]
- Scoping 360: [done / not done]

#### Technology

**RAG:** [Red / Amber / Green]
**Key finding:** [1 paragraph]
- CAF tech principles: [assessed / not assessed]
- Fitness functions active: [N active / N total defined]
- Failing fitness functions: [N — list]
- Event storming coverage: [N domains documented]

#### Operations

**RAG:** [Red / Amber / Green]
**Key finding:** [1 paragraph]
- Capability assessment: [done / partial / missing]
- Operational readiness: [Green / Amber / Red / not assessed]
- Digital operating model: [defined / partial / missing]

#### Organisation

**RAG:** [Red / Amber / Green]
**Key finding:** [1 paragraph]
- Team topology: [defined / evolving / undefined]
- Interaction modes: [formalised / informal / undefined]
- Conway alignment: [aligned / partial / misaligned]

#### Enterprise Decomposition

**RAG:** [Red / Amber / Green]
**Key finding:** [1 paragraph]
- OU map: [complete / partial / missing]
- Product portfolio: [mapped / partial / missing]
- Domain map: [complete / partial / missing]
- Core domains identified: [yes / no]

### 3. Cross-view tensions

The most important findings of a CAF review are often the tensions *between* views — where one view creates pressure on another.

| Tension | Views involved | Description | Risk if unresolved | Recommended action |
|---|---|---|---|---|
| [e.g. OU boundary ≠ team boundary] | Enterprise Decomp. ↔ Organisation | Wealth OU is served by 2 teams — coordination overhead | Slow delivery, inconsistent client experience | Run `/caf.org-inverse-conway` |
| [e.g. JTBD requires real-time but ops not ready] | Experience Objectives ↔ Operations | Customer expects real-time payment status but ops readiness is Amber | Launch risk | Resolve ops gap before launch |
| [e.g. Tech debt blocks JTBD delivery] | Technology ↔ Experience Objectives | Fitness function FF-002 (coupling) failing — blocking new features | Feature delivery slowing | Prioritise EN-002 in runway |

Document at least 3 cross-view tensions.

### 4. Architecture debt register

Compile all architectural debt items from across the views:

| ID | Debt item | View | Impact | Effort | Priority | Linked enabler |
|---|---|---|---|---|---|---|
| DEBT-001 | Shared database across Order and Customer domains | Technology | High | L | High | EN-002 |
| DEBT-002 | No fitness function for security compliance | Technology | High | S | High | New |
| DEBT-003 | Wealth OU served by 2 teams — no clear boundary | Organisation | Medium | M | Medium | — |

### 5. Prioritised action plan

Consolidate the top 10 actions across all views, ordered by impact:

| Priority | Action | View | Owner | Effort | Deadline |
|---|---|---|---|---|---|
| 1 | [action] | | | | |
| 2 | | | | | |
| ... | | | | | |

### 6. Architecture maturity trajectory

Based on the current review and any previous reviews, assess the trend:

| View | Previous RAG | Current RAG | Trend | Velocity |
|---|---|---|---|---|
| Technology | Amber | Green | Improving | Fast |
| Organisation | Red | Amber | Improving | Slow |

If this is the first review, note: "Baseline established. Next review in [3 months]."

### 7. Governance recommendations

For an Architecture Review Board or programme steering committee:

**Decisions requiring board sign-off:**
- [e.g. DEBT-001 resolution — significant investment required]

**Decisions delegated to programme architects:**
- [e.g. DEBT-003 — team restructuring within programme scope]

**Next review date:** [recommended: quarterly, or at each SAFe PI boundary]

---

## Quality gates

- [ ] All 6 views assessed with RAG
- [ ] At least 3 cross-view tensions documented
- [ ] Architecture debt register is complete
- [ ] Top 10 actions are prioritised with owners
- [ ] Governance recommendations are clear

Save the output to `project/caf-review-[YYYY-MM-DD].md`.
