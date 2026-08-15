# Collaboration Reflection Workflow

A structured approach to capturing insights and improving collaboration with Claude Code after completing
substantial work.

## Purpose

Claude Code writes memories as it works, but those writes are opportunistic — it saves what happens to stand
out while it is busy doing something else. The `/clawed-up:reflect` skill is the deliberate pass: a look back
across the whole session, at leisure, to decide what is actually worth keeping.

This is not about blame or criticism. It is systematic reflection to:

- Identify patterns in successful collaboration — both what works in your workflow and what Claude Code does
  well
- Surface misunderstandings or gaps in context before they compound
- Capture technical and architectural patterns worth remembering
- Keep your persistent context an accurate representation of how you actually work

## When to Use It

Invoke `/clawed-up:reflect` when:

- You've completed a substantial feature, project, or problem-solving session
- The session had real friction and you want to understand where it came from
- You've discovered new patterns in how you approach problems
- Your approach or constraints have evolved since your last update

You don't need this after every interaction. Save it for moments of real learning or significant work.

## What the Skill Does

### 1. Reconstructs the session

Before offering observations, it checks git history and the actual diff rather than relying on recall of the
conversation. What changed, where the work stalled, where it reversed direction.

### 2. Presents four areas

**What went well** — decisions that held up, framings that led somewhere good, places where pushback or a
clarifying question saved effort.

**What didn't work** — bad advice given, issues missed, wrong paths pursued and how long before they were
noticed, requirements misread, suggestions that contradicted preferences you had already stated. This section
is the point of the exercise; a reflection that softens it is not worth running.

**Patterns worth capturing** — technical and architectural choices likely to recur, process patterns in how you
approach diagnosis and iteration, and gaps between what Claude Code's instructions say and how the work
actually went.

**What to persist** — concrete text, routed to a specific destination.

It prioritizes the three to five observations that would change future behavior. A comprehensive list is a
worse deliverable than a short sharp one.

## Where Insights Go

Not everything belongs in the same place, and most things belong in none of them.

| Insight | Destination |
|---|---|
| How Claude should work — corrections, confirmed approaches | a `feedback` memory, with the reasoning |
| Who you are — role, expertise, standing preferences | a `user` memory |
| Ongoing goals or constraints not derivable from the code | a `project` memory |
| External resources — dashboards, tickets, docs | a `reference` memory |
| A convention for one repo, binding on anyone working in it | that project's `CLAUDE.md` |
| A standing preference across all your projects | your global `CLAUDE.md` |
| Anything the code, tests, or git history already record | nowhere |

The rough split: **memory** holds what was learned about working with you; **`CLAUDE.md`** holds rules a
different collaborator would also need to follow.

A retrospective is also the right moment to prune. If a memory turns out to have been wrong, it gets deleted,
not just supplemented.

## Example Use Cases

### Case 1: Architectural clarity

After building a complex feature, you realize Claude Code should have pushed back harder on your initial
design. Reflection captures which signals were present and missed, and turns that into a `feedback` memory
about when to challenge a design rather than implement it.

### Case 2: Context gap

You find yourself explaining the same constraint three times. Reflection identifies what was missing, and the
constraint becomes a `project` memory or a `CLAUDE.md` line so it does not need a fourth explanation.

### Case 3: Communication pattern

You discover a way of framing problems that consistently leads to better solutions. That becomes a `user`
memory so it is the default going forward.

## Version-Controlled Global Configuration

If your `~/.claude` directory is managed as a git repository, the skill offers to commit and push changes made
under it:

1. It checks whether `~/.claude` is a git repository
2. If so, it asks whether to commit — it will not commit without approval
3. On approval, it drafts a commit message reflecting the insights, commits, and pushes
4. If you decline, changes stay local

This keeps your global collaboration context synced across machines with version history. If `~/.claude` is not
a git repository, the skill says so plainly and leaves the changes local.

### Prerequisites

- `~/.claude` initialized as a git repository (`git init ~/.claude`)
- A configured remote
- Credentials set up to push

## Tips for Effective Reflection

- **Be specific** — name the moment, not the category. "It went well" is not usable feedback
- **Focus on patterns** — an individual mistake matters less than a recurring one
- **Think systemically** — consider how constraints, priorities, and context shaped the collaboration
- **Update incrementally** — small frequent updates beat periodic rewrites
- **Correct the record** — if Claude's summary of what happened is wrong, say so before it writes anything
