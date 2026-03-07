# Example Workflow: Bug Fix

## Scenario

A checkout page occasionally submits duplicate orders when users click the submit button twice during a slow network response.

## Recommended role sequence

1. `Research Agent`
2. `Implementer Agent`
3. `Reviewer Agent`

Use the `Planner Agent` only if the fix spans multiple systems or requires a rollout strategy.

## Example task brief

### Goal
Prevent duplicate order submission while preserving a responsive checkout experience.

### Constraints
- do not change payment provider contracts
- keep the fix reversible
- include evidence that the duplicate path is blocked

### Validation
- reproduction steps before and after the fix
- automated or manual verification for double-submit behavior
- note any edge cases still not covered

## Example prompt flow

### Prompt to Research Agent
> Analyze the checkout submission flow and identify where duplicate requests can occur. Return the likely root causes, relevant files, and the recommended next debugging step. Do not implement a fix yet.

### Prompt to Implementer Agent
> The duplicate-submit path is confirmed. Apply the smallest safe fix, preserve existing behavior for normal checkout, and summarize validation steps and residual risk.

### Prompt to Reviewer Agent
> Review this fix against the reported defect. Identify any remaining race conditions, missing validation, or edge cases.

## Expected artifacts

- defect analysis summary
- fix summary
- validation notes
- follow-up risks if any

## Common failure modes

- adding broad locking without understanding the user flow
- fixing only the UI while ignoring server-side duplication risk
- declaring success without reproducing the issue first
