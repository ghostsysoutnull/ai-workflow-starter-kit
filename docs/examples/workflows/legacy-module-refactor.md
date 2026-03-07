# Example Workflow: Legacy Module Refactor

## Scenario

A large service module is hard to change because validation, transformation, and persistence logic are all mixed into one file.

## Recommended role sequence

1. `Research Agent`
2. `Planner Agent`
3. `Implementer Agent`
4. `Reviewer Agent`

## Example task brief

### Goal
Improve maintainability of the legacy module without intentionally changing behavior.

### Constraints
- preserve current public interfaces
- prefer small structural steps
- do not combine the refactor with feature work
- identify validation gaps before moving logic

### Validation
- existing tests still pass
- new checks added if critical behavior was previously uncovered
- reviewer confirms no accidental behavior drift is evident

## Example prompt flow

### Prompt to Research Agent
> Inspect this legacy module and identify the major responsibilities, coupling points, and safest seams for a thin-slice refactor. Return findings and recommended first moves.

### Prompt to Planner Agent
> Create a phased refactor plan that preserves behavior. Include slice boundaries, validation checkpoints, and rollback considerations.

### Prompt to Implementer Agent
> Execute only the first approved refactor slice. Keep the diff focused, preserve behavior, and report validation results.

### Prompt to Reviewer Agent
> Review the refactor for hidden behavior changes, overreach, and maintainability gains.

## Common failure modes

- introducing a new architecture all at once
- mixing cleanup with unrelated fixes
- assuming tests cover behavior when they do not
- failing to define what the first slice should prove
