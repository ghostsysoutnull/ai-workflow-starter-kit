# Project Context with GEMINI.md

`GEMINI.md` is the most important file-level feature to use if you want consistent Gemini CLI behavior across a project.

## What it does

Gemini CLI loads instructional context from `GEMINI.md` files and sends that context to the model.

This is better than rewriting the same instructions in every prompt.

## Context hierarchy

Gemini CLI uses hierarchical context loading.

Key sources include:

1. global context, typically in `~/.gemini/GEMINI.md`
2. workspace and ancestor `GEMINI.md` files
3. just-in-time context discovered when tools access relevant directories

The practical result is simple:

- put global defaults in your user-level file
- put project rules in the repo-level file
- put component-specific rules deeper in the tree only when they are truly local

## What belongs in a repo-level GEMINI.md

Keep it compact and durable.

Good content:

- project purpose
- stack summary
- coding style rules that matter
- test expectations
- architectural boundaries
- documentation rules
- things the agent must avoid

Bad content:

- one-off task notes
- stale migration status
- temporary personal reminders
- long duplicate copies of existing docs

## Sample starter content

```md
# Project: Example Service

## Purpose
- Internal service for processing scheduled jobs and reporting status.

## Rules
- Preserve public API contracts unless the task explicitly allows breaking changes.
- Add or update tests when behavior changes.
- Keep diffs focused. Do not mix feature work with broad cleanup.
- Update markdown docs when workflows or setup steps change.

## Architecture
- `src/api` handles HTTP routes.
- `src/jobs` handles scheduled background work.
- `tests/integration` covers external behavior.
```

## Useful commands

- `/init` — generate an initial `GEMINI.md` for the current directory
- `/memory list` — show which memory files are loaded
- `/memory show` — inspect the current effective memory
- `/memory refresh` — reload memory after editing files
- `/memory add <text>` — append persistent text to the global memory file

## Modular imports

A `GEMINI.md` file can import other files using `@file.md` syntax.

Use this to keep context modular when the file becomes too large.

Example:

```md
# Main project context
@./docs/agent-rules.md
@./docs/style-guide.md
```

## Filename customization

If needed, Gemini CLI can be configured to look for different context filenames through settings.

Example configuration pattern:

```json
{
  "context": {
    "fileName": ["AGENTS.md", "CONTEXT.md", "GEMINI.md"]
  }
}
```

## Practical rule

A good `GEMINI.md` reduces repetition and lowers prompt failure rates.

A bad `GEMINI.md` becomes a dumping ground and silently makes every session worse.
