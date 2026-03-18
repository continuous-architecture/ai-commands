# CAF Operations — Operational Readiness Assessment

## Context

You are an enterprise architect assessing operational readiness before a product goes live or reaches a new lifecycle stage.

Project context: $ARGUMENTS

Read available artifacts:
- `operations/capabilities.md` (if available)
- `technology/fitness-functions.md`
- `technology/tech-principles.md`
- `project/architecture-runway.md`
- `organisation/team-design.md`

---

## Objective

Produce an **Operational Readiness Assessment** — a structured gate check that validates the product is ready to operate at scale, safely, and sustainably.

This is not a pre-launch checklist. It is an architecture-grade assessment that surfaces risks before they become production incidents.

---

## Output: `operations/readiness.md`

### 1. Readiness scope

- Product / release in scope:
- Target lifecycle stage: Alpha → Beta | Beta → Live | Live → Scale
- Target date:
- Assessment date:

### 2. Observability readiness

The ability to understand system behaviour from its outputs.

| Dimension | Status | Evidence | Gap |
|---|---|---|---|
| Structured logging in place | Ready / Partial / Not started | | |
| Distributed tracing configured | | | |
| Key metrics instrumented | | | |
| Dashboards for SLIs exist | | | |
| Alerting rules defined and tested | | | |
| On-call runbooks written | | | |

**SLI / SLO definitions:**

| Service / feature | SLI (what we measure) | SLO (target) | Current baseline |
|---|---|---|---|
| [e.g. Payment API] | p95 latency | < 500ms | 420ms |
| [e.g. Availability] | Uptime | 99.9% | 99.7% |

Flag any SLO that is not yet measured as a critical readiness gap.

### 3. Failure readiness

The ability to detect, contain, and recover from failures.

| Dimension | Status | Notes |
|---|---|---|
| Failure modes documented (FMEA or equivalent) | | |
| Circuit breakers in place for external dependencies | | |
| Graceful degradation defined (what happens when X fails?) | | |
| Data backup and recovery tested | | |
| Disaster recovery plan exists | | |
| Chaos engineering / failure injection tested | | |

**Failure scenario table** (top 5 risks):

| Failure scenario | Probability | Impact | Detection mechanism | Recovery procedure | Time to recover |
|---|---|---|---|---|---|
| [e.g. Payment gateway unavailable] | Medium | High | Alert on error rate > 1% | Circuit breaker + queue | < 30 min |
| [e.g. Database primary fails] | Low | Critical | Automated failover monitor | Automated failover | < 5 min |

### 4. Security and compliance readiness

| Dimension | Status | Owner | Evidence |
|---|---|---|---|
| OWASP Top 10 addressed | | | |
| Secrets management in place (no hardcoded credentials) | | | |
| Data classification applied | | | |
| PII handling reviewed | | | |
| Penetration test completed or scheduled | | | |
| Compliance requirements met (list applicable: GDPR, PCI-DSS, etc.) | | | |
| Security architecture review completed | | | |

### 5. Capacity and scalability readiness

| Dimension | Current state | Target state | Gap |
|---|---|---|---|
| Peak load tested | | | |
| Auto-scaling configured | | | |
| Database connection pool sized | | | |
| CDN / caching strategy in place | | | |
| Cost at peak load estimated | | | |

**Load test results summary** (if available):
- Test scenario:
- Peak concurrent users tested:
- Results: pass / fail
- Bottleneck identified:

### 6. Deployment readiness

| Dimension | Status | Notes |
|---|---|---|
| CI/CD pipeline to production exists | | |
| Deployment is automated (no manual steps) | | |
| Rollback procedure documented and tested | | |
| Feature flags in place for risky features | | |
| Blue/green or canary deployment available | | |
| Deployment frequency target: [daily / weekly / per sprint] | | |

### 7. Team readiness

| Dimension | Status | Notes |
|---|---|---|
| On-call rota defined | | |
| Escalation path documented | | |
| Runbooks written for top 5 failure scenarios | | |
| Post-incident review process defined | | |
| Team trained on observability tooling | | |

### 8. Readiness verdict

| Domain | RAG | Top blocker |
|---|---|---|
| Observability | | |
| Failure readiness | | |
| Security / compliance | | |
| Capacity / scalability | | |
| Deployment | | |
| Team | | |

**Overall readiness: Red / Amber / Green**

**Recommendation:**
- Green → Proceed to [target lifecycle stage]
- Amber → Proceed with conditions: [list mandatory items to resolve within N weeks]
- Red → Do not proceed. Blockers: [list]

### 9. Action plan for non-Green items

| Item | Owner | Due date | Priority |
|---|---|---|---|
| | | | |

### 10. Next steps

- [ ] Resolve Red items before go-live date
- [ ] Amber items: agree mitigation plan with product owner and engineering lead
- [ ] Schedule readiness re-assessment after Red/Amber items resolved
- [ ] Document post-launch monitoring plan (first 2 weeks of operation)

---

## Quality gates

- [ ] All 6 readiness domains assessed with RAG
- [ ] SLI/SLO defined for at least the top 2 user-facing services
- [ ] Top 5 failure scenarios documented with recovery procedures
- [ ] Security and compliance checklist completed
- [ ] Overall verdict is clear and justified
- [ ] Action plan covers all non-Green items

Save the output to `operations/readiness.md`.
