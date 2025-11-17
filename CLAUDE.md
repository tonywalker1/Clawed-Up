# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal repository called "Clawed-Up" containing shareable Claude Code resources and documentation
related to Claude, other LLMs, and AI development workflows. The repository is **primarily documentation-focused**
with no build system, testing frameworks, or compiled artifacts. The target audience includes the project maintainer,
Claude Code itself, and a small circle of computing-expert collaborators.

## Collaboration Guidelines

Claude Code acts as an **expert peer collaborator** on this project. This means:

- Ask clarifying questions about goals, constraints, and tradeoffs
- Actively challenge questionable design decisions with specific concerns
- Push back on requests when you identify better approaches
- Assume domain knowledge and keep explanations concise
- Prioritize architectural decisions in this order: security/safety → simplicity → performance

**Sharing These Guidelines**: These collaboration guidelines are also available as a standalone, shareable resource at [`claude/guidelines/collaboration.md`](claude/guidelines/collaboration.md). The full guidelines include a three-phase workflow (Discuss → Propose → Execute), communication preferences, and clear autonomy levels. You can integrate them into your global `~/.claude/CLAUDE.md` using the `/guidelines-collaboration` slash command.

## Repository Structure

This is a new repository with basic structure:

- `.idea/` - IntelliJ IDEA configuration files
- `claude/` - Shareable Claude Code resources
  - `commands/` - Custom slash commands for feature workflow automation
- `LICENSE` - Project license
- `README.md` - Basic project description
- `.gitignore` - Git ignore rules (currently ignoring .idea directory)

## Development

Since this is a documentation-focused repository, there is no build system, testing framework, or compiled
artifacts. Documentation should be clear, well-organized, and accessible to both technical experts and general
users interested in Claude Code resources.

## Using Shareable Resources

This repository provides reusable Claude Code resources that can be integrated into other projects. Resources
are stored in `claude/` and include collaboration guidelines and automation commands.

### Integrating Collaboration Guidelines

The collaboration guidelines defined in this project are available as a standalone resource in
[`claude/guidelines/collaboration.md`](claude/guidelines/collaboration.md). To integrate them into your
global Claude configuration:

**Option 1: Using the slash command (recommended)**
```bash
/guidelines-collaboration                    # Global scope (default)
/guidelines-collaboration --scope project    # Project scope
```
This command will intelligently integrate the guidelines into your CLAUDE.md, checking for existing guidelines
and offering to update if needed. Use `--scope global` (default) to integrate into `~/.claude/CLAUDE.md` for
use across all projects, or `--scope project` to integrate into your current project's `.claude/CLAUDE.md`.

**Option 2: Manual integration**
```bash
curl https://raw.githubusercontent.com/tonywalker1/Clawed-Up/main/claude/guidelines/collaboration.md >> ~/.claude/CLAUDE.md
```

Global guidelines apply to all your projects unless overridden by a project-level `CLAUDE.md` file.

## Shareable Commands and Guides

This project includes custom slash commands and workflow guides designed for reuse across projects. These are
stored in `claude/commands/` and `claude/guides/` and can be easily integrated into other projects.

### Git Workflow Commands

Automate feature branch creation, commits, and pull requests:

- **`/git-start-feature [description]`** - Create and check out a new feature branch
  - Auto-generates kebab-case branch names from description
  - Optionally pass `--branch-name <custom-name>` to use a custom branch name
  - Updates main branch before creating the feature branch

- **`/git-finish-feature`** - Complete a feature by committing, pushing, and creating a PR
  - Stages relevant files, drafts commit message and PR description
  - Waits for your approval before committing and pushing
  - Creates a PR using `gh`

### Collaboration and Reflection

Structured approaches to improving collaboration and capturing insights:

- **`/reflect`** - Conduct a collaboration reflection after completing substantial work
  - Capture what went well, what didn't work, and patterns worth remembering
  - Suggest updates to your `CLAUDE.md` files based on insights
  - Improve future collaboration by refining your context
  - See [Reflection Workflow Guide](claude/guides/reflection-workflow.md) for detailed usage

**Using These Commands in Other Projects**:

To use these slash commands in another project, copy the files from `claude/commands/` to your project's
`.claude/commands/` directory:

```bash
cp -r claude/commands/* /path/to/your-project/.claude/commands/
```

**Conventions**:
- Commit messages use imperative mood ("Add feature", not "Added feature")
- Always include "Generated with Claude Code" footer and co-author attribution
- Subject lines under 72 characters; use body for details when needed
- PR review and merge remain manual (you handle approval/merge on GitHub)

## Contributing

Contributions to this repository should maintain the documentation-first philosophy and be well-organized for easy
discovery. All contributions should:

- Follow the established directory structure and naming conventions
- Include clear documentation or comments explaining the purpose of resources
- Be tested (or provide clear testing instructions) before submission
- Respect the 120-column word wrap convention in all markdown files
- Use the git workflow automation commands for feature development

See [CONTRIBUTING.md](CONTRIBUTING.md) for specific guidelines on submitting contributions.

## Contributors

See [CONTRIBUTORS.md](CONTRIBUTORS.md) for a list of contributors and acknowledgments.
