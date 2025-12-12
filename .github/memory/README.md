---
description: "Working memory system for development discoveries"
---

# Memory System

## Purpose

Track patterns, decisions, and lessons during development so Copilot can provide context-aware assistance across sessions.

## Memory Types

- Persistent Memory: `.github/copilot-instructions.md` — canonical principles, workflows, and guardrails.
- Working Memory: `.github/memory/` — in-flight discoveries, patterns, and session summaries.

## Directory Structure

- `session-notes.md`: Historical summaries of completed sessions (committed).
- `patterns-discovered.md`: Accumulated patterns and examples (committed).
- `scratch/working-notes.md`: Active-session notes (not committed); `.gitignore` keeps scratch ephemeral.

## When to Use Each File

- TDD: Capture failing scenarios, hypotheses, and fixes in `scratch/working-notes.md`; summarize durable learnings in `session-notes.md` after the session.
- Linting: Note recurring lint categories and resolutions in `scratch/working-notes.md`; promote reusable fixes to `patterns-discovered.md` if they generalize.
- Debugging: Log reproduction steps and root causes in `scratch/working-notes.md`; add stable patterns (e.g., guard clauses, initialization defaults) to `patterns-discovered.md`.

## How AI Applies This Memory

- During a session, refer to `scratch/working-notes.md` to recall active context and decisions.
- For future work, read `session-notes.md` to understand past outcomes and `patterns-discovered.md` to reuse proven solutions.

## File Roles

- `session-notes.md`: Completed session summaries. Keep concise, committed to git for continuity.
- `scratch/working-notes.md`: Active workpad. Do not commit; clear or roll into `session-notes.md` at session end.

## Workflow Guidance

1) Work in `scratch/working-notes.md` during the session.
2) When a pattern is repeatable, add it to `patterns-discovered.md` (with context and example).
3) At session end, write a summary in `session-notes.md` and clear/rotate the scratch notes.

---
Last updated: automated memory setup