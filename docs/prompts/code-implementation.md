# Code Implementation Prompts

## Prompt: scoped code change

> Act as an Implementer Agent. Apply the approved plan with the smallest practical set of edits. Preserve existing style, avoid unrelated refactors, and summarize changed files, validation performed, and any remaining risks.

## Prompt: doc-backed implementation

> Implement the requested change and update any affected markdown documentation so the repository stays consistent. Keep the code and docs aligned and call out any assumptions.

## Prompt: constrained patch

> Make only the edits required to satisfy this request. Do not redesign surrounding code unless the change cannot work otherwise. If you hit a blocker, stop and report the blocker with recommended next steps.
