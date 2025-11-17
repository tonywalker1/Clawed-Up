# Clawed-Up: Resource Index

Complete catalog of shareable Claude Code resources in this project.

## Guidelines

Reusable collaboration standards and configuration best practices.

- **[Collaboration Guidelines](claude/guidelines/collaboration.md)** - Expert peer collaborator standards
  - Universal guidelines for Claude Code collaboration on projects
  - Three-phase workflow (Discuss → Propose → Execute) with clear autonomy levels
  - Communication preferences and execution style guidance
  - Prioritizes security/safety → simplicity → performance
  - Shareable across projects via integration command or manual copy
  - Example: Integrate with `/guidelines-collaboration`

## Configuration Commands

Slash commands for integrating guidelines and configuration into your Claude Code setup.

- **[`/guidelines-collaboration`](claude/commands/guidelines-collaboration.md)** - Integrate collaboration guidelines into CLAUDE.md
  - Intelligently integrates guidelines into global (`~/.claude/CLAUDE.md`) or project scope (`./.claude/CLAUDE.md`)
  - Includes three-phase workflow, communication preferences, and autonomy levels
  - Detects existing guidelines and offers update/skip options
  - Defaults to global scope; use `--scope project` for project-specific integration
  - Example: `/guidelines-collaboration` or `/guidelines-collaboration --scope project`

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

## Collaboration Commands

Slash commands for improving collaboration and capturing insights from your work.

- **[`/reflect`](claude/commands/reflect.md)** - Conduct a collaboration reflection after completing substantial work
  - Capture what went well, what didn't work, and patterns worth remembering
  - Suggest updates to your `CLAUDE.md` files based on insights
  - Improve future collaboration by refining your context
  - See [Reflection Workflow Guide](claude/guides/reflection-workflow.md) for detailed guidance
  - Example: `/reflect`

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
