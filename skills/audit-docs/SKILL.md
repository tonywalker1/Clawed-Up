---
name: audit-docs
description: Find and fix drift between documentation and the code or systems it describes. Use when asked to audit or realign docs, after a refactor that renamed or moved things, or when docs may describe a system that no longer exists. Not for writing new docs.
allowed-tools: Read, Edit, Write, Glob, Grep, Bash
---

# Audit documentation against reality

Documentation drifts silently — nothing fails when a doc goes stale. This skill finds the drift and fixes it.

Audit the whole project unless the user names specific paths.

## The standard docs are held to

These are the criteria. A doc that violates one of them is a finding, even if it reads well.

1. **Single source of truth.** Any fact stated in two places will eventually disagree. When you find the same
   fact in two docs, one of them becomes a link to the other. When a doc restates what a script, config file,
   or `--help` output already says, the doc loses — replace the restatement with a pointer.
2. **The script is canonical.** For deployment and operations docs, the automation script is the truth and the
   doc explains why and when. A doc containing step-by-step commands that a script also performs is a defect:
   the doc will drift, and the drift will surface during an incident. If the doc has steps and no script
   exists, say so — that is a finding to report, not something to silently paper over.
3. **Absolute paths.** `/etc/nginx/nginx.conf`, not "the nginx config." Relative paths are ambiguous the
   moment a reader is in a different directory than the author was.
4. **Concrete examples with real output.** An example that shows a command but not its output cannot be
   verified by the reader. Where practical, run the command and paste what it actually printed.
5. **Consistent terminology.** One name per concept, matching what the code calls it. If code says `br7` and
   docs say "the bridge," the docs change.
6. **120-column wrap** in all markdown.

## Procedure

### 1. Establish what is actually true

Read the code, configs, and scripts before reading a single doc — otherwise the docs anchor you to their own
version of reality. Build your own picture of: architecture and module boundaries, public/exported interfaces,
entry points and commands, and recent changes (`git log` on the areas in question).

### 2. Map the documentation

Find every doc: `README`, `CONTRIBUTING`, `CLAUDE.md`, `docs/`, design notes, runbooks, module-level comments,
and docstrings on public interfaces.

### 3. Diff reality against the docs

Look for:

- **Removed or renamed**: docs reference APIs, flags, files, or services that no longer exist. Highest
  priority — these actively mislead, and a reader following them fails.
- **Added but undocumented**: public interfaces or major features with no coverage.
- **Architectural drift**: the described design is a past version of the system.
- **Duplication**: the same fact in multiple places, already diverging.
- **Restated mechanics**: prose walking through what a script does.
- **Terminology splits**: two names for one thing.

### 4. Fix directly

Make the edits. Prefer deleting over updating when content is obsolete — a shorter accurate doc beats a longer
one carrying dead weight. Verify commands and paths against the system rather than assuming they still work.

### 5. Report

Keep it short:

- What categories of drift you found, with the worst first
- Files changed and what changed in each
- **Anything you could not fix alone** — a doc describing behavior that may be an unreported bug, a missing
  script that condition 2 calls for, or a question only the maintainer can answer. Do not quietly skip these.
