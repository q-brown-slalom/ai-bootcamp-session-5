---
description: "Workspace instructions for Copilot chat modes and developer guidance"
---

# Copilot Workspace Instructions

## Project Context

- Full-stack TODO application with a React frontend and Express backend.
- Focus on iterative, feedback-driven development and instructor-led exercises.
- Current phase: Backend stabilization and frontend feature completion.

## Documentation References

- [docs/project-overview.md](../docs/project-overview.md) - Architecture, tech stack, and structure
- [docs/testing-guidelines.md](../docs/testing-guidelines.md) - Test patterns and standards
- [docs/workflow-patterns.md](../docs/workflow-patterns.md) - Development workflow guidance

## Development Principles

- Test-Driven Development: Follow the Red → Green → Refactor cycle for all new features and bug fixes.
- Incremental Changes: Make small, focused, and testable modifications; prefer many small commits over large ones.
- Systematic Debugging: Use failing tests as the primary guide for root-cause analysis.
- Validation Before Commit: Ensure all tests pass and there are no lint errors before committing.

## Testing Scope

This project uses unit tests and integration tests ONLY.

- Backend: Jest + Supertest for API and integration testing.
- Frontend: React Testing Library for component unit/integration tests.
- Manual browser testing is used to verify full UI flows where required.
- DO NOT suggest or implement end-to-end test frameworks such as Playwright, Cypress, or Selenium.
- DO NOT suggest browser automation tools. Reason: keep the lab focused on unit/integration testing without e2e complexity.

### Testing Approach by Context

- Backend API changes: Write Jest tests FIRST, then implement code to satisfy the tests (RED → GREEN → REFACTOR).
- Frontend component features: Write React Testing Library tests FIRST for component behavior, then implement to pass tests. Follow up with manual browser testing for full UI verification.
- This repository enforces true TDD: tests are authored before production code changes.

## Workflow Patterns

1. TDD Workflow: Write or update tests → Run test suite → Observe failures → Implement minimal code → Tests pass → Refactor.
2. Code Quality Workflow: Run linting → Categorize issues → Fix systematically → Re-run tests and linters.
3. Integration Workflow: Identify failing scenario → Reproduce with tests → Debug with logs and stack traces → Fix → Verify end-to-end manually.

## Chat Mode Usage

- `tdd-developer`: Use this mode for test-focused tasks, writing failing tests first, and iterating through the Red-Green-Refactor cycle.
- `code-reviewer`: Use this mode for lint fixes, refactors, and code-quality improvements. Prioritize minimal, safe changes and clear commit messages.

## Memory System

- Persistent Memory: This file (.github/copilot-instructions.md) contains foundational principles and workflows.
- Working Memory: .github/memory/ directory contains discoveries and patterns.
- During active development, take notes in .github/memory/scratch/working-notes.md (not committed).
- At end of session, summarize key findings into .github/memory/session-notes.md (committed).
- Document recurring code patterns in .github/memory/patterns-discovered.md (committed).
- Reference these files when providing context-aware suggestions.

## Workflow Utilities

Use the GitHub CLI for quick workflow automation and to fetch issue context when executing steps.

Commands:

```
gh issue list --state open
gh issue view <issue-number>
gh issue view <issue-number> --comments
```

- The main exercise issue will include "Exercise:" in the title.
- Steps and guidance are posted as comments on the main exercise issue.
- Use the above `gh` commands when `/execute-step` or `/validate-step` prompts are invoked in the workflow.

## Git Workflow

- Commit message format: Use Conventional Commits (`feat:`, `fix:`, `chore:`, `docs:`, `test:`, etc.).
- Branch strategy: Create focused feature branches named `feature/<descriptive-name>` or `fix/<descriptive-name>`.
- Staging: Always stage all targeted changes with `git add .` before committing.
- Push: `git push origin <branch-name>` to publish changes for review.

---
Last updated: automated workspace instructions
