# CAF Practice — ADR Index & Decision Health Check

## Context

You are an enterprise architect managing the Architecture Decision Record practice across a product or programme.

Project context: $ARGUMENTS

Read all ADRs in `technology/adrs/` and cross-reference with:
- `project/principles.md`
- `project/architecture-runway.md`
- `technology/fitness-functions.md`

---

## Objective

This command serves two purposes:

1. **Generate an ADR index** — a navigable register of all decisions for the programme
2. **Run a decision health check** — identify stale, conflicting, or undocumented decisions

For creating a *new* individual ADR, use `/caf.product-adr` instead.

---

## Output: `technology/adrs/README.md` (updated)

### 1. ADR register

Read every file in `technology/adrs/` and produce a complete index:

| ID | Title | Status | Date | Deciders | Linked principle | Linked enabler | Superseded by |
|---|---|---|---|---|---|---|---|
| ADR-001 | [title] | Accepted | [date] | [roles] | P1 | EN-002 | — |
| ADR-002 | [title] | Superseded | [date] | | | | ADR-005 |

Status values: Proposed | Accepted | Superseded | Deprecated

### 2. Decision health check

**Stale decisions** (Proposed status older than 4 weeks — decision is stuck):

| ADR | Age | Blocker | Recommended action |
|---|---|---|---|
| ADR-003 | 6 weeks | Waiting for PoC results | Schedule PoC review, set deadline |

**Superseded chain** (ensure supersession is fully documented):

| Superseded ADR | Superseded by | Gap check |
|---|---|---|
| ADR-002 | ADR-005 | Does ADR-005 fully address ADR-002's consequences? [Yes/No] |

**Orphaned decisions** (decisions referenced in the codebase or other docs but not in the ADR register):
- Check `project/architecture-runway.md` for technology choices that don't have a corresponding ADR
- Flag each as: "Technology X is used — no ADR found. Recommend creating ADR."

**Principle alignment check**:

| ADR | Stated principle | Assessment |
|---|---|---|
| ADR-001 | P1 (Modularity) | Aligned — decision introduces event-driven boundary |
| ADR-004 | None stated | Gap — recommend adding principle reference |

### 3. Decision coverage map

For each CAF view, are the key decisions documented?

| CAF view | Key decisions expected | ADRs found | Coverage |
|---|---|---|---|
| Technology | Architecture style, key patterns, platform choices | ADR-001, ADR-002 | Partial |
| Organisation | Team boundaries, interaction contracts | None found | Gap |
| Enterprise Decomposition | OU boundaries, domain ownership | ADR-006 | Partial |
| Product | Build/buy/reuse for each platform capability | None found | Gap |

Flag gaps where important decisions are being made without ADRs.

### 4. Upcoming decisions

Based on open items in `project/architecture-runway.md` and open questions in other artifacts, identify decisions that need to be made in the next 30 days:

| Decision needed | Context | Recommended owner | Urgency | Create ADR |
|---|---|---|---|---|
| API gateway selection | EN-003 in runway — sprint 7 | Product Architect | High | `/caf.product-adr API gateway selection` |
| Event schema versioning strategy | Event storming identified need | Lead engineer | Medium | `/caf.product-adr event schema versioning` |

### 5. Decision governance summary

| Metric | Value | Target | Status |
|---|---|---|---|
| Total ADRs | N | | |
| Accepted | N | >80% of total | |
| Proposed (pending) | N | <3 at any time | |
| Older than 4 weeks in Proposed | N | 0 | |
| ADRs with no linked principle | N | 0 | |

### 6. Next steps

- [ ] Resolve stale Proposed ADRs (set deadline or escalate)
- [ ] Create missing ADRs for orphaned decisions
- [ ] Add principle references to ADRs missing them
- [ ] Share ADR register with all teams at next Weekly Architecture Meeting

---

## Quality gates

- [ ] Every ADR in `technology/adrs/` appears in the index
- [ ] Every stale Proposed ADR has a recommended action
- [ ] Decision coverage map identifies all gaps
- [ ] Upcoming decisions list is populated from the architecture runway

Save the output to `technology/adrs/README.md`.
