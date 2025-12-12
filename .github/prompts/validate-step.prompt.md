---
description: "Validate that all success criteria for the current step are met"
mode: "code-reviewer"
tools: [codebase, problems, runCommands, getTerminalOutput]
inputs:
  - id: step-number
    type: promptString
    description: "Step identifier (e.g., 5-0, 5-1)"
---

# Instructions

- Require `step-number`; if missing, ask the user to provide it and stop.
- Use gh CLI per workflow utilities to find the main exercise issue (title contains "Exercise:").
- Fetch the issue with comments (`gh issue view <issue> --comments`).
- Locate the section `# Step {step-number}:` and extract its "Success Criteria" list.
- Check each criterion against the current workspace (code, problems, recent commands/tests) and note pass/fail with specifics.
- Report completion status and call out any incomplete items with actionable guidance.
- Respect testing scope: unit/integration tests only; no e2e/browser automation recommendations.
