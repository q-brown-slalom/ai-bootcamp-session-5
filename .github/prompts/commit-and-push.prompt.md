---
description: "Analyze changes, generate commit message, and push to feature branch"
tools: [runCommands, getTerminalOutput]
inputs:
  - id: branch-name
    type: promptString
    description: "Target feature branch name (required)"
---

# Instructions

- If branch name is missing, prompt the user for `branch-name` and stop until provided.
- Analyze pending changes with git diff to craft an accurate conventional commit message.
- Ensure branch safety: never commit to main; use only the provided branch.
- If branch does not exist: `git checkout -b <branch-name>`; otherwise `git checkout <branch-name>`.
- Stage all changes: `git add .`.
- Commit with the generated Conventional Commit message.
- Push to the specified branch: `git push origin <branch-name>`.
- Leave a short summary of what was committed and remind the user if further validation is needed.
