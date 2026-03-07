# Debugging Strategy

Use this strategy when behavior is broken, unclear, or inconsistent.

## Goal

Find the cause, verify the fix, and prevent shallow guess-driven edits.

## Sequence

### 1. Describe the failure clearly
Capture:

- expected behavior
- actual behavior
- reproduction steps
- error messages or failing tests

### 2. Narrow the search area
Use the `Research Agent` to identify:

- relevant files and flows
- recent changes if known
- suspicious dependencies or configuration

### 3. Form hypotheses
List the most likely causes before editing.

### 4. Validate a hypothesis
Use logs, tests, targeted reads, or tracing to confirm or reject the likely cause.

### 5. Apply the smallest fix
Use the `Implementer Agent` to fix the confirmed cause, not every nearby code smell.

### 6. Re-run validation
Confirm:

- the original issue is gone
- no nearby regressions were introduced
- any new tests or docs are in place if needed

## Common debugging mistakes

- editing before reproducing
- changing multiple unrelated things at once
- treating symptoms instead of the cause
- stopping after the first plausible theory

## Recommended supporting docs

- [../agents/research-agent.md](../agents/research-agent.md)
- [../prompts/test-and-debug.md](../prompts/test-and-debug.md)
- [../templates/handoff-template.md](../templates/handoff-template.md)
