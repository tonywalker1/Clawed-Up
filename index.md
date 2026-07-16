# Clawed-Up: Resource Index

Complete catalog of shareable Claude Code resources in this project.

## Guidelines

Reusable collaboration standards and configuration best practices.

- **[Collaboration Guidelines](guidelines/collaboration.md)** - Expert peer collaborator standards
  - Universal guidelines for Claude Code collaboration on projects
  - Three-phase workflow (Discuss → Propose → Execute) with clear autonomy levels
  - Prioritizes security/safety → simplicity → performance
  - Shareable across projects via integration command or manual copy
  - Example: Integrate with `/clawed-up:guidelines-collaboration`

## Guides

Workflow guides and tutorials for managing Claude Code configurations and collaboration.

- **[Version Control Guide](guides/version-control-claude.md)** - Version control your `~/.claude` directory
  - Track changes to your Claude Code configuration over time
  - Sync configurations across multiple machines
  - Share best practices with collaborators
  - Covers both existing setups and starting fresh
  - Includes production-tested `.gitignore` example
  - Quick start with private GitHub repository setup

- **[Reflection Workflow Guide](guides/reflection-workflow.md)** - Conduct collaboration reflections
  - Structured approach to capturing insights after substantial work
  - Four reflection prompts: what worked, what didn't, patterns, and CLAUDE.md updates
  - Git integration for version-controlled global configurations
  - Pairs well with `/clawed-up:git-finish-feature` for post-feature reflection
  - Used with `/clawed-up:reflect` skill for guided reflection sessions

## Configuration Skills

Skills for integrating guidelines and configuration into your Claude Code setup.

- **[`/clawed-up:guidelines-collaboration`](skills/guidelines-collaboration/SKILL.md)** - Integrate collaboration guidelines into CLAUDE.md
  - Intelligently integrates guidelines into global (`~/.claude/CLAUDE.md`) or project scope (`./.claude/CLAUDE.md`)
  - Includes three-phase workflow and autonomy levels
  - Detects existing guidelines and offers update/skip options
  - Defaults to global scope; use `--scope project` for project-specific integration
  - Example: `/clawed-up:guidelines-collaboration` or `/clawed-up:guidelines-collaboration --scope project`

## Git Skills

Skills for automating git workflow and feature branch management.

- **[`/clawed-up:git-start-feature`](skills/git-start-feature/SKILL.md)** - Create and check out a new feature branch
  - Auto-generates kebab-case branch names from description
  - Optionally pass `--branch-name <custom-name>` to use a custom branch name
  - Example: `/clawed-up:git-start-feature add user authentication`

- **[`/clawed-up:git-commit`](skills/git-commit/SKILL.md)** - Stage changes, write a commit message, and commit
  - Stages modified files and drafts a commit message with co-author attribution
  - Waits for your approval before committing
  - Useful for making incremental commits while developing a feature
  - Example: `/clawed-up:git-commit`

- **[`/clawed-up:git-finish-feature`](skills/git-finish-feature/SKILL.md)** - Complete a feature by committing, pushing, and creating a PR
  - Stages relevant files, drafts commit message and PR description
  - Creates a PR using `gh` after your approval
  - Example: `/clawed-up:git-finish-feature`

- **[`/clawed-up:git-cleanup-branch`](skills/git-cleanup-branch/SKILL.md)** - Clean up a feature branch after merging
  - Checks out main and deletes the local feature branch
  - Handles unpushed changes with safe force-delete option
  - Example: `/clawed-up:git-cleanup-branch`

- **[`/clawed-up:git-add-workflow-guidance`](skills/git-add-workflow-guidance/SKILL.md)** - Add git workflow best practices to CLAUDE.md
  - Integrates git workflow guidance into global or project CLAUDE.md
  - Reminds Claude Code to check branches before making changes
  - Provides context for using the git workflow commands
  - Example: `/clawed-up:git-add-workflow-guidance` or `/clawed-up:git-add-workflow-guidance --scope project`

## Documentation Skills

Skills for auditing, maintaining, and improving project documentation.

- **[`/clawed-up:audit-docs`](skills/audit-docs/SKILL.md)** - Audit documentation for alignment with code
  - Examines codebase and all documentation to identify architectural, implementation, and content misalignments
  - Checks for API/function coverage, terminology consistency, and audience accessibility
  - Makes direct edits to fix identified issues
  - Example: `/clawed-up:audit-docs` or `/clawed-up:audit-docs src/ lib/`

- **[`/clawed-up:write-docs`](skills/write-docs/SKILL.md)** - Automation-first documentation procedure
  - Write the script first, then document it — the script is canonical, docs explain "why" and "when"
  - Prevents documentation drift by keeping automation as the single source of truth
  - Provides a template for referencing scripts instead of duplicating their steps
  - Example: `/clawed-up:write-docs`

## Troubleshooting Skills

Skills for evidence-based debugging and infrastructure change verification.

- **[`/clawed-up:troubleshoot`](skills/troubleshoot/SKILL.md)** - Evidence-based troubleshooting with pivot recognition
  - Recognizes pivot signals: identical errors across "should work" configs, hours stuck with no progress, repeated
    reinstalls failing identically
  - On pivot: documents what was tried, proposes a fundamentally different solution, explains trade-offs, and gets
    approval before architecture changes
  - Distinguishes debugging configuration from recognizing upstream bugs or bad environmental assumptions
  - Example: `/clawed-up:troubleshoot`

- **[`/clawed-up:verify-change`](skills/verify-change/SKILL.md)** - Verify infrastructure changes before making updates
  - Confirms understanding and asks for the "why" (current state vs. aspirational vs. clarification) before acting
  - Requests concrete evidence (command output, config files) instead of relying on descriptions
  - Updates in minimal scope, checking for downstream effects before touching multiple locations
  - Example: `/clawed-up:verify-change`

## Collaboration Skills

Skills for improving collaboration and capturing insights from your work.

- **[`/clawed-up:reflect`](skills/reflect/SKILL.md)** - Conduct a collaboration reflection after completing substantial work
  - Capture what went well, what didn't work, and patterns worth remembering
  - Suggest updates to your `CLAUDE.md` files based on insights
  - Improve future collaboration by refining your context
  - See [Reflection Workflow Guide](guides/reflection-workflow.md) for detailed guidance
  - Example: `/clawed-up:reflect`

## Prompts

*Coming soon*

## Utilities

*Coming soon*

---

**Using these resources in other projects:**

Install the plugin, then invoke its skills from any project:

```bash
/plugin marketplace add tonywalker1/Clawed-Up
/plugin install clawed-up@clawed-up
```

For detailed usage instructions, see [CLAUDE.md](CLAUDE.md).
