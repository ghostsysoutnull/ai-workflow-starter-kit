# Gemini CLI Example: Research Session

## Use this when

- the repository is unfamiliar
- the requested change is not yet scoped
- you need concrete findings before planning or editing

## Session goal

Identify the files, boundaries, and risks involved in a change before implementation starts.

## Minimal setup

Start Gemini CLI in the repository root.

```text
gemini
```

If the project uses `GEMINI.md`, inspect the loaded context first:

```text
/memory show
```

## Practical prompt sequence

### Step 1: inspect the repo shape

```text
@README.md @docs/ Summarize this project, identify the main documentation areas, and list the highest-value missing pieces.
```

Expected output:

- short project summary
- relevant directories
- initial gaps

### Step 2: narrow to the change area

```text
@src/ @tests/ Identify the files and subsystems most likely affected by adding saved search filters. Return findings, unknowns, and likely validation needs. Do not suggest code yet.
```

Expected output:

- likely files
- flow summary
- unresolved questions
- validation path

### Step 3: save the state

```text
/chat save research-saved-search-filters
```

Why:

This creates a named checkpoint before planning starts.

### Step 4: compress if the session is getting noisy

```text
/compress
```

Use this when the context is becoming too long but the work should stay in the same session.

## Stoic rules

- do not implement during research
- do not ask for a giant report
- stop when the output is enough to plan the next step
- checkpoint before changing modes

## Good outcome

A good research session produces:

- a bounded change area
- a list of likely files
- known unknowns
- a clear next step for planning
