# Continuous Architecture Framework — Copilot Instructions

This repository contains AI commands for the Continuous Architecture Framework (CAF).
See https://continuous-architecture.org for the full framework documentation.

## What this repository is

This repository provides architecture commands for practitioners of the CAF.
Each file in `.claude/commands/` is a command that produces a structured architecture artifact.
Commands cover the 6 CAF views: Experience Objectives, Product, Technology, Operations, Organisation, Enterprise Decomposition.
Commands also cover CAF practices (ADR, Architecture Runway, Fitness Functions) and rituals (Kata, Peer Review, Weekly Meeting).

## How to use these commands with Copilot

You cannot invoke these commands with a slash syntax in Copilot.
Instead, paste the content of the relevant `.claude/commands/caf.*.md` file into the Copilot Chat and provide your project context.
For example: paste the content of `caf.org-team-design.md` and add "My context: payment modernisation programme, 80 engineers, 4 domains."

## CAF core principles to apply in all responses

When answering architecture questions in this project, always apply these CAF principles.

The central equation of the CAF is: ALIGNMENT + AUTONOMY > CONTROL.
Prefer team autonomy over centralised governance when making architecture recommendations.

Architect for evolutivity and modularity. Prefer modular, independently deployable components over monoliths.
Architect for scalability and resilience. Design for failure as a fact, not a probability.
Architect for continuous delivery and operability. Architecture quality correlates with CI/CD performance.
Apply symbiotic coupling of machines and humans. AI and automation should augment human judgement, not replace it.

## Vocabulary to use

Use "Operating Unit" (not "domain" or "business unit") when referring to CAF enterprise decomposition units.
Use "Architecture Runway" (not "technical backlog") for the list of architecture enablers.
Use "Fitness Function" (not "non-functional requirement monitor") for automated architectural checks.
Use "Interaction Mode" (not "dependency") when describing how teams work together.
Use "Stream-aligned team", "Platform team", "Enabling team", "Complicated-subsystem team" (Team Topologies vocabulary).

## Artifact structure

When producing architecture artifacts, always include these sections.
A context section that states the programme name, scope and key constraints.
A quality gates section at the end with checkboxes verifying completeness.
A next steps section that references the next CAF command to run.
A traceability section linking decisions to principles and requirements.

## What to avoid

Do not recommend big-bang architecture designs. Prefer incremental, continuous approaches.
Do not produce generic content. Always anchor recommendations in the project context provided.
Do not use the word "domain" where "Operating Unit" or "bounded context" is more precise.
Do not recommend a team structure without assessing cognitive load.
