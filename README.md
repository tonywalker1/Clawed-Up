# Clawed-Up

A collection of shareable Claude Code resources including skills, prompts, and utilities for AI development
workflows.

## Overview

This repository contains reusable resources designed to work with [Claude Code](https://claude.com/claude-code) to
automate common development tasks and workflows. All resources are organized by category and can be easily integrated
into other projects.

## What's Included

See **[index.md](index.md)** for a complete catalog of available resources:

- **Collaboration Guidelines** - Expert peer collaborator standards with three-phase workflow and autonomy levels
- **Git Skills** - Automate feature branch creation, commits, pull requests, and branch cleanup
- **Documentation Skills** - Audit and maintain project documentation
- **Collaboration Skills** - Reflect on collaboration and improve your context
- **Prompts** - Coming soon
- **Utilities** - Coming soon

## Quick Start

### Using Resources in Your Project

1. Clone or download this repository
2. Copy the resources you need to your project's `.claude/` directory:

```bash
# Copy Git skills
cp -r claude/skills/* /path/to/your-project/.claude/skills/
```

3. Use the skills with Claude Code (e.g., `/git-start-feature add user authentication`)

### Contributing to This Project

See [CLAUDE.md](CLAUDE.md) for detailed guidance on the development workflow and conventions used in this project.

## Philosophy on AI-Assisted Development

While AI tools like Claude Code significantly enhance productivity, fundamental skills remain critical:

### Knowledge Still Matters

Young developers should still learn core competencies:
- Programming fundamentals and design patterns
- Security principles and threat modeling
- Safety-critical system design
- Algorithm analysis and performance optimization
- Hardware architecture and system constraints

AI augments expertise—it doesn't replace the need to understand what you're building.

### Communication and Leadership Still Matter

Success with AI requires humans to:
- Provide accurate, concise, and precise instructions
- Clearly articulate goals, constraints, and tradeoffs
- Review and validate AI-generated solutions critically

**Pro tip**: Ask AI to help you refine your prompts and context. Better communication with AI leads to better results.

## License

See [LICENSE](LICENSE) for details.
