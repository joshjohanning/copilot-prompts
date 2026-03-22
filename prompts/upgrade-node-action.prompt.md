---
description: "Upgrade a GitHub Actions Node.js action from node20 to node24 with major version bump, CI updates, README updates, and full test run"
agent: "agent"
---

Upgrade this GitHub Actions JavaScript action from node20 to node24. This is a breaking change requiring a major version bump.

## Steps

1. **action.yml**: Change `runs.using` from `node20` to `node24`
2. **package.json**: Run `npm version major --no-git-tag-version` to bump to the next major version (e.g. 1.x.x -> 2.0.0). This also updates `package-lock.json` automatically. If `npm` is unavailable, manually edit the `version` field in both `package.json` and `package-lock.json`. Update `engines.node` to `>=24` if present.
3. **CI workflows**: Update all `node-version` values in `.github/workflows/` from `20` to `24`
4. **README.md**: Update usage examples to reference the new major version tag (e.g. `@v1` -> `@v2`). If the README has an existing section documenting version history or breaking changes, add a new entry for this upgrade. Otherwise, proceed without adding one.
5. **Other docs**: Search for and update any other references to the old version tag or node20 in markdown files, copilot-instructions, etc.
6. **Build and test**: Run `npm run all` (or equivalent) and confirm all tests pass. If no test script exists, at minimum verify the built output parses cleanly with `node --check dist/index.js` (or the entry point defined in `action.yml`).
7. **Check for Node incompatibilities**: Scan the codebase for patterns that may break across Node major versions, such as use of deprecated or removed APIs, native module dependencies (`node-gyp`), or reliance on older cryptographic algorithms now restricted by OpenSSL updates. Flag any potential issues found.
8. **Generate commit message and PR content**: Provide a conventional commit message, PR title, and PR body ready to copy and paste

## Guidelines

- Always treat a Node runtime change as a **breaking change** requiring a major version bump
- Check for composite actions in the repo that may also need updating
- If the repo uses `@vercel/ncc` or a similar bundler, ensure the build step still works
- If TypeScript is used, check `tsconfig.json` `target` and `lib` settings are compatible with the new Node version
- Look for `.node-version`, `.nvmrc`, or `.tool-versions` files that may also need updating
