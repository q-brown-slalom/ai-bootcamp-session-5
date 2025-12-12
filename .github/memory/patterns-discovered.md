# Patterns Discovered

## Template

- Pattern Name:
- Context:
- Problem:
- Solution:
- Example:
- Related Files:

## Example Pattern

- Pattern Name: Service initialization (empty array vs null)
- Context: In-memory todo service startup.
- Problem: Null `todos` causes route handlers to throw or require repeated null checks.
- Solution: Initialize `todos` to an empty array during startup; treat it as immutable reference and mutate contents.
- Example: `const todos = [];` in the service/module scope; route handlers push/splice without null guards.
- Related Files: `packages/backend/src/app.js`, service initialization modules.
