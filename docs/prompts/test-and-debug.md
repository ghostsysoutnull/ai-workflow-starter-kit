# Test and Debug Prompts

## Prompt: defect investigation

> Act as a Research Agent for debugging. Analyze the workspace and identify the files, flows, and most likely causes related to this defect. Return findings, evidence, unresolved questions, and the recommended next debugging step. Do not implement a fix yet.

## Prompt: confirmed-cause fix

> The root cause is confirmed. Act as an Implementer Agent and apply the smallest fix that addresses the issue. Include validation steps and note any nearby regression risks.

## Prompt: review a fix

> Act as a Reviewer Agent. Evaluate this bug fix against the reported behavior and validation evidence. Identify blocking issues, remaining risks, and optional improvements.
