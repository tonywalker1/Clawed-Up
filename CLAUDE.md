# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working in this repository.

For what this project offers and how to install it, see [README.md](README.md). For the complete catalog of
skills, guides, and guidelines, see [index.md](index.md). This file covers only how to work *on* the repository.

## Project Overview

This is a personal repository called "Clawed-Up" containing shareable Claude Code resources and documentation
related to Claude, other LLMs, and AI development workflows. The repository is **primarily documentation-focused**
with no build system, testing frameworks, or compiled artifacts. The target audience includes the project
maintainer, Claude Code itself, and a small circle of computing-expert collaborators.

The repository's skills are packaged as a single Claude Code plugin (`.claude-plugin/plugin.json` and
`marketplace.json`). Once installed, skills are namespaced as `/clawed-up:<skill-name>`. Guides, guidelines, and
examples remain plain markdown outside the plugin, since plugins only package executable components like skills,
agents, and hooks.

Note that skills are edited here directly as files under `skills/`; there is no need to install the plugin to
work on them.

## Collaboration Guidelines

**Read [`guidelines/collaboration.md`](guidelines/collaboration.md) before non-trivial work in this repository.**

That file defines how Claude Code collaborates here: the expert peer collaborator stance, the three-phase
workflow (Discuss → Propose → Execute), and autonomy levels. It governs work on this project and is also the
project's shareable artifact — one file serving both uses, so there is no second copy to drift out of sync.

## Git Workflow

Feature-branch workflow. Check the current branch before starting; if on main and the work is non-trivial,
branch from an updated main first. Commit incrementally, then push and open a PR with `gh pr create`.

**Conventions**:

- Commit messages use imperative mood ("Add feature", not "Added feature")
- Subject lines under 72 characters; use the body for details when needed
- Wrap markdown at 120 columns
- PR review and merge remain manual (the maintainer handles approval/merge on GitHub)

## Repository Structure

- `.claude-plugin/` - Plugin manifest (`plugin.json`) and marketplace catalog (`marketplace.json`)
- `skills/` - Custom skills (the plugin's skill directory)
- `guides/` - Workflow guides and tutorials
- `guidelines/` - Collaboration frameworks and best practices
- `examples/` - Production-tested configuration examples
- `index.md` - Complete catalog of every resource in the repository
- `README.md` - Project overview and installation
- `CLAUDE.md` - This file
- `CONTRIBUTING.md` - Contribution guidelines
- `CONTRIBUTORS.md` - Contributors and acknowledgments
- `LICENSE` - Project license
- `.gitignore` - Git ignore rules

## Documentation Maintenance

When adding a new resource:

1. **Create the content** in the appropriate subdirectory (`skills/`, `guides/`, `guidelines/`, `examples/`)
2. **Update [index.md](index.md)**, which is the single catalog of record: add an entry to the relevant section
   with bullets describing key capabilities, and a usage example where applicable
3. **Update [README.md](README.md)** only when adding a whole new *category* — its "What's Included" list is a
   one-line-per-category summary that defers to index.md for detail

Do not add per-resource entries to this file. It documents how to work on the repository, not what the repository
contains; a second catalog here would drift from index.md. Update this file when the repository's own structure,
workflow, or conventions change.

## Development

Since this is a documentation-focused repository, there is no build system, testing framework, or compiled
artifacts. Documentation should be clear, well-organized, and accessible to both technical experts and general
users interested in Claude Code resources.

## Contributing

Contributions should maintain the documentation-first philosophy and be well-organized for easy discovery. All
contributions should:

- Follow the established directory structure and naming conventions
- Include clear documentation or comments explaining the purpose of resources
- Be tested (or provide clear testing instructions) before submission
- Respect the 120-column word wrap convention in all markdown files
- Use the git workflow automation skills for feature development

See [CONTRIBUTING.md](CONTRIBUTING.md) for specific guidelines on submitting contributions.

## Contributors

See [CONTRIBUTORS.md](CONTRIBUTORS.md) for a list of contributors and acknowledgments.
