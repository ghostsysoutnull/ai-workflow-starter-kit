# Documentation Workflow Strategy

Use this strategy when the main deliverable is documentation or when a code change requires supporting docs.

## Goal

Create documentation that is discoverable, accurate, and connected to how the project is actually used.

## Sequence

### 1. Identify the reader
Choose one primary audience:

- new contributor
- maintainer
- operator
- end user
- agent author

### 2. Choose the doc type
Examples:

- overview
- task guide
- reference page
- template
- prompt example
- decision record

### 3. Gather only the needed facts
Use the `Research Agent` if the docs must reflect code, repo structure, or behavior.

### 4. Write for action
Prefer docs that help the reader do something, decide something, or avoid a mistake.

### 5. Review for drift risk
Ask the `Reviewer Agent` whether the doc contains fragile statements that will become outdated quickly.

## Documentation quality checklist

- clear audience
- explicit purpose
- short sections with meaningful headings
- links to related docs
- examples where useful
- minimal hand-waving

## Recommended supporting docs

- [../templates/task-template.md](../templates/task-template.md)
- [../best-practices/prompt-design.md](../best-practices/prompt-design.md)
- [../prompts/doc-generation.md](../prompts/doc-generation.md)
