---
description: Conduct a collaboration reflection after substantial work
---

# Collaboration Reflection

After we've worked together on a substantive project or problem, I'd like your feedback to improve our collaboration.
Please reflect on:

## What Went Well

- Specific moments where you identified problems, asked clarifying questions, or provided clear guidance
- Patterns in my communication or approach that were particularly effective
- Decisions or trade-offs that proved sound

## What Didn't Work

- Where you gave bad advice, missed architectural issues, or went down wrong paths (be direct)
- Where you misunderstood my requirements or constraints
- Where your suggestions contradicted my stated preferences or infrastructure decisions
- Mistakes you made and what the underlying lesson is (I care about the wisdom, not the mistake itself)

## Patterns Worth Capturing

- Technical/architectural patterns I used that might repeat in future projects
- Communication or collaboration patterns that worked well
- Process patterns (how I approached the problem, how I tested/iterated)
- Any gaps between your current understanding (in CLAUDE.md) and how I actually work

## Suggested CLAUDE.md Updates

Based on the above, suggest concrete additions or clarifications to:

- `~/.claude/CLAUDE.md` (global collaboration/coding preferences)
- Project-level `CLAUDE.md` (project-specific context)

Show both the conceptual idea *and* exact text that could be added, formatted as you'd include it.

## Handling Global CLAUDE.md Changes

After providing suggested updates:

1. If updates involve `~/.claude/CLAUDE.md` changes, check whether `~/.claude` is a git repository
2. If it IS a git repo:
   - Ask the user: "Your ~/.claude directory appears to be version-controlled via git. Would you like me to commit these global CLAUDE.md changes to your remote?"
   - If the user declines: Stop here. The changes are suggested but not committed.
   - If the user agrees:
     a. Switch to the `~/.claude` directory
     b. Verify the changes to CLAUDE.md
     c. Draft a commit message describing the reflection-based updates (e.g., "Refine collaboration patterns based on recent reflection")
     d. Request user approval of the commit message
     e. Execute: `git add CLAUDE.md && git commit -m "..."` (with approved message)
     f. Execute: `git push` to the remote
     g. Switch back to the original repository (the one where `/reflect` was invoked)
     h. Confirm completion

3. If it's NOT a git repo: Inform the user that `~/.claude` is not version-controlled, and changes are local-only.

## Token Budget

Be thorough but pragmatic—prioritize wisdom over comprehensiveness if context is tight. Focus on the 3-5 most important
observations.

---

If you'd like to update CLAUDE.md files as a result, I'm ready to help with that too. If your ~/.claude directory is
version-controlled, I can also help commit those changes to your remote.
