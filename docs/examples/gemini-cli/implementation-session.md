# Gemini CLI Example: Implementation Session

## Use this when

- the task is already scoped
- the relevant files are known
- validation steps are defined

## Session goal

Make a focused code or documentation change while preserving context and recoverability.

## Start from a scoped request

If the scope was discovered in a previous session, resume it.

```text
/chat resume research-saved-search-filters
```

If needed, inspect memory first:

```text
/memory show
```

## Practical prompt sequence

### Step 1: restate the bounded task

```text
@src/search/ @tests/search/ Implement the first thin slice for saved search filters. Preserve the existing search API contract, keep the diff minimal, and include validation notes. Do not redesign unrelated code.
```

Expected output:

- concrete implementation attempt
- minimal changed area
- summary of edits

### Step 2: run validation from inside Gemini CLI

```text
!npm test -- search
```

Or use the validation command that matches the project.

### Step 3: recover if the edit went wrong

Use one of these controls when needed:

```text
/restore
```

```text
/rewind
```

Use them early. Do not stack more edits on top of a bad state.

### Step 4: checkpoint a good state

```text
/chat save implementation-saved-search-filters-v1
```

## Stoic rules

- keep the request narrow
- use `@` to attach only the relevant files
- validate before declaring success
- checkpoint good states
- rewind or restore early if the change drifted

## Good outcome

A good implementation session produces:

- a focused diff
- clear validation evidence
- a recoverable session state
- a clean handoff to review
