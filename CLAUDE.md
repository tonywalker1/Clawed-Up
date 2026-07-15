# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal repository called "Clawed-Up" containing shareable Claude Code resources and documentation
related to Claude, other LLMs, and AI development workflows. The repository is **primarily documentation-focused**
with no build system, testing frameworks, or compiled artifacts. The target audience includes the project maintainer,
Claude Code itself, and a small circle of computing-expert collaborators.

The repository's skills are packaged as a single Claude Code plugin (`.claude-plugin/plugin.json` and
`marketplace.json`), installable with `/plugin marketplace add tonywalker1/Clawed-Up` and
`/plugin install clawed-up@clawed-up`. Once installed, skills are namespaced as `/clawed-up:<skill-name>`.
Guides, guidelines, and examples remain plain markdown outside the plugin (plugins only package executable
components like skills, agents, and hooks).

## Collaboration Guidelines

Claude Code acts as an **expert peer collaborator** on this project. This means:

- Ask clarifying questions about goals, constraints, and tradeoffs
- Actively challenge questionable design decisions with specific concerns
- Push back on requests when you identify better approaches
- Assume domain knowledge and keep explanations concise
- Prioritize architectural decisions in this order: security/safety → simplicity → performance

**Sharing These Guidelines**: These collaboration guidelines are also available as a standalone, shareable resource at [`guidelines/collaboration.md`](guidelines/collaboration.md). The full guidelines include a three-phase workflow (Discuss → Propose → Execute), communication preferences, and clear autonomy levels. You can integrate them into your global `~/.claude/CLAUDE.md` using the `/clawed-up:guidelines-collaboration` slash command (once the plugin is installed).

## Git Workflow

When working on this project:

- **Starting work**: Before making changes, check current branch with `git branch --show-current`
  - If on main/master and working on a feature or non-trivial change, create a feature branch first using `/clawed-up:git-start-feature`
- **Incremental commits**: Use `/clawed-up:git-commit` for commits during development (handles staging, message drafting, co-author attribution)
- **Completing features**: Use `/clawed-up:git-finish-feature` to commit, push, and create a PR
- **After merge**: Use `/clawed-up:git-cleanup-branch` to clean up the local feature branch

**Note:** For projects that commit directly to main, `/clawed-up:git-commit` will offer the choice to proceed on main or create a feature branch.

## Repository Structure

- `.claude-plugin/` - Plugin manifest (`plugin.json`) and marketplace catalog (`marketplace.json`)
- `skills/` - Custom skills for feature workflow automation (the plugin's skill directory)
- `guides/` - Workflow guides and tutorials
- `guidelines/` - Collaboration frameworks and best practices
- `examples/` - Production-tested configuration examples
- `LICENSE` - Project license
- `README.md` - Basic project description
- `.gitignore` - Git ignore rules

## Documentation Maintenance

When adding new resources:

1. **Create content** in the appropriate subdirectory (`skills/`, `guides/`, `guidelines/`, `examples/`)
2. **Update index.md**:
   - Add entry to the relevant section (Guides, Skills, etc.)
   - Include bullet points describing key features/capabilities
   - Show usage examples where applicable
3. **Update README.md**:
   - Add high-level mention in "What's Included" section
   - Keep descriptions concise (one line per category)
4. **Update CLAUDE.md** (this file):
   - If it's a skill, add to the skills section with usage examples
   - If it's a guide, add to relevant section with brief description

This ensures resources are discoverable through multiple navigation paths.

## Development

Since this is a documentation-focused repository, there is no build system, testing framework, or compiled
artifacts. Documentation should be clear, well-organized, and accessible to both technical experts and general
users interested in Claude Code resources.

## Using Shareable Resources

This repository provides reusable Claude Code resources that can be integrated into other projects. Skills are
packaged as the `clawed-up` plugin; guides and guidelines are plain markdown you copy or curl as needed.

### Integrating Collaboration Guidelines

The collaboration guidelines defined in this project are available as a standalone resource in
[`guidelines/collaboration.md`](guidelines/collaboration.md). To integrate them into your
global Claude configuration:

**Option 1: Using the skill (recommended)**
```bash
/plugin marketplace add tonywalker1/Clawed-Up
/plugin install clawed-up@clawed-up
/clawed-up:guidelines-collaboration                    # Global scope (default)
/clawed-up:guidelines-collaboration --scope project    # Project scope
```
This skill will intelligently integrate the guidelines into your CLAUDE.md, checking for existing guidelines
and offering to update if needed. Use `--scope global` (default) to integrate into `~/.claude/CLAUDE.md` for
use across all projects, or `--scope project` to integrate into your current project's `.claude/CLAUDE.md`.

**Option 2: Manual integration**
```bash
curl https://raw.githubusercontent.com/tonywalker1/Clawed-Up/main/guidelines/collaboration.md >> ~/.claude/CLAUDE.md
```

Global guidelines apply to all your projects unless overridden by a project-level `CLAUDE.md` file.

## Shareable Skills and Guides

This project includes custom skills and workflow guides designed for reuse across projects. Skills install as
the `clawed-up` plugin (see [Quick Start](README.md#quick-start)); guides live in `guides/` and are referenced
directly.

### Git Workflow Skills

Automate feature branch creation, commits, and pull requests:

- **`/clawed-up:git-start-feature [description]`** - Create and check out a new feature branch
  - Auto-generates kebab-case branch names from description
  - Optionally pass `--branch-name <custom-name>` to use a custom branch name
  - Updates main branch before creating the feature branch

- **`/clawed-up:git-commit`** - Stage changes, write a commit message, and commit
  - Stages modified files related to your current work
  - Drafts a commit message with co-author attribution
  - Waits for your approval before committing
  - Useful for making incremental commits while developing a feature

- **`/clawed-up:git-finish-feature`** - Complete a feature by committing, pushing, and creating a PR
  - Stages relevant files, drafts commit message and PR description
  - Waits for your approval before committing and pushing
  - Creates a PR using `gh`

- **`/clawed-up:git-cleanup-branch`** - Clean up a feature branch after merging
  - Checks out main and deletes the local feature branch
  - Handles unpushed changes with a force-delete option
  - Keeps your local workspace tidy

### Collaboration and Reflection

Structured approaches to improving collaboration and capturing insights:

- **`/clawed-up:reflect`** - Conduct a collaboration reflection after completing substantial work
  - Capture what went well, what didn't work, and patterns worth remembering
  - Suggest updates to your `CLAUDE.md` files based on insights
  - Improve future collaboration by refining your context
  - See [Reflection Workflow Guide](guides/reflection-workflow.md) for detailed usage

### Configuration Management

Guides for managing your Claude Code configuration:

- **[Version Control Guide](guides/version-control-claude.md)** - Version control your `~/.claude`
  directory
  - Track changes to your Claude Code configuration over time
  - Sync configurations across multiple machines
  - Share best practices with collaborators
  - Covers both existing setups and starting fresh

**Using These Skills in Other Projects**:

Install the plugin once, and its skills are available in every project:

```bash
/plugin marketplace add tonywalker1/Clawed-Up
/plugin install clawed-up@clawed-up
```

**Conventions**:
- Commit messages use imperative mood ("Add feature", not "Added feature")
- Include co-author attribution: `Co-Authored-By: Claude <noreply@anthropic.com>`
- Subject lines under 72 characters; use body for details when needed
- PR review and merge remain manual (you handle approval/merge on GitHub)

## Contributing

Contributions to this repository should maintain the documentation-first philosophy and be well-organized for easy
discovery. All contributions should:

- Follow the established directory structure and naming conventions
- Include clear documentation or comments explaining the purpose of resources
- Be tested (or provide clear testing instructions) before submission
- Respect the 120-column word wrap convention in all markdown files
- Use the git workflow automation skills for feature development

See [CONTRIBUTING.md](CONTRIBUTING.md) for specific guidelines on submitting contributions.

## Contributors

See [CONTRIBUTORS.md](CONTRIBUTORS.md) for a list of contributors and acknowledgments.
