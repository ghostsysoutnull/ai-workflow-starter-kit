# Gemini CLI Example: Headless Automation

## Use this when

- you need machine-readable output
- the task belongs in a script or pipeline
- interactive review is not required for the first pass

## Session goal

Run Gemini CLI non-interactively and capture structured output.

## Simple text output

```text
gemini -p "Summarize the architecture of this repository"
```

Use this for quick automation where plain text is sufficient.

## JSON output

```text
gemini -p "Summarize the architecture of this repository" --output-format json
```

Use this when another tool needs to parse the result.

Current documented JSON shape includes:

- `response`
- `stats`
- optional `error`

## Streaming JSON output

```text
gemini -p "Analyze the repository and report progress as work happens" --output-format stream-json
```

Use this when long operations should be monitored as events.

Current documented event types include:

- `init`
- `message`
- `tool_use`
- `tool_result`
- `error`
- `result`

## Exit codes that matter

Current documented exit codes include:

- `0` success
- `1` general error or API failure
- `42` input error
- `53` turn limit exceeded

## Practical uses

Headless mode is a good fit for:

- daily repository summaries
- CI annotations
- report generation
- prompt-driven analysis that returns JSON

It is not the best fit for:

- exploratory debugging
- long interactive refactors
- ambiguous tasks with multiple turns

## Stoic rules

- use headless mode when determinism of output format matters more than interactivity
- keep prompts narrow
- prefer JSON when the result will be consumed by another tool
- fail fast on non-zero exit codes
