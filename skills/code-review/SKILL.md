---
name: code-review
description: Reviews a code snippet or file and gives concise feedback on bugs, style, and improvements. Trigger with /review or "review this code".
---

# Code Review Skill

When invoked, review the provided code and give concise, actionable feedback.

## Triggers

- User types `/review`
- User says "review this code" or "can you review this"

## Response format

1. **Bugs** — any correctness issues (or "None found")
2. **Style** — naming, formatting, readability notes
3. **Improvements** — up to 3 concrete suggestions

Keep feedback short and direct. No praise padding.

## Example

**User:** /review
```js
function add(a,b){ return a+b }
```

**Claude:**
- **Bugs:** None
- **Style:** Missing spaces around params and operator; no semicolon
- **Improvements:** Add parameter type hints if using TypeScript; consider named exports for testability
