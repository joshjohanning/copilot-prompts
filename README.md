# copilot-prompts

A collection of reusable [VS Code Copilot prompt files](https://code.visualstudio.com/docs/copilot/copilot-customization#_reusable-prompt-files) (`.prompt.md`) and [instruction files](https://code.visualstudio.com/docs/copilot/copilot-customization#_instruction-files) (`.instructions.md`) for GitHub Copilot.

## What are prompt files and instruction files?

- **Prompt files** (`.prompt.md`) are reusable prompts you invoke on demand in Copilot Chat. Think of them as saved workflows or recipes.
- **Instruction files** (`.instructions.md`) are automatically attached to Copilot Chat based on glob patterns (e.g., all `.yml` files, all `.sh` files). They provide persistent context without you having to repeat yourself.

Both file types can be placed at the **user level** (applies across all projects) or at the **repo level** (scoped to a specific project).

## Prompts

| File | Description |
|------|-------------|
| [`generate-commit-and-pr.prompt.md`](prompts/generate-commit-and-pr.prompt.md) | Generate a conventional commit message, PR title, and PR body from the current branch's changes |
| [`generate-commit.prompt.md`](prompts/generate-commit.prompt.md) | Generate a conventional commit message for staged or branch changes |
| [`upgrade-node-action.prompt.md`](prompts/upgrade-node-action.prompt.md) | Upgrade a GitHub Actions Node.js action from node20 to node24 with version bumps, CI updates, and tests |
| [`weekly-snippets.prompt.md`](prompts/weekly-snippets.prompt.md) | Compile weekly snippets from GitHub activity for status updates |

## Instructions

| File | Applies To | Description |
|------|------------|-------------|
| [`md.instructions.md`](instructions/md.instructions.md) | Markdown and text files (`**/*.{md,txt}`) | Do not use emdashes or AI speak |
| [`shell.instructions.md`](instructions/shell.instructions.md) | Shell scripts (`**/*.sh`) | Shell script conventions (2-space indent, input params, usage docs) |
| [`yml.instructions.md`](instructions/yml.instructions.md) | YAML files (`**.yml`) | Extra line breaks between major sections in GitHub Actions workflows |

## Installation

### User-level (all projects)

Copy prompt and instruction files to your VS Code user prompts folder:

- **macOS**: `~/Library/Application Support/Code/User/prompts/`
- **Linux**: `~/.config/Code/User/prompts/`
- **Windows**: `%APPDATA%\Code\User\prompts\`

### Repo-level (single project)

Copy files into your repository's `.github/prompts/` directory. This makes them available to anyone working in that repo.

## Usage

1. Open Copilot Chat in VS Code
2. Type `/` to see available prompt files, or start typing the prompt name
3. Select the prompt you want to run

For instruction files, there's nothing to do. They are automatically included when Copilot Chat is working with files that match the `applyTo` glob pattern.

## Customization

These prompts are starting points. Fork this repo and customize them to fit your workflow:

- Update `weekly-snippets.prompt.md` with your own repos and exclusion filters
- Adjust the conventional commit types in the commit prompts
- Add your own instruction files for languages or frameworks you use

## Contributing

Have a useful prompt or instruction file? PRs are welcome!

## Resources

- [VS Code Copilot Customization docs](https://code.visualstudio.com/docs/copilot/copilot-customization)
- [Prompt files documentation](https://code.visualstudio.com/docs/copilot/copilot-customization#_reusable-prompt-files)
- [Instruction files documentation](https://code.visualstudio.com/docs/copilot/copilot-customization#_instruction-files)
