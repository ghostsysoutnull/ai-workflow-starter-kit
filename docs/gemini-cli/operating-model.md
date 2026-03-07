# Gemini CLI Operating Model

This page defines a practical default way to use Gemini CLI on software projects.

## Core principle

Treat Gemini CLI as a stateful terminal agent, not as a one-shot chatbot.

That means:

- start in the correct project directory
- control what context is loaded
- keep the task bounded
- preserve useful state
- verify outputs before escalating scope

## Working modes

### Interactive mode
Use interactive mode for:

- discovery
- planning
- implementation
- review
- multi-turn work where context matters

This is the default mode when you run:

```text
gemini
```

### Headless mode
Use headless mode for:

- scripts
- CI-friendly summaries
- structured JSON output
- one-off automation tasks

This is typically triggered when you pass a prompt non-interactively, for example:

```text
gemini -p "Summarize changes" --output-format json
```

## The practical loop

### 1. Establish context
Before asking for work, make sure the session knows where it is and what the project expects.

Use:

- the current working directory
- `GEMINI.md` files
- `@file` or `@directory` references
- `/memory show`

### 2. Separate discovery from action
Do not start with a large implementation request if the codebase is unclear.

Default rule:

- unknown area: research first
- clear task: implement directly
- risky task: save a checkpoint first

### 3. Preserve state deliberately
Useful session controls:

- `/chat save <tag>` for named checkpoints
- `/resume` to browse automatically saved sessions
- `/chat resume <tag>` when continuing a project-scoped saved conversation
- `/compress` when the active context has become too large or noisy

### 4. Use tools intentionally
Gemini CLI is effective because it is not limited to plain text.

Use:

- `@` to inject file content
- `!` to run shell commands when direct terminal evidence is needed
- `/tools` to inspect available tools
- `/mcp` when using external tool servers
- `/skills` when specialized skills are available

### 5. Control reversibility
When file edits are involved, keep recovery options available.

Useful controls:

- checkpointing support
- `/restore` to recover pre-tool state when available
- `/rewind` to move backward through prior interactions and optionally revert effects

## What Gemini CLI does better than generic chat

### Project-scoped context
Gemini CLI is tied to the repository you start in. This is a strength. It keeps work grounded.

### File-aware prompting
`@path` is materially better than pasting large file dumps into chat.

### Memory via `GEMINI.md`
Persistent instructions should live in files, not in repeated prompt boilerplate.

### Session controls
Commands like `/chat save`, `/resume`, `/compress`, `/restore`, and `/rewind` make long-running work manageable.

### Headless automation
`--output-format json` and `--output-format stream-json` make Gemini CLI usable in scripts, not just manual sessions.

## Default operating rules

- use interactive mode for work that needs judgment or multiple turns
- use headless mode for repeatable scripted outputs
- keep project instructions in `GEMINI.md`
- use `@` for local context instead of pasting files into prompts
- use `/compress` before the session becomes chaotic
- save checkpoints before risky edits or major task transitions
- prefer one bounded request over one giant omnibus request

## Failure handling

### If the model loses the plot

- stop adding new instructions
- save the useful state if needed
- compress the conversation or start a fresh session
- reload project context with `/memory refresh`
- restate the task in smaller scope

### If the session is too large

- use `/compress`
- start a new session from the same project directory
- reattach only the files that matter with `@`

### If context is wrong or stale

- run `/memory show`
- fix the `GEMINI.md` file
- run `/memory refresh`

### If a tool-based edit was wrong

- inspect available restore points with `/restore`
- use `/rewind` for session rollback
- do not continue stacking fixes on top of a bad state

## Recommended session pattern for software projects

1. start Gemini CLI in the repository root
2. verify loaded instructions with `/memory show`
3. inspect files with `@`
4. ask for research or planning if needed
5. checkpoint with `/chat save`
6. implement in bounded steps
7. run validation with `!`
8. review or summarize
9. export or save the result when it should persist outside the session

## Bottom line

Gemini CLI is strongest when you treat it like a project-aware terminal agent with memory, tools, and recoverability.

It is weakest when you use it like an oversized chat box and force every task into one prompt.
