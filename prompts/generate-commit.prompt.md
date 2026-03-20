---
description: "Generate a conventional commit message for staged or branch changes"
agent: "agent"
---

Generate a conventional commit message for the current changes.

## Conventional Commit Format

```
<type>(<optional scope>): <description>

<optional body>
```

## Rules

- Use one of these types: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`
- Keep the subject line under 72 characters
- Use the imperative mood ("add feature" not "added feature")
- Do not end the subject line with a period
- Use the body to explain **what** and **why**, not **how**
- If the change is simple, a subject line alone is sufficient
- Wrap body lines at 72 characters
- Separate subject from body with a blank line
