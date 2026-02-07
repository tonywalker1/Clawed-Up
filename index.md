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

## Guides

Workflow guides and tutorials for managing Claude Code configurations and collaboration.

- **[Version Control Guide](claude/guides/version-control-claude.md)** - Version control your `~/.claude` directory
  - Track changes to your Claude Code configuration over time
  - Sync configurations across multiple machines
  - Share best practices with collaborators
  - Covers both existing setups and starting fresh
  - Includes production-tested `.gitignore` example
  - Quick start with private GitHub repository setup

- **[Reflection Workflow Guide](claude/guides/reflection-workflow.md)** - Conduct collaboration reflections
  - Structured approach to capturing insights after substantial work
  - Four reflection prompts: what worked, what didn't, patterns, and CLAUDE.md updates
  - Git integration for version-controlled global configurations
  - Pairs well with `/git-finish-feature` for post-feature reflection
  - Used with `/reflect` skill for guided reflection sessions

## Configuration Skills

Skills for integrating guidelines and configuration into your Claude Code setup.

- **[`/guidelines-collaboration`](claude/skills/guidelines-collaboration/SKILL.md)** - Integrate collaboration guidelines into CLAUDE.md
  - Intelligently integrates guidelines into global (`~/.claude/CLAUDE.md`) or project scope (`./.claude/CLAUDE.md`)
  - Includes three-phase workflow, communication preferences, and autonomy levels
  - Detects existing guidelines and offers update/skip options
  - Defaults to global scope; use `--scope project` for project-specific integration
  - Example: `/guidelines-collaboration` or `/guidelines-collaboration --scope project`

## Git Skills

Skills for automating git workflow and feature branch management.

- **[`/git-start-feature`](claude/skills/git-start-feature/SKILL.md)** - Create and check out a new feature branch
  - Auto-generates kebab-case branch names from description
  - Optionally pass `--branch-name <custom-name>` to use a custom branch name
  - Example: `/git-start-feature add user authentication`

- **[`/git-commit`](claude/skills/git-commit/SKILL.md)** - Stage changes, write a commit message, and commit
  - Stages modified files and drafts a commit message with co-author attribution
  - Waits for your approval before committing
  - Useful for making incremental commits while developing a feature
  - Example: `/git-commit`

- **[`/git-finish-feature`](claude/skills/git-finish-feature/SKILL.md)** - Complete a feature by committing, pushing, and creating a PR
  - Stages relevant files, drafts commit message and PR description
  - Creates a PR using `gh` after your approval
  - Example: `/git-finish-feature`

- **[`/git-cleanup-branch`](claude/skills/git-cleanup-branch/SKILL.md)** - Clean up a feature branch after merging
  - Checks out main and deletes the local feature branch
  - Handles unpushed changes with safe force-delete option
  - Example: `/git-cleanup-branch`

- **[`/git-add-workflow-guidance`](claude/skills/git-add-workflow-guidance/SKILL.md)** - Add git workflow best practices to CLAUDE.md
  - Integrates git workflow guidance into global or project CLAUDE.md
  - Reminds Claude Code to check branches before making changes
  - Provides context for using the git workflow commands
  - Example: `/git-add-workflow-guidance` or `/git-add-workflow-guidance --scope project`

## Documentation Skills

Skills for auditing, maintaining, and improving project documentation.

- **[`/audit-docs`](claude/skills/audit-docs/SKILL.md)** - Audit documentation for alignment with code
  - Examines codebase and all documentation to identify architectural, implementation, and content misalignments
  - Checks for API/function coverage, terminology consistency, and audience accessibility
  - Makes direct edits to fix identified issues
  - Example: `/audit-docs` or `/audit-docs src/ lib/`

## Collaboration Skills

Skills for improving collaboration and capturing insights from your work.

- **[`/reflect`](claude/skills/reflect/SKILL.md)** - Conduct a collaboration reflection after completing substantial work
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
cp -r claude/skills/* /path/to/your-project/.claude/skills/
```

For detailed usage instructions, see [CLAUDE.md](CLAUDE.md).
