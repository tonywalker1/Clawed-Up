# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal repository called "Clawed-Up" containing random stuff related to Claude (and other LLMs) and AI. The
repository is currently in its initial state with minimal structure.

## Repository Structure

This is a new repository with basic structure:

- `.idea/` - IntelliJ IDEA configuration files
- `claude/` - Shareable Claude Code resources
  - `commands/` - Custom slash commands for feature workflow automation
- `LICENSE` - Project license
- `README.md` - Basic project description
- `.gitignore` - Git ignore rules (currently ignoring .idea directory)

## Development

This repository currently has no specific build tools, testing frameworks, or development commands configured. The
project appears to be in an early initialization phase.

Since no specific programming language or framework has been established yet, development approaches will depend on what
content gets added to the repository.

## Git Workflow Automation

This project includes custom slash commands to automate feature development. These commands are stored in `claude/commands/` and are shareable across projects.

**Available Commands**:

- **`/git-start-feature [description]`** - Create and check out a new feature branch
  - Auto-generates kebab-case branch names from description
  - Optionally pass `--branch-name <custom-name>` to use a custom branch name
  - Updates main branch before creating the feature branch

- **`/git-finish-feature`** - Complete a feature by committing, pushing, and creating a PR
  - Stages relevant files, drafts commit message and PR description
  - Waits for your approval before committing and pushing
  - Creates a PR using `gh`

**Using These Commands in Other Projects**:

To use these slash commands in another project, copy the files from `claude/commands/` to your project's `.claude/commands/` directory:

```bash
cp -r claude/commands/* /path/to/your-project/.claude/commands/
```

**Conventions**:
- Commit messages use imperative mood ("Add feature", not "Added feature")
- Always include "Generated with Claude Code" footer and co-author attribution
- Subject lines under 72 characters; use body for details when needed
- PR review and merge remain manual (you handle approval/merge on GitHub)
