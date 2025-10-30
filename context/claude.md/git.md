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
