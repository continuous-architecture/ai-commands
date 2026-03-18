![License](https://img.shields.io/badge/license-Apache%202.0-blue)
![Commands](https://img.shields.io/badge/commands-25-1D9E75)
![CAF](https://img.shields.io/badge/framework-Continuous%20Architecture-534AB7)
![Claude Code](https://img.shields.io/badge/Claude%20Code-compatible-black)
![Copilot](https://img.shields.io/badge/GitHub%20Copilot-compatible-black)

# Continuous Architecture — AI Commands

AI-assisted commands for architects practising the [Continuous Architecture Framework (CAF)](https://continuous-architecture.org).

This repository provides 25 ready-to-use commands for AI coding assistants — Claude Code, GitHub Copilot, Gemini — that operationalise the full CAF across its six views, five practices, and five rituals. Each command produces structured, traceable architecture artifacts aligned with the CAF manifesto.

> This repository is a companion to the [Continuous Architecture Toolkit](https://github.com/continuous-architecture/toolkit).
> The toolkit defines the framework. This repo puts it into practice with AI.

---

## Why this exists

Architecture frameworks often live in documentation. Practitioners read them, then face a blank page when starting a real engagement.

These commands close that gap. They embed CAF thinking directly into your AI assistant: the right questions, the right outputs, the right quality gates — for each phase of the product lifecycle, across every CAF view.

The approach is inspired by [ArcKit](https://arckit.org), adapted and extended to cover the full CAF, including the Organisation and Enterprise Decomposition views that most AI toolkits overlook.

---

## Quick start

```bash
# 1. Clone this repository
git clone https://github.com/continuous-architecture/ai-commands.git

# 2. Copy the commands into your project (Claude Code)
cp -r ai-commands/.claude/commands/ my-project/.claude/commands/

# 3. Start Claude Code
cd my-project
claude

# 4. Initialise your CAF project
/caf.init  Payment modernisation programme, retail bank, 80 engineers
```

---

## The 25 commands

### Transversal — project lifecycle

| Command | What it produces |
|---|---|
| `caf.init` | Project structure, `CLAUDE.md`, seeded principles file |
| `caf.review` | Cross-view RAG health assessment for Architecture Review Board |
| `caf.report` | 2-page executive report for CTO / Programme Director |
| `caf.self-assessment` | Maturity scoring across all views, practices, and rituals + improvement roadmap |

### Experience Objectives view

| Command | What it produces |
|---|---|
| `caf.xo-jtbd` | Jobs-to-be-done analysis — performer, jobs, stages, needs, circumstances |
| `caf.xo-personas` | Persona cards + experience map + architecture sensitivity matrix |

### Product view

| Command | What it produces |
|---|---|
| `caf.product-runway` | Architecture runway — tech radar, enabler backlog, consolidated roadmap |
| `caf.product-adr` | Individual Architecture Decision Record (full CAF 5-step process) |
| `caf.product-scoping` | Scoping 360 — problem framing, team composition, architecture approach, delivery plan |

### Technology view

| Command | What it produces |
|---|---|
| `caf.tech-principles` | Assessment of the 4 CAF technology principles with RAG + DORA metrics |
| `caf.tech-fitness` | Fitness functions register + board + implementation roadmap |
| `caf.tech-eventstorming` | Event storming facilitation package — brief, domain events, bounded context candidates, aggregates |

### Operations view

| Command | What it produces |
|---|---|
| `caf.ops-capabilities` | VCAP capability assessment — values, capabilities, assets, processes |
| `caf.ops-readiness` | Operational readiness gate — observability, failure, security, capacity, deployment |
| `caf.ops-digital` | Digital operating model — automation, AI/ML, self-care, developer experience |

### Organisation view

| Command | What it produces |
|---|---|
| `caf.org-team-design` | Team topology (Team Topologies typology), cognitive load assessment, dependency map |
| `caf.org-interaction-modes` | Team API cards, interaction mode register (Collaboration / X-as-a-Service / Facilitating) |
| `caf.org-inverse-conway` | Conway's Law audit, coupling heatmap, action plan — RAG status for ARB |

### Enterprise Decomposition view

| Command | What it produces |
|---|---|
| `caf.ed-operating-unit-map` | OU hierarchy, decomposition criteria, cross-OU dependencies |
| `caf.ed-product-portfolio` | Product inventory per OU, platform candidates, lifecycle heat map |
| `caf.ed-domain-map` | Bounded context map (DDD), OU–domain alignment, core domain identification |

### Practices

| Command | What it produces |
|---|---|
| `caf.practice-adr` | ADR index + decision health check (stale, orphaned, coverage gaps) |

### Rituals

| Command | What it produces |
|---|---|
| `caf.ritual-kata` | Architecture kata facilitation package — brief, format, session output |
| `caf.ritual-peer-review` | Peer review request + feedback register + dissent log |
| `caf.ritual-weekly` | Weekly architecture meeting agenda + minutes template |

---

## Installation

### Prerequisites

You need one of the following AI assistants:

- [Claude Code](https://docs.anthropic.com/claude-code) — recommended, full agent support
- GitHub Copilot with custom instructions support
- Gemini CLI

You do **not** need to know how to code. These are text files.

### Step 1 — Clone

```bash
git clone https://github.com/continuous-architecture/ai-commands.git
```

### Step 2 — Copy

**Claude Code:**
```bash
cp -r ai-commands/.claude/commands/ my-project/.claude/commands/
```

**GitHub Copilot:**
```bash
cp -r ai-commands/.copilot/ my-project/.copilot/
```

**Gemini:**
```bash
cp -r ai-commands/.gemini/ my-project/.gemini/
```

### Step 3 — Use

```bash
cd my-project
claude
/caf.init  [your programme context in plain language]
```

---

## How to use a command

Each command accepts a plain-language description of your context as input.

```
/caf.xo-jtbd
  Corporate treasury management platform, targeting mid-size companies, 3 personas

/caf.org-team-design
  E-commerce replatforming, migrating from monolith, 6 teams, 80 engineers

/caf.self-assessment
  We are 6 months into our CAF adoption, team of 12 architects across 4 programmes
```

The command reads any existing project artifacts, asks for clarification if critical context is missing, and produces a structured Markdown document.

---

## Recommended workflow

### At project start

```
caf.init
    │
    ├── caf.xo-jtbd ──→ caf.xo-personas
    │
    ├── caf.ed-operating-unit-map ──→ caf.ed-product-portfolio ──→ caf.ed-domain-map
    │
    └── caf.org-team-design ──→ caf.org-interaction-modes ──→ caf.org-inverse-conway
```

### Ongoing delivery

```
caf.product-runway ──→ caf.product-adr (per decision)
caf.tech-principles ──→ caf.tech-fitness
caf.ritual-weekly (every week)
```

### Before a major release

```
caf.ops-readiness ──→ caf.review ──→ caf.report
```

### Every 6 months

```
caf.self-assessment ──→ caf.review ──→ caf.report
```

### On-demand

```
caf.tech-eventstorming [domain]     ← when exploring a new domain
caf.ritual-kata [challenge]         ← quarterly or on a hard problem
caf.ritual-peer-review [ADR]        ← before committing a significant decision
caf.product-scoping                 ← at the start of a new product or team
```

---

## Project structure produced by these commands

```
my-project/
├── CLAUDE.md                          ← auto-context for Claude Code (from caf.init)
├── project/
│   ├── principles.md
│   ├── requirements.md
│   ├── architecture-runway.md
│   ├── caf-review-YYYY-MM-DD.md
│   ├── executive-report-YYYY-MM-DD.md
│   └── self-assessment-YYYY-MM-DD.md
│
├── experience-objectives/
│   ├── jtbd.md
│   └── personas.md
│
├── product/
│   ├── portfolio.md
│   └── scoping-360.md
│
├── technology/
│   ├── tech-principles.md
│   ├── fitness-functions.md
│   ├── event-storming-[domain].md
│   └── adrs/
│       ├── README.md                  ← ADR index (from caf.practice-adr)
│       ├── ADR-001-[title].md
│       └── ...
│
├── operations/
│   ├── capabilities.md
│   ├── readiness.md
│   └── digital-operating-model.md
│
├── organisation/
│   ├── team-design.md
│   ├── interaction-modes.md
│   └── inverse-conway-audit.md
│
├── enterprise/
│   ├── operating-unit-map.md
│   ├── product-portfolio-map.md
│   └── domain-map.md
│
└── rituals/
    ├── weekly-arch-YYYY-MM-DD.md
    ├── kata-[topic]-YYYY-MM-DD.md
    └── peer-review-[topic]-YYYY-MM-DD.md
```

---

## Design principles

**Alignment + Autonomy > Control.** Commands produce artifacts that help teams align without imposing top-down control. Every output is a starting point for conversation, not a constraint.

**Grounded in real problems.** Each command reads existing project context before generating anything. It does not produce generic content — it reasons from your specific situation.

**AI-agnostic by design.** The same commands work across Claude Code, Copilot, and Gemini. Output format is identical regardless of the underlying model. Your artifacts are portable.

**Traceable.** Every command produces quality gates that verify traceability back to principles, requirements, and other artifacts. Architecture decisions do not appear from nowhere.

---

## Contributing

A command is a Markdown file. If you have a CAF practice that could be assisted by AI, you can contribute it — no coding experience required.

See [CONTRIBUTING.md](./CONTRIBUTING.md) for the command template and review process.

Join the conversation on [LinkedIn](https://www.linkedin.com/company/continuous-architecture/) or at our [events](https://continuous-architecture.org/#events).

---

## Relationship to other frameworks

These commands draw on:

- [Team Topologies](https://teamtopologies.com) — Skelton & Pais
- [Domain-Driven Design](https://github.com/ddd-crew) — Evans / DDD-crew
- [Open Agile Architecture](https://www.opengroup.org/AgileArchitecture) — The Open Group
- [Scaled Agile Framework (SAFe)](https://www.scaledagileframework.com)
- [Building Evolutionary Architectures](https://www.thoughtworks.com/books/building-evolutionary-architectures) — Ford, Parsons, Kua (fitness functions)
- [ArcKit](https://arckit.org) — inspiration for the command structure

---

## License

Apache License 2.0 — see [LICENSE](./LICENSE).

Content is part of the [Continuous Architecture](https://continuous-architecture.org) open community.
