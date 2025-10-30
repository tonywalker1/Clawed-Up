# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal repository called "Clawed-Up" containing random stuff related to Claude (and other LLMs) and AI. The
repository is currently in its initial state with minimal structure.

## Repository Structure

This is a new repository with basic structure:

- `.idea/` - IntelliJ IDEA configuration files
- `LICENSE` - Project license
- `README.md` - Basic project description
- `.gitignore` - Git ignore rules (currently ignoring .idea directory)

## Development

This repository currently has no specific build tools, testing frameworks, or development commands configured. The
project appears to be in an early initialization phase.

Since no specific programming language or framework has been established yet, development approaches will depend on what
content gets added to the repository.

## Git Workflow Automation

**Feature Development Workflow**:

*Starting a new feature:*
When you say "start feature: [description]" or similar, Claude will:
- Update local main branch (`git pull origin main`)
- Create new feature branch with auto-generated name from description
- Check out the new branch
- Example: "start feature: add user authentication" → branch `add-user-authentication`

*Completing a feature:*
When you say "finish feature" or ask to commit and create PR, Claude will:
- Stage all relevant modified files
- Draft commit message and PR description for your approval
- After your approval: commit, push branch, and create PR using `gh`
- Handle merge conflicts if they occur during the process

**Branch and Message Conventions**:

- Branch naming: Auto-generated from description (kebab-case)
- Commit message style: Imperative mood ("Add feature", not "Added feature")
- Always include "Generated with Claude Code" footer and co-author attribution
- Subject lines under 72 characters; use body for details when needed

**Manual Steps**:
- PR review and merge remain manual (you handle approval/merge on GitHub)
- Local branch cleanup after successful merge (Claude can help when requested)
