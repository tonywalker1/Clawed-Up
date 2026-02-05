---
name: reflect
description: Conduct a collaboration reflection after substantial work
allowed-tools: Read, Edit, Write, Bash(git:*)
---

## Task

Reflect on our collaboration to improve future work together.

## Reflection Areas

### What Went Well
- Effective problem identification and guidance
- Communication patterns that worked
- Sound decisions and trade-offs

### What Didn't Work (be direct)
- Bad advice, missed issues, wrong paths
- Misunderstood requirements or constraints
- Suggestions that contradicted stated preferences
- Mistakes and underlying lessons

### Patterns Worth Capturing
- Technical/architectural patterns likely to repeat
- Effective communication/collaboration patterns
- Process patterns (approach, testing, iteration)
- Gaps between CLAUDE.md understanding and actual workflow

### Suggested CLAUDE.md Updates

Propose concrete additions to:
- `~/.claude/CLAUDE.md` (global preferences)
- Project-level `CLAUDE.md` (project-specific context)

Show both the concept and exact text to add.

## Handling Global Updates

After suggesting updates:

1. Check if `~/.claude` is a git repository
2. If yes: ask user if they want changes committed to remote
   - If agreed: commit with descriptive message, push, return to original directory
3. If no: inform user changes are local-only

## Guidelines

Be thorough but pragmatic. Prioritize the 3-5 most important observations over comprehensiveness.
