---
name: reflect
description: Run a deliberate end-of-session retrospective on the collaboration and persist what was learned as memory files. Use after substantial work, after a session with real friction, or when asked to reflect, debrief, or capture lessons. Not for routine task completion.
allowed-tools: Read, Write, Edit, Glob, Bash
---

# Collaboration retrospective

Memory writes during a session are opportunistic — you save what happens to stand out while you are busy doing
something else. This skill is the deliberate pass: look back across the whole session, at leisure, and decide
what is actually worth keeping.

Do this *with* the user, not at them. Present observations, let them correct you, then write.

## 1. Look back before speaking

Reconstruct what actually happened rather than what you remember of it. Check the session's git history
(`git log`, `git diff main..HEAD`), what files changed, and where the work stalled or reversed direction.

## 2. Present observations

Cover these four areas. Be specific — name the moment, not the category. Prioritize the **3–5 observations that
would change future behavior**; a comprehensive list is a worse deliverable than a short sharp one.

**What worked.** Decisions that held up. Ways the user framed a problem that led somewhere good. Places where
pushback or a clarifying question saved effort.

**What didn't — be direct.** Bad advice you gave. Issues you missed. Wrong paths you pursued and how long
before you noticed. Requirements you misread. Suggestions that contradicted preferences the user had already
stated. Understating this section makes the whole exercise worthless; the friction is the signal.

**Patterns worth capturing.** Technical or architectural choices likely to recur. Process patterns — how this
user approaches diagnosis, testing, iteration. Gaps between what your instructions say and how the work
actually went.

**What to persist.** For each, name where it goes (below) and show the exact text.

## 3. Route each insight to the right place

Not everything belongs in the same file, and most things belong in none of them.

| Insight | Goes to |
|---|---|
| How you should work — corrections, confirmed approaches | a `feedback` memory, **with the why** |
| Who the user is — role, expertise, standing preferences | a `user` memory |
| Ongoing goals or constraints not derivable from the code | a `project` memory (absolute dates, not "last week") |
| External resources — dashboards, tickets, docs URLs | a `reference` memory |
| A durable convention for *this repo*, affecting anyone working in it | the project's `CLAUDE.md` |
| A standing preference across all projects | the user's global `CLAUDE.md` |
| Anything the code, tests, or git history already record | **nowhere** — do not save it |

Memory is the default for things learned about working with this person. `CLAUDE.md` is for rules a *different*
collaborator would also need to follow.

## 4. Write it

For memories, follow the memory-file format from your instructions: one fact per file, frontmatter with `name`,
`description`, and `metadata.type`; `**Why:**` and `**How to apply:**` lines for `feedback` and `project`
entries; `[[links]]` to related memories. Then add the one-line pointer to `MEMORY.md`.

Before writing, check for an existing memory that already covers the ground and update it instead of creating a
near-duplicate. If a past memory turns out to have been wrong, delete it — a retrospective is the right moment
to prune, not only to add.

## 5. If `~/.claude` is version controlled

Check with `git -C ~/.claude rev-parse --git-dir`. If it is a repo and you changed anything under it, offer to
commit and push. Do not commit without asking. If it is not a repo, say plainly that the changes are local
only.
