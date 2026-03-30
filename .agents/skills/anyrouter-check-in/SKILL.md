```markdown
# anyrouter-check-in Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you how to contribute to the `anyrouter-check-in` Python project, which automates check-in and notification tasks for various services. You'll learn the project's coding conventions, how to implement new features, update notification channels, maintain documentation, configure pre-commit hooks, and ensure PR quality checks. The guide also covers testing patterns and provides handy commands for common workflows.

## Coding Conventions

- **File Naming:**  
  Use `camelCase` for Python files.  
  *Example:*  
  ```
  checkin.py
  utils/notify.py
  ```

- **Import Style:**  
  Use **relative imports** within the package.  
  *Example:*  
  ```python
  from .config import get_config
  from ..utils.notify import send_notification
  ```

- **Export Style:**  
  Use **named exports** (explicit function/class definitions).  
  *Example:*  
  ```python
  def send_notification(...):
      ...
  ```

- **Commit Messages:**  
  Use prefixes such as `feat`, `fix`, `docs`, `refactor`, `chore`.  
  Keep messages concise (~30 characters).  
  *Example:*  
  ```
  feat: add telegram notification support
  fix: correct env variable parsing
  docs: update usage instructions
  ```

## Workflows

### Add or Enhance Notification Channel
**Trigger:** When adding or improving a notification channel integration (e.g., Bark, Gotify, Telegram)  
**Command:** `/add-notification-channel`

1. Implement notification logic in `utils/notify.py`.
2. Add or update the environment variable example in `.env.example`.
3. Update the GitHub Actions workflow in `.github/workflows/checkin.yml` to support the new env variable.
4. Update documentation in `README.md`.
5. Add or update tests in `tests/test_notify.py` (if applicable).

*Example snippet (utils/notify.py):*
```python
def send_telegram_notification(token, chat_id, message):
    # Implementation here
    ...
```

---

### Pre-commit Config Update
**Trigger:** When upgrading, optimizing, or fixing pre-commit hooks or related settings  
**Command:** `/update-pre-commit`

1. Update `.pre-commit-config.yaml` (manually or via `pre-commit.ci autoupdate`).
2. Optionally update related files like `.pre-commit-ci.yaml` or `.vscode/settings.json`.

*Example snippet (.pre-commit-config.yaml):*
```yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.3.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
```

---

### Documentation Update
**Trigger:** When clarifying, correcting, or enhancing documentation  
**Command:** `/update-docs`

1. Edit `README.md` (as a standalone commit or with feature changes).

---

### Add or Update PR Quality Checks
**Trigger:** When improving or introducing PR review standards and automation  
**Command:** `/add-pr-checks`

1. Edit or add `.github/pull_request_template.md`.
2. Edit or add `.github/workflows/pr-check.yml`.
3. Edit or add `.codecov.yml`, `.pre-commit-config.yaml`, `.pre-commit-ci.yaml`.
4. Update `CONTRIBUTING.md` and/or `README.md`.
5. Update `pyproject.toml` if needed.

---

### Feature Implementation with Config and Docs
**Trigger:** When adding a new core feature or significant enhancement  
**Command:** `/add-feature`

1. Implement the feature in `checkin.py` and/or `utils/config.py`.
2. Update `README.md` to document the feature.
3. Update or add relevant configuration in `.env.example`.

*Example snippet (checkin.py):*
```python
def new_feature():
    # Feature logic here
    ...
```

## Testing Patterns

- **Framework:** Not explicitly specified; use standard Python testing tools (e.g., `unittest`, `pytest`).
- **Test File Pattern:** Files are named with `.test.` in the filename, e.g., `test_notify.py`.
- **Location:** Tests are placed in the `tests/` directory.
- **Example:**
  ```python
  # tests/test_notify.py
  def test_send_notification():
      assert send_notification("test") is True
  ```

## Commands

| Command                    | Purpose                                                        |
|----------------------------|----------------------------------------------------------------|
| /add-notification-channel  | Add or enhance a notification channel integration              |
| /update-pre-commit         | Update or optimize pre-commit configuration                    |
| /update-docs               | Update or enhance documentation                                |
| /add-pr-checks             | Add or update PR quality check configurations and templates    |
| /add-feature               | Implement a new feature with config and documentation updates  |
```
