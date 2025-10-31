# Clawed-Up: Resource Index

Complete catalog of shareable Claude Code resources in this project.

## Guidelines

Reusable collaboration standards and configuration best practices.

- **[Collaboration Guidelines](claude/guidelines/collaboration.md)** - Expert peer collaborator standards
  - Universal guidelines for Claude Code collaboration on projects
  - Covers asking clarifying questions, challenging design decisions, and prioritizing security/safety
  - Shareable across projects via integration command or manual copy
  - Example: Integrate with `/integrate-collaboration-guidelines`

## Configuration Commands

Slash commands for integrating guidelines and configuration into your Claude Code setup.

- **[`/integrate-collaboration-guidelines`](claude/commands/integrate-collaboration-guidelines.md)** - Integrate collaboration guidelines into CLAUDE.md
  - Intelligently integrates guidelines into global (`~/.claude/CLAUDE.md`) or project scope (`./.claude/CLAUDE.md`)
  - Detects existing guidelines and offers update/skip options
  - Defaults to global scope; use `--scope project` for project-specific integration
  - Example: `/integrate-collaboration-guidelines` or `/integrate-collaboration-guidelines --scope project`

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

## Documentation Commands

Slash commands for auditing, maintaining, and improving project documentation.

- **[`/audit-docs`](claude/commands/audit-docs.md)** - Audit documentation for alignment with code
  - Examines codebase and all documentation to identify architectural, implementation, and content misalignments
  - Checks for API/function coverage, terminology consistency, and audience accessibility
  - Makes direct edits to fix identified issues
  - Example: `/audit-docs` or `/audit-docs src/ lib/`

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
