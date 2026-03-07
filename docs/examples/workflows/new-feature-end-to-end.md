# Example Workflow: New Feature End to End

## Scenario

A product team wants to add saved search filters to a web application. Users should be able to name a filter, reuse it later, and delete it safely.

## Recommended role sequence

1. `Research Agent`
2. `Planner Agent`
3. `Implementer Agent`
4. `Reviewer Agent`

## Example task brief

### Goal
Add saved search filters without breaking existing search behavior.

### Constraints
- preserve the current search endpoint contract
- avoid introducing a new database technology
- add or update tests for create, read, and delete behavior
- update user-facing docs if the UI changes

### Validation
- relevant unit or integration tests pass
- manual verification path is documented
- changed files are summarized

## Example prompt flow

### Prompt to Research Agent
> Inspect the workspace and identify the files, services, UI components, and data models involved in the current search flow. Return findings, likely change points, and unknowns. Do not implement.

### Prompt to Planner Agent
> Convert the feature request into a phased plan. Include assumptions, likely files, risks, and validation checkpoints. Keep the plan short and actionable.

### Prompt to Implementer Agent
> Apply the approved plan with the smallest practical set of edits. Preserve existing style, update related docs if behavior changes, and report changed files and validation performed.

### Prompt to Reviewer Agent
> Compare the result against the requested feature and constraints. Identify blocking issues, notable risks, and optional improvements.

## Expected artifacts

- discovery report
- phased plan
- patch summary
- review findings
- updated docs if needed

## Common failure modes

- changing search behavior while adding saved filters
- creating too much UI and backend work in one step
- forgetting deletion edge cases
- shipping code without updating help text or docs

## Good thin-slice version

First milestone:

- backend support for storing one saved filter per user
- API read and write support
- no UI management page yet

This proves the concept before the full workflow is built.
