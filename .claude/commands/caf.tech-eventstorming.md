# CAF Technology — Event Storming Facilitation Guide

## Context

You are an enterprise architect facilitating or preparing an **Event Storming** workshop as part of the CAF Technology view.

Domain or bounded context to explore: $ARGUMENTS

Read available artifacts:
- `enterprise/domain-map.md` (if available — provides domain context)
- `experience-objectives/jtbd.md` (if available — provides business process signals)
- `project/requirements.md`

---

## Objective

Produce an **Event Storming Facilitation Package** — everything needed to run or document the event storming session for a given domain.

Event storming (as recommended in the CAF Technology view) is the primary DDD practice for identifying domain events, modelling business domain behaviour, and finding bounded context boundaries. It is a workshop, not a solo exercise — but this command prepares the materials and produces the documentation artefact.

---

## Output: `technology/event-storming-[domain-name].md`

### 1. Workshop preparation

**Domain in scope:** [from $ARGUMENTS]
**Recommended participants:**
- Domain expert(s): [roles — e.g. product owner, business analyst, operations lead]
- Developers: 2–4 engineers who will build in this domain
- Product Architect: facilitator
- Optional: UX designer if user-facing flows are involved

**Duration:** 2–4 hours for a focused domain; 1 day for a full business process
**Format:** Physical (sticky notes on a wall) preferred; Miro/FigJam for remote

**Preparation checklist:**
- [ ] Define the scope: which business process or bounded context?
- [ ] Invite the right domain experts — no domain expert = no event storming
- [ ] Brief participants: "We are modelling events, not building a system"
- [ ] Prepare materials: orange stickies (events), blue (commands), yellow (actors), pink (pain points / questions), lilac (aggregates), green (read models / views)

### 2. Event storming narrative (pre-session analysis)

Based on available artifacts, produce a first-pass narrative of the domain to seed the workshop:

**Business process being modelled:** [name]
**Starting trigger:** [e.g. "Treasurer initiates a payment"]
**End state:** [e.g. "Payment settled and reconciled"]

**First-pass domain events** (orange stickies — past tense, significant business facts):

List at least 10–15 domain events in sequence. Format: `[EventName]` — one line description.

Example:
- `PaymentInitiated` — Treasurer submits payment instruction
- `PaymentValidated` — Business rules check passed
- `FundsReserved` — Liquidity confirmed in source account
- `PaymentSentToBank` — Instruction dispatched to banking network
- `PaymentConfirmed` — Bank acknowledgement received
- `AccountDebited` — Source account balance updated
- `AccountCredited` — Destination account balance updated
- `ReconciliationTriggered` — End-of-day reconciliation process started
- `TransactionRecorded` — Accounting entry created
- `ReportGenerated` — Transaction appears in treasurer's report

**Known pain points / hotspots** (pink stickies — questions or problems):
- [Pain point 1: e.g. "Manual reconciliation step — high error rate"]
- [Pain point 2]
- [...]

**Actors identified** (yellow stickies — who triggers or receives events):
- [Actor 1: e.g. "Treasurer"]
- [Actor 2]
- [...]

### 3. Bounded context candidates

Based on the event sequence, identify natural clustering points where events have high internal cohesion and low coupling with other clusters:

| Bounded context candidate | Events it contains | Rationale for boundary |
|---|---|---|
| Payment Initiation | PaymentInitiated, PaymentValidated, FundsReserved | Same actor, same business moment |
| Payment Execution | PaymentSentToBank, PaymentConfirmed | Banking network interaction — different latency and failure mode |
| Accounting | AccountDebited, AccountCredited, TransactionRecorded | Financial record — regulatory boundary |
| Reconciliation | ReconciliationTriggered, ReportGenerated | End-of-day batch — different lifecycle |

Flag any context boundary that feels uncertain — these are the most valuable workshop discussion points.

### 4. Aggregates and commands

For each bounded context, identify:

**Aggregates** (lilac stickies — the business entities that enforce consistency rules):

| Aggregate | Bounded context | Key invariant (the rule it enforces) |
|---|---|---|
| Payment | Payment Initiation | A payment cannot be initiated without sufficient funds |
| Transaction | Accounting | A transaction must always balance (debit = credit) |

**Commands** (blue stickies — actions that trigger events):

| Command | Triggers event | Actor | Aggregate |
|---|---|---|---|
| InitiatePayment | PaymentInitiated | Treasurer | Payment |
| ValidatePayment | PaymentValidated | System (automated) | Payment |
| RecordTransaction | TransactionRecorded | System | Transaction |

### 5. Read models and integration points

**Read models** (green stickies — views that users or systems need):

| Read model | Consumer | Data needed | Update trigger |
|---|---|---|---|
| Cash position dashboard | Treasurer | Account balances, pending payments | Real-time, on PaymentInitiated |
| Daily transaction report | Finance team | All transactions in period | End of day |

**Integration points with other domains:**

| Event | Published to | Consumer domain | Integration pattern |
|---|---|---|---|
| PaymentConfirmed | Payment domain → Accounting domain | Accounting | Published Language (event schema) |
| TransactionRecorded | Accounting → Reporting | Reporting | Customer-Supplier |

### 6. Post-workshop documentation checklist

After running the physical session, capture:

- [ ] Photograph the wall / export the Miro board
- [ ] Document all domain events in the final sequence
- [ ] Record all hotspots (pink stickies) as open questions in this document
- [ ] Confirm bounded context boundaries with domain experts
- [ ] Update `enterprise/domain-map.md` with confirmed bounded contexts
- [ ] Create ADRs for any significant design decisions made during the session via `/caf.product-adr`

### 7. Open questions

List all unresolved questions identified during the analysis (to be answered in the workshop or follow-up sessions):

| Question | Why it matters | Owner | Target date |
|---|---|---|---|
| [e.g. "Who owns the Payment aggregate — Initiation or Execution context?"] | Boundary decision affects team ownership | Product Architect | Sprint N |

### 8. Next steps

- [ ] Run the workshop with domain experts
- [ ] Update this document with workshop findings
- [ ] Update `enterprise/domain-map.md` with confirmed bounded contexts
- [ ] Create implementation enablers in `project/architecture-runway.md`

---

## Quality gates

- [ ] At least 10 domain events identified in past-tense format
- [ ] At least 2 bounded context candidates with rationale
- [ ] Aggregates identified for each bounded context
- [ ] Integration points with other domains documented
- [ ] Open questions are listed (not hidden)

Save the output to `technology/event-storming-[domain-name].md`.
