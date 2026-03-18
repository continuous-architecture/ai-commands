# Contributing to Continuous Architecture AI Commands

Thank you for considering a contribution. This project is maintained by the Continuous Architecture community and welcomes contributions from architects — no coding experience required.

---

## What you can contribute

- **A new command** — a CAF practice you have applied in the field and want to make available to others
- **An improvement to an existing command** — better questions, additional quality gates, richer output structure
- **A translation** — commands in French (the community has a strong French-speaking contingent)
- **Feedback** — open an issue if a command produced poor output or missed something important

---

## Command template

A command is a single Markdown file. Copy this template and fill it in.

```markdown
# CAF [View name] — [Practice name]

## Context

You are an enterprise architect applying the **Continuous Architecture Framework (CAF)** [view name] view.

Project context: $ARGUMENTS

Read the following artifacts before starting:
- `project/principles.md`
- `project/requirements.md`
- [any other relevant input]

If a required artifact is missing, note the assumption and continue.

---

## Objective

[One paragraph describing what this command does and why it matters.]

---

## Output: `[folder]/[filename].md`

### 1. [Section title]
[Describe the expected content of this section]

### 2. [Section title]
[...]

---

## Quality gates

Before saving, verify:
- [ ] [Check 1]
- [ ] [Check 2]
- [ ] [Check 3]

Save the output to `[folder]/[filename].md`.
```

---

## File naming convention

Command files follow this pattern:

```
caf.[view-abbreviation]-[practice-name].md
```

View abbreviations:

| CAF view | Abbreviation |
|---|---|
| Experience Objectives | `xo` |
| Product | `product` |
| Technology | `tech` |
| Operations | `ops` |
| Organisation | `org` |
| Enterprise Decomposition | `ed` |

Examples: `caf.org-team-design.md`, `caf.tech-fitness-functions.md`, `caf.ed-bounded-contexts.md`

---

## Where to place the file

Place your command file in the folder matching the AI assistant:

```
.claude/commands/caf.org-my-command.md     ← Claude Code
.copilot/caf.org-my-command.md             ← GitHub Copilot
.gemini/caf.org-my-command.md              ← Gemini
```

If you only write the Claude Code version, that is fine — the maintainers will port it to the other assistants.

---

## Submitting a contribution

1. Fork the repository
2. Create a branch: `git checkout -b command/caf-org-my-command`
3. Add your command file(s)
4. Open a Pull Request with a short description:
   - Which CAF view and practice does it cover?
   - What input does it expect?
   - What does it produce?
   - Have you tested it on a real engagement (even partially)?

---

## Review criteria

A command will be accepted if it:

- Is grounded in a CAF view or practice documented on [continuous-architecture.org](https://continuous-architecture.org)
- Produces a useful, structured artifact that an architect would actually use
- Includes at least 3 quality gates
- Does not require the user to have coding skills to run it

---

## Questions

Open an issue or join the community on [LinkedIn](https://www.linkedin.com/company/continuous-architecture/).
