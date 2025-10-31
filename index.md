# Clawed-Up: Resource Index

Complete catalog of shareable Claude Code resources in this project.

## Git Commands

Slash commands for automating git workflow and feature branch management.

- **[`/git-start-feature`](claude/commands/git-start-feature.md)** - Create and check out a new feature branch
  - Auto-generates kebab-case branch names from description
  - Optionally pass `--branch-name <custom-name>` to use a custom branch name
  - Example: `/git-start-feature add user authentication`

- **[`/git-finish-feature`](claude/commands/git-finish-feature.md)** - Complete a feature by committing, pushing, and creating a PR
  - Stages relevant files, drafts commit message and PR description
  - Creates a PR using `gh` after your approval
  - Example: `/git-finish-feature`

## Prompts

*Coming soon*

## Utilities

*Coming soon*

---

**Using these resources in other projects:**

Copy the files from this repository to your project's `.claude/` directory:

```bash
# Copy specific resources
cp -r claude/commands/* /path/to/your-project/.claude/commands/
```

For detailed usage instructions, see [CLAUDE.md](CLAUDE.md).
