# Prompt Design

Strong prompts reduce ambiguity, constrain output, and make validation easier.

## Recommended structure

A reliable prompt usually includes:

1. role or task framing
2. desired outcome
3. relevant context
4. constraints
5. expected output shape
6. validation expectations

## Example pattern

> Act as a Planner Agent. Given the request below, produce a short phased plan with assumptions, risks, likely files, and validation checkpoints. Do not implement code.

## Practical rules

- ask for one primary artifact
- prefer explicit constraints over implied preferences
- tell the agent what not to do when it matters
- request concise structure instead of open-ended prose
- ask for evidence-backed conclusions when discovery is involved

## Weak prompt example

> Help me improve this project.

Why it is weak:

- no outcome
- no scope
- no constraints
- no output shape

## Better version

> Review this repository and propose a prioritized plan to improve test reliability. Limit the response to the top five issues, include likely files or subsystems, and list validation checks. Do not modify code.
