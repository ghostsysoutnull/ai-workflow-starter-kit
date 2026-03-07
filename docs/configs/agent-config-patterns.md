# Agent Config Patterns

This guide defines a practical way to describe agent behavior for Gemini CLI projects, even when your team has not adopted a formal config file format yet.

## Recommended config dimensions

Document these for each role:

- **name** — the role name
- **purpose** — the one-sentence job
- **allowed work** — what the role may do
- **restricted work** — what the role should avoid
- **inputs required** — minimum context needed to perform well
- **output contract** — expected structure of the result
- **handoff targets** — roles that should receive the next step
- **validation expectations** — what proof is required before completion

## Example markdown config shape

```md
## Role: Implementer Agent
- Purpose: make scoped changes based on an approved plan
- Allowed work: edit files, add tests, summarize changes
- Restricted work: redesign architecture without approval
- Inputs required: task brief, constraints, validation target
- Output contract: summary, changed files, validation notes, open risks
- Handoff targets: Reviewer Agent
- Validation expectations: run tests or explain why not possible
```

## Why document config in markdown first

Markdown-based conventions are easy to review and adapt. They help you stabilize behavior before you invest in a machine-readable config layer.

## Good defaults

- prefer one primary responsibility per role
- keep output contracts short and explicit
- require uncertainty disclosure
- define when the role should stop and hand off
- define what evidence counts as done

## Signs your team needs a formal config file

You may be ready for JSON, YAML, or TOML when:

- many projects share the same roles
- automation needs to read the rules
- output contracts are becoming standardized
- onboarding depends on repeatability
