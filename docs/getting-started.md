# Getting Started

Use this guide when turning an empty or messy workspace into an agent-friendly project.

## Quick-start workflow

### 1. Define the goal
State the outcome in one sentence.

Example:

> Add OAuth login to the app, keep existing email login working, and document the rollout steps.

### 2. Define constraints
Capture the non-negotiables before work starts.

Typical constraints:

- do not break public APIs
- keep changes under a target size
- preserve current coding style
- add or update tests
- avoid introducing new dependencies unless justified

### 3. Choose a primary strategy
Use one of these first:

- [docs/strategies/project-kickoff.md](strategies/project-kickoff.md)
- [docs/strategies/feature-delivery.md](strategies/feature-delivery.md)
- [docs/strategies/debugging.md](strategies/debugging.md)
- [docs/strategies/refactoring.md](strategies/refactoring.md)

### 4. Assign agent roles
Recommended default split:

- `Research Agent` for discovery and unknowns
- `Planner Agent` for scoping and milestones
- `Implementer Agent` for file changes
- `Reviewer Agent` for validation and risk review

See [docs/agents/README.md](agents/README.md).

### 5. Create a brief
Use [docs/templates/agent-brief-template.md](templates/agent-brief-template.md) or [docs/templates/task-template.md](templates/task-template.md).

### 6. Ask for structured output
Good tasks request a concrete artifact, such as:

- a short plan
- a list of affected files
- a patch summary
- a validation report
- a handoff note

### 7. Validate before moving on
Validation should include one or more of:

- compile or lint checks
- targeted tests
- diff review
- requirement checklist review
- user-facing doc updates

## Default operating loop

1. discover
2. plan
3. implement
4. validate
5. hand off

Do not collapse all five into a single vague request when the work is meaningful.

## First-day setup checklist

- Read [docs/overview.md](overview.md)
- Review [docs/configs/project-conventions.md](configs/project-conventions.md)
- Pick an agent role set from [docs/agents/README.md](agents/README.md)
- Save a local project brief based on [docs/templates/task-template.md](templates/task-template.md)
- Copy at least two prompts from [docs/prompts/README.md](prompts/README.md)

## Common mistakes

- asking for implementation before clarifying constraints
- mixing research, planning, coding, and review in one oversized prompt
- failing to define the output format
- failing to specify how success will be checked
- not saving reusable prompts and conventions after a successful run

## Good default rule

If the task spans multiple files or has unclear requirements, start with research and planning before asking for edits.
