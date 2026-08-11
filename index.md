# Clawed-Up: Resource Index

Complete catalog of shareable Claude Code resources in this project.

## Guidelines

Reusable collaboration standards and configuration best practices.

- **[Collaboration Guidelines](guidelines/collaboration.md)** - Expert peer collaborator standards
  - Universal guidelines for Claude Code collaboration on projects
  - Three-phase workflow (Discuss → Propose → Execute) with clear autonomy levels
  - Prioritizes security/safety → simplicity → performance
  - Grounding claims in evidence: distinguishing current from aspirational state, preferring command output
    over description, correcting in minimal scope
  - Pivot recognition: when identical failures across correct configurations mean the problem is upstream
  - Copy into a `CLAUDE.md` (global or project) to adopt it

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
  - Four reflection areas: what worked, what didn't, patterns, and what to persist
  - Routing insights between memory files and `CLAUDE.md`
  - Git integration for version-controlled global configuration
  - Used with the `/clawed-up:reflect` skill for guided reflection sessions

## Skills

Skills packaged in the `clawed-up` plugin. Both cover ground Claude Code does not handle on its own.

- **[`/clawed-up:audit-docs`](skills/audit-docs/SKILL.md)** - Find and fix drift between docs and reality
  - Establishes what is true from code and configs *before* reading docs, so stale docs cannot anchor the audit
  - Enforces a specific standard: single source of truth, script-is-canonical, absolute paths, real command
    output, consistent terminology, 120-column wrap
  - Prioritizes removed and renamed references — the drift that actively misleads readers
  - Makes edits directly, and reports what it could not fix alone rather than skipping it
  - Example: `/clawed-up:audit-docs` or `/clawed-up:audit-docs src/ lib/`

- **[`/clawed-up:reflect`](skills/reflect/SKILL.md)** - Deliberate end-of-session retrospective
  - Reconstructs the session from git history rather than from recall
  - Presses on what didn't work — the friction is the signal
  - Routes each insight to the right home: memory files for how to work with you, `CLAUDE.md` for rules any
    collaborator would need, nowhere for what the code already records
  - Prunes memories that turned out to be wrong, not just adds new ones
  - Offers to commit if `~/.claude` is version controlled
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

Guidelines and guides are plain markdown — copy them where you need them.

For detailed usage instructions, see [CLAUDE.md](CLAUDE.md).
