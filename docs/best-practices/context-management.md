# Context Management

Most poor agent output comes from bad context, not bad intent.

## Goal

Provide enough context to be useful without overwhelming the task.

## What to include

Include:

- the specific objective
- the relevant files, modules, or docs
- hard constraints
- known failure modes
- desired output format

## What to avoid

Avoid:

- dumping unrelated files
- mixing facts and guesses
- repeating the same instructions several times
- requesting large changes without a plan

## Context layering model

### Layer 1: objective
One sentence describing the target outcome.

### Layer 2: local context
Only the files, functions, or docs likely to matter.

### Layer 3: constraints
What must be preserved.

### Layer 4: evidence expectations
How the result will be checked.

## Good rule

If the work touches many files and you cannot identify the key ones yet, ask for research first instead of flooding the prompt with the whole repository.
