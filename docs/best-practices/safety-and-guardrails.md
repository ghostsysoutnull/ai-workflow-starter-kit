# Safety and Guardrails

Use these rules to keep agent work reliable and low-risk.

## Core guardrails

- do not assume requirements that were not stated
- do not change unrelated files during targeted work
- do not skip validation when a change can be checked
- do not hide blockers or uncertainty
- do not rewrite architecture without approval

## Ask for explicit behavior

When the task is sensitive, state constraints directly:

- preserve public interfaces
- avoid new dependencies
- keep changes reversible
- limit edits to listed files unless evidence requires otherwise

## Review expectations

Before accepting a result, confirm:

- the requested outcome was addressed
- the scope did not drift
- risks were disclosed
- validation evidence exists

## Good escalation rule

If the task becomes ambiguous, risky, or much larger than expected, stop and return a scoped plan or blocker report instead of forcing implementation.
