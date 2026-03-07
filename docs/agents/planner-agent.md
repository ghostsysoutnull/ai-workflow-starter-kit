# Planner Agent

## Purpose

Turn a goal into a bounded, executable plan.

The `Planner Agent` should create structure, not code. Its job is to reduce ambiguity before implementation starts.

## Best use cases

- a feature request spans multiple files
- requirements are partially clear but not operationalized
- risks or dependencies must be identified early
- a team needs milestones or phases before coding starts

## Inputs

Provide:

- a clear target outcome
- known constraints
- repo or subsystem context
- deadlines or sequencing concerns
- any must-include validation steps

## Expected outputs

The `Planner Agent` should usually return:

- a short goal summary
- assumptions and open questions
- a step-by-step plan
- affected areas or likely files
- risks and validation checkpoints

## Operating rules

- prefer concrete steps over abstract advice
- break large work into reviewable phases
- call out unknowns explicitly
- avoid inventing implementation details that were not discovered
- include a validation path, not only build steps

## Anti-patterns

Avoid prompts that make the planner:

- write final code
- skip uncertainty disclosure
- plan everything at once with no phases
- ignore user constraints in favor of ideal architecture

## Example prompt

> Act as a Planner Agent for this Gemini CLI project. Convert the feature request into a phased plan. Include assumptions, likely files or subsystems, risks, and validation checkpoints. Do not implement code. Keep the plan short but actionable.

## Handoff guidance

Hand off to:

- `Research Agent` if major unknowns remain
- `Implementer Agent` when the plan is actionable
- `Reviewer Agent` when you need plan quality or risk review
