# Overview

The Gemini-CLI Software Project Starter Kit is a reference library for teams that want to use Gemini CLI as a reliable project copilot rather than a one-off chat tool.

## Core idea

Good results come from treating agent work as a lightweight operating system:

- define roles clearly
- provide bounded context
- use explicit task statements
- require structured outputs
- review before moving to the next phase

This repository gives you reusable markdown assets to do that.

## What is inside

### Agents
Agent role cards describe what a role is responsible for, what it should avoid, and what output it should produce.

See [docs/agents/README.md](agents/README.md).

### Strategies
Strategy guides describe multi-step workflows such as kickoff, feature delivery, debugging, and refactoring.

See [docs/strategies/README.md](strategies/README.md).

### Configs
Configuration docs explain how to define conventions, agent operating modes, and documentation structures even when the target project does not yet have a fixed schema.

See [docs/configs/README.md](configs/README.md).

### Templates
Templates provide reusable shapes for task briefs, agent briefs, and handoff notes.

See [docs/templates/README.md](templates/README.md).

### Best practices
Best-practice docs cover prompt design, context handling, safety, and repo hygiene.

See [docs/best-practices/README.md](best-practices/README.md).

### Prompts
Prompt examples show how to ask for better results and how to constrain outputs for common development tasks.

See [docs/prompts/README.md](prompts/README.md).

## How to use this kit

1. Pick a workflow from the strategies section.
2. Assign one or more agent roles.
3. Create a task brief using a template.
4. Run the work in small verified steps.
5. Capture the outcome in a handoff document.
6. Update your team conventions as patterns stabilize.

## Design assumptions

This starter kit assumes:

- Gemini CLI is used in a code workspace, not only for brainstorming.
- Users want repeatable workflows, not ad hoc prompting.
- Markdown is the default medium for preserving operating knowledge.
- Teams benefit from explicit constraints, ownership, and expected artifacts.

## What this kit is not

This repository is not:

- a replacement for engineering judgment
- a complete framework with proprietary config syntax
- a promise that one prompt can solve every problem
- a substitute for tests, validation, and code review

## Suggested extension model

After adopting this kit, create project-specific additions such as:

- stack-specific prompt examples
- language or framework agent cards
- release checklists
- incident response playbooks
- architecture decision templates
