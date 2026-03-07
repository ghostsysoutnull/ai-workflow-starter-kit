# Project Conventions

Use this page as the default convention sheet for a Gemini CLI-enabled repository.

## Recommended defaults

### Task framing
- Start with the outcome, not the implementation idea.
- State constraints before asking for work.
- Ask for a structured output.

### Scope control
- Prefer thin slices.
- Avoid mixing feature work and large cleanup in one request.
- Split discovery from implementation when uncertainty is high.

### File changes
- Keep edits minimal and relevant.
- Preserve existing style unless there is an explicit standardization task.
- Update related docs when behavior or workflow changes.

### Validation
- Require evidence for completion.
- Prefer targeted tests or checks over broad unverified claims.
- Record blockers and skipped validation explicitly.

### Communication
- Separate facts, assumptions, and recommendations.
- Call out risks early.
- End with next actions when work is partial.

## Suggested convention snippet for new projects

```md
## Gemini CLI operating conventions
- Use research first when the repo is unfamiliar.
- Require plans for multi-file work.
- Keep implementation diffs focused.
- Run validation or explain why it was not possible.
- Save reusable prompts and templates after successful tasks.
```

## Maintenance rule

Review these conventions after major incidents, process failures, or repeated prompt mistakes.
