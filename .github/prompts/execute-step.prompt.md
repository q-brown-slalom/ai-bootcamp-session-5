---
description: "Execute instructions from the current GitHub Issue step"
mode: "tdd-developer"
tools: [codebase, search, problems, editFiles, runCommands, getTerminalOutput, testFailure]
inputs:
  - id: issue-number
    type: promptString
    description: "GitHub issue number (optional)"
---

# Instructions

- If no issue number is provided, use gh CLI per workflow utilities to find the main exercise issue (title contains "Exercise:").
- Fetch the issue with comments (`gh issue view <issue> --comments`).
- Parse the latest step instructions; focus on sections labeled ":keyboard: Activity:" and execute them in order.
- Follow project testing scope: only unit/integration tests with Jest/Supertest and React Testing Library; do not suggest or add e2e/browser automation.
- Run necessary commands to complete each activity; keep changes minimal and test-focused (Red → Green → Refactor).
- Do NOT commit or push; finishing activities stops the prompt. Tell the user to run /validate-step afterward.
- Surface any blockers or missing context before proceeding.
