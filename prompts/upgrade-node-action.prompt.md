---
description: "Upgrade a GitHub Actions Node.js action from node20 to node24 with major version bump, CI updates, README updates, and full test run"
agent: "agent"
---

Upgrade this GitHub Actions JavaScript action from node20 to node24. This is a breaking change requiring a major version bump.

## Steps

1. **action.yml**: Change `runs.using` from `node20` to `node24`
2. **package.json**: Bump to the next major version (e.g. 1.x.x -> 2.0.0, 2.x.x -> 3.0.0) and update `engines.node` to `>=24`
3. **CI workflows**: Update all `node-version` values in `.github/workflows/` from `20` to `24`
4. **README.md**: Update usage examples to reference the new major version tag (e.g. `@v1` -> `@v2`). Add a "What's new" section after the description if one doesn't exist:
   ```markdown
   ## What's new

   Please refer to the [release page](<repo-releases-url>) for the latest release notes.
   ```
5. **Other docs**: Search for and update any other references to the old version tag or node20 in markdown files, copilot-instructions, etc.
6. **Sync lockfile**: Run `npm install` to update `package-lock.json`
7. **Full build and test**: Run `npm run all` (or equivalent) and confirm all tests pass
8. **Generate commit message and PR content**: Provide a conventional commit message, PR title, and PR body ready to copy and paste
