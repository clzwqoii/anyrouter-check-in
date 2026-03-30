---
name: pre-commit-config-update
description: Workflow command scaffold for pre-commit-config-update in anyrouter-check-in.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /pre-commit-config-update

Use this workflow when working on **pre-commit-config-update** in `anyrouter-check-in`.

## Goal

Updates or optimizes pre-commit configuration, often via automated tools or minor manual tweaks.

## Common Files

- `.pre-commit-config.yaml`
- `.pre-commit-ci.yaml`
- `.vscode/settings.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update .pre-commit-config.yaml (either manually or via pre-commit.ci autoupdate)
- Optionally update related files like .pre-commit-ci.yaml or .vscode/settings.json

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.