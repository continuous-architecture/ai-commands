# CAF Enterprise Decomposition — Product Portfolio Map

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** Enterprise Decomposition view, focusing on the Product dimension.

Project context: $ARGUMENTS

Read the following artifacts before starting:
- `enterprise/operating-unit-map.md` ← **required**: OU structure must exist first
- `project/requirements.md`
- `project/stakeholders.md`

If `enterprise/operating-unit-map.md` does not exist, halt and instruct the user to run `/caf.ed-operating-unit-map` first.

---

## Objective

Produce a **Product Portfolio Map** that shows how products and product lines are distributed across Operating Units — and identifies opportunities for shared platforms.

In the CAF, a product is a named collection of business capabilities valuable to a defined customer segment. Products are owned by OUs, but some products can be shared (as platforms) across multiple OUs.

This command answers three questions central to the CAF Product view:
- Which OU owns which products?
- Which products could become platforms shared across OUs?
- Which products are candidates for rationalisation or retirement?

---

## Output: `enterprise/product-portfolio-map.md`

### 1. Product inventory

For each product identified across all Operating Units in `enterprise/operating-unit-map.md`, produce a structured entry:

---

**Product:** [name]
**Owning OU:** [OU name]
**Type:** External product | Internal product | Platform | Shared service
**Customer segment:** [who uses this product]
**Business capabilities delivered:** List 3–5 core capabilities
**Lifecycle stage:** Ideation | Growth | Maturity | Decline | Retirement
**Digital channel:** Web | Mobile | API | Physical | Omnichannel
**Shared with other OUs?** Yes — [list OUs] | No
**Technical footprint:** Standalone application | Shared component | Legacy system | Greenfield

---

### 2. Product lines

Group products into product lines. A product line is a set of related products serving the same customer segment or business capability family.

| Product line | Products included | Owning OU | Shared across OUs? |
|---|---|---|---|
| Mortgage products | Home loan, Buy-to-let loan, Bridge loan | Back Office | Yes — Retail and Wealth |
| Payment services | Card payment, Wire transfer, Direct debit | Payment Factory | Yes — all market-facing OUs |

### 3. Platform candidates

Identify products or capabilities that are — or should be — offered as platforms shared across OUs.

For each platform candidate:

**Platform candidate:** [name]
**Current state:** [Siloed per OU / Partially shared / Already a platform]
**Consuming OUs:** [list]
**Value of platforming:** Cost reduction | Speed of delivery | Compliance centralisation | Quality consistency
**Effort to platform:** Low (API wrapper) | Medium (product redesign) | High (programme-level investment)
**Recommendation:** Proceed | Investigate | Defer

Flag at least the top 3 platform candidates. In large groups, shared digital capabilities (identity, notification, payment, data) are almost always platform candidates.

### 4. Product lifecycle heat map

Summarise the portfolio health across OUs:

| OU | Products in Growth | Products in Maturity | Products in Decline | Products to retire |
|---|---|---|---|---|
| Retail segment | 3 | 8 | 2 | 1 |
| Wealth segment | 5 | 4 | 1 | 0 |
| Payment Factory | 1 | 4 | 3 | 2 |

Flag any OU where the majority of products are in Decline or Maturity — this signals a need for portfolio renewal investment.

### 5. Shared ownership risks

List every product that is currently shared across OUs without a clear platform model:

| Product | OUs involved | Problem | Recommended resolution |
|---|---|---|---|
| Mortgage origination system | Retail + Wealth | Shared codebase, no API boundary | Platform OU with consumer contracts |
| Customer data store | All OUs | Multiple copies, inconsistent | Master data management platform |

Shared ownership without a platform model = high architectural and operational risk. Flag these prominently.

### 6. Product-to-team alignment

If `organisation/team-design.md` exists, map products to their owning teams:

| Product | Owning OU | Owning team | Team type | Gap? |
|---|---|---|---|---|
| Home loan | Back Office | Mortgage team | Stream-aligned | No |
| Payment API | Payment Factory | Platform team | Platform | No |
| Customer profile | Multiple | No clear owner | — | Yes — ownership gap |

Flag every product without a clear team owner. In large groups, ownership gaps are a primary source of delivery failure.

### 7. Inputs from CAF views

| CAF view | Input | Portfolio impact |
|---|---|---|
| Experience Objectives | Wealth clients demand personalised advisory | → Advisory product line investment needed |
| Operations | Payment processing at scale requires industrialisation | → Payment Factory platform reinforced |
| Technology | API-first strategy | → All platform candidates must expose REST/event APIs |
| Enterprise Decomposition | OU boundaries | → Products mapped to single OU where possible |

### 8. Next steps

- [ ] Validate product ownership with OU leads and product owners
- [ ] Prioritise top 3 platform candidates for architecture runway
- [ ] Run `/caf.ed-domain-map` to align technical bounded contexts with product boundaries
- [ ] Add platform candidates to `project/architecture-runway.md` (or create it)

---

## Quality gates

Before saving, verify:
- [ ] Every OU from `operating-unit-map.md` has at least one product listed
- [ ] Every shared product has an ownership analysis entry
- [ ] At least 3 platform candidates are identified and assessed
- [ ] Products without a team owner are explicitly flagged
- [ ] The product lifecycle heat map covers all OUs

Save the output to `enterprise/product-portfolio-map.md`.
