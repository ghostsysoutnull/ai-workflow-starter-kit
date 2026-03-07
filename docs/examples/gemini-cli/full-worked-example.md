# Gemini CLI Example: Full Worked Flow

This is a concrete example of how one task can move through Gemini CLI from discovery to implementation to review.

## Scenario

A repository has outdated onboarding docs. New contributors hit broken setup steps and lose time.

## Objective

Bring onboarding documentation back in line with the actual repository state.

## Phase 1: start the session

Start in the repository root:

```text
gemini
```

Inspect loaded project memory:

```text
/memory show
```

If no project context exists yet, create a starting point:

```text
/init
```

## Phase 2: research

Prompt:

```text
@README.md @docs/ Review the current onboarding and setup documentation. Identify what looks outdated, what appears to be the current source of truth, and what pages should be updated first. Return findings only.
```

Expected output shape:

- current entry points
- stale pages
- missing steps
- recommended next move

Checkpoint the result:

```text
/chat save docs-onboarding-research
```

## Phase 3: planning

Prompt:

```text
Using the research findings, produce a short plan to refresh onboarding docs. Prefer a small linked doc set, identify likely files to update, and include validation checkpoints. Do not rewrite the docs yet.
```

Expected output shape:

- ordered plan
- files to update
- validation checks
- risks

Compress if the conversation has grown noisy:

```text
/compress
```

## Phase 4: implementation

Prompt:

```text
@README.md @docs/getting-started.md @docs/overview.md Apply the approved docs refresh plan. Keep the structure easy to navigate, remove stale guidance, and summarize exactly what changed.
```

Validate with shell commands if useful:

```text
!git diff -- docs
```

If the result drifted badly, use:

```text
/rewind
```

or:

```text
/restore
```

Checkpoint a good state:

```text
/chat save docs-onboarding-implementation-v1
```

## Phase 5: review

Prompt:

```text
Review the updated onboarding docs against the original objective. Identify blocking issues, likely drift risks, and optional improvements. Keep the review short and prioritized.
```

Expected output shape:

- blockers
- drift risks
- optional improvements
- approval or non-approval

## Why this works

- research and implementation are separated
- file context is attached with `@`
- state is preserved with `/chat save`
- session noise is controlled with `/compress`
- recovery paths exist with `/restore` and `/rewind`

## What this example proves

Gemini CLI is strongest when you:

- start in the right directory
- keep context explicit
- work in phases
- preserve state between phases
- validate before moving on
