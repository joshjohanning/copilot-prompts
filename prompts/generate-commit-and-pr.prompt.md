---
description: 'Generate a conventional commit message, PR title, and PR body'
agent: "agent"
---

Generate a conventional commit message, PR title, and PR body for the current branch's changes.

## Conventional Commit Format

```
<type>(<optional scope>): <description>

<optional body>
```

## Rules

### Commit Message

- Use one of these types: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`
- Keep the subject line under 72 characters
- Use the imperative mood ("add feature" not "added feature")
- Do not end the subject line with a period
- Use the body to explain **what** and **why**, not **how**
- If the change is simple, a subject line alone is sufficient

### PR Title

- Same format as the commit subject line
- If there is a single commit, base the title on that commit message
- If there are multiple commits, summarize the overall intent

### PR Body

- Write in markdown
- Start with a brief summary of what the PR does
- Use a `## Changes` section with a bulleted list of key changes
- If applicable, include a `## Why` section explaining the motivation
- Keep it concise -- what changed and why, not how
- Skip boilerplate sections that aren't relevant

## Steps

1. Look at the commits on this branch vs the default branch (use `git log --oneline main..HEAD` or `git log --oneline master..HEAD`)
2. Look at the diff (use `git diff main..HEAD` or `git diff master..HEAD`); for staged-only changes use `git diff --staged`
3. Generate all three outputs below

## Output Format

Provide the output in this exact structure with each section in its own markdown code block for easy copy and paste:

### Commit Message

```
<commit message here>
```

### PR Title

```
<PR title here>
```

### PR Body

```markdown
<PR body here>
```
