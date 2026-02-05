---
name: write-docs
description: Automation-first documentation procedure
allowed-tools: Read, Write, Edit, Bash(*)
---

## Task

Write documentation for deployments/operations using automation-first approach.

## Core Principle

Write the script first, then document it.

## Procedure

1. **Script First**: Create automation script with clear, idempotent steps
2. **Document Second**: Write documentation that references the script, not duplicates it
3. **Single Source of Truth**: Script is canonical; docs explain "why" and "when"

## Benefits

- Script validates the documented procedure works
- Future deployments use tested code, not manual transcription
- Documentation stays focused on decisions and context, not mechanics
- Recovery can use script even without deep technical knowledge

## Documentation Template

```markdown
## Deployment

Run the automated deployment script:

\`\`\`bash
./create-pod.sh
\`\`\`

See the script for implementation details. This documentation explains architectural decisions and trade-offs.
```

## Anti-Patterns to Avoid

- Writing step-by-step docs that duplicate script logic
- Documenting commands without a script to execute them
- Creating docs that will drift from actual implementation
