# AI-Native Engineering Toolkit

A small, reusable toolkit for managing AI-assisted software projects. It contains **process guidance**, not a ready-made solution to any assessment or task.

## Contents

- `AGENTS.md` — core project workflow and guardrails
- `workflows/requirements.md` — discovering missing requirements and stakeholder questions
- `workflows/verification.md` — proving end-to-end functionality
- `templates/WORK_LOG.md` — traceable evidence of work, decisions, tests and limitations
- `templates/DECISION_LOG.md` — alternative comparisons and design trade-offs

## Quick start

Clone the public branch:

```bash
git clone --depth 1 --single-branch -b ai-native-toolkit https://github.com/Ululu00/Ululu00.git /tmp/ai-native-toolkit
```

From your **actual project workspace**:

1. Read `/tmp/ai-native-toolkit/toolkit/AGENTS.md`, `workflows/requirements.md`, and `workflows/verification.md`.
2. Follow the current project's README, existing project instructions and environment rules first.
3. To make Codex load these rules as project guidance, copy `toolkit/AGENTS.md` to the project root **only if doing so does not overwrite or conflict with existing instructions**. Otherwise, explicitly ask Codex to read the toolkit files as reference.
4. Do **not** copy example answers, assume requirements, or upload any local project material to this repository.

### Starter prompt for Codex

> Read the current project README, code and data, and the reference workflow files under `/tmp/ai-native-toolkit/toolkit/`. Do not modify code yet. Identify confirmed facts, unknowns that could change architecture or business logic, the three to five highest-impact stakeholder questions, and a small verifiable first implementation slice. Explain why each proposed question matters. Pause for my decisions before choosing important business rules.

Use only tools and public sources permitted in your current environment. Network access and repository availability may vary; the project must remain solvable without this toolkit.
