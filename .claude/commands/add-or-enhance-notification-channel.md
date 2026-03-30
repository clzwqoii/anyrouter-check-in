---
name: add-or-enhance-notification-channel
description: Workflow command scaffold for add-or-enhance-notification-channel in anyrouter-check-in.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-enhance-notification-channel

Use this workflow when working on **add-or-enhance-notification-channel** in `anyrouter-check-in`.

## Goal

Adds support for a new notification channel (e.g., Bark, Gotify, Telegram) or enhances an existing one, including environment variable, workflow, documentation, and tests.

## Common Files

- `utils/notify.py`
- `.env.example`
- `.github/workflows/checkin.yml`
- `README.md`
- `tests/test_notify.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement notification logic in utils/notify.py
- Add or update environment variable example in .env.example
- Update GitHub Actions workflow to support new env variable in .github/workflows/checkin.yml
- Update documentation in README.md
- Add or update tests in tests/test_notify.py (if applicable)

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.