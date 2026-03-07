# Feature Delivery Strategy

Use this strategy for adding or changing a capability without losing control of scope.

## Goal

Translate a requirement into a validated change with clear evidence that the requested behavior was delivered.

## Sequence

### 1. Clarify the request
Write down:

- desired user-visible outcome
- acceptance criteria
- non-goals
- compatibility constraints

### 2. Discover affected areas
Use the `Research Agent` if file ownership, flow, or dependencies are unclear.

### 3. Plan the change
Use the `Planner Agent` to define:

- steps
- likely files
- validation path
- rollback or mitigation concerns

### 4. Implement narrowly
Use the `Implementer Agent` to make the smallest useful change set.

### 5. Review against acceptance criteria
Use the `Reviewer Agent` to check:

- requested behavior
- edge cases
- regressions
- doc or test gaps

## Delivery checklist

- request restated clearly
- scope bounded
- change summary available
- tests or checks run
- docs updated if behavior changed

## When to split the feature

Split into phases if:

- the change touches multiple subsystems
- migration or rollout risk exists
- validation is expensive or slow
- requirements are partly unknown

## Recommended supporting docs

- [../agents/planner-agent.md](../agents/planner-agent.md)
- [../templates/agent-brief-template.md](../templates/agent-brief-template.md)
- [../prompts/feature-planning.md](../prompts/feature-planning.md)
- [../prompts/code-implementation.md](../prompts/code-implementation.md)
