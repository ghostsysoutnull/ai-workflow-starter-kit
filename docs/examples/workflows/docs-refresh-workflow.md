# Example Workflow: Documentation Refresh

## Scenario

A repository has grown quickly and its onboarding docs no longer match the actual setup process.

## Recommended role sequence

1. `Research Agent`
2. `Planner Agent`
3. `Implementer Agent`
4. `Reviewer Agent`

## Example task brief

### Goal
Bring onboarding documentation in line with the current repository layout and setup flow.

### Constraints
- prefer concise pages over one giant guide
- preserve links that may already be shared internally if possible
- flag any setup steps that cannot be verified from the repo alone

### Validation
- doc links resolve
- setup steps are evidence-backed
- outdated guidance is removed or rewritten

## Example prompt flow

### Prompt to Research Agent
> Review the repository docs and identify outdated onboarding information, missing setup guidance, and current sources of truth. Return a concise findings report.

### Prompt to Planner Agent
> Propose a docs refresh plan with page targets, ordering, and validation checkpoints. Keep the plan practical and low-maintenance.

### Prompt to Implementer Agent
> Update the docs according to the approved plan. Prefer small linked pages, remove stale guidance, and keep the final structure easy to navigate.

### Prompt to Reviewer Agent
> Review the updated docs for clarity, consistency, and likely drift risks.

## Common failure modes

- preserving outdated sections for too long
- rewriting everything instead of targeting the broken path
- adding setup claims that were never verified
