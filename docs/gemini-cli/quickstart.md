# Gemini CLI Quickstart

This is the shortest practical path from zero to a useful Gemini CLI session.

## 1. Install

Recommended install methods:

### Run without global install

```text
npx @google/gemini-cli
```

### Install globally with npm

```text
npm install -g @google/gemini-cli
```

Start the CLI with:

```text
gemini
```

## 2. Choose authentication

Use the simplest option that fits your environment.

### Default choice for most local users

Start Gemini CLI and choose **Login with Google**.

This is the default recommendation for most individual developers.

### Use an API key when browser login is not the right fit

Set `GEMINI_API_KEY` before starting the CLI.

Windows PowerShell example:

```powershell
$env:GEMINI_API_KEY="YOUR_GEMINI_API_KEY"
gemini
```

### Use Vertex AI for enterprise or headless environments

Typical required variables:

- `GOOGLE_CLOUD_PROJECT`
- `GOOGLE_CLOUD_LOCATION`
- one of:
  - Application Default Credentials via `gcloud`
  - `GOOGLE_APPLICATION_CREDENTIALS`
  - `GOOGLE_API_KEY`

If you are using a company, school, or Google Workspace account, you may also need to set `GOOGLE_CLOUD_PROJECT` even when logging in with Google.

## 3. Start in the correct directory

Gemini CLI is project-sensitive.

Open the terminal in the repository you want to work on and start the CLI there.

```text
gemini
```

If you need more than one folder in scope, include them at startup:

```text
gemini --include-directories ../shared,../docs
```

## 4. Use the three command families correctly

### Plain prompts
Use plain text for normal work.

Example:

```text
Summarize the architecture of this repository and identify the three highest-risk areas.
```

### `@` for file and directory context
Use `@` when you need the model to read local files or directories.

Examples:

```text
@README.md Explain the purpose of this repository.
@docs/ Summarize the documentation structure and identify gaps.
```

### `!` for shell commands
Use `!` to run shell commands from inside Gemini CLI.

Examples:

```text
!git status
!npm test
```

Do not use shell mode casually. Commands run with your user permissions.

## 5. Learn the first slash commands that matter

These are the commands worth learning immediately:

- `/help` — show available commands
- `/tools` — show what tools are available
- `/auth` — change authentication method
- `/memory show` — inspect loaded `GEMINI.md` context
- `/memory refresh` — reload context files
- `/chat save <tag>` — save a checkpoint for the current conversation
- `/chat resume <tag>` — resume a saved checkpoint in the current project
- `/compress` — replace the current long chat context with a summary
- `/stats model` — check token and quota usage
- `/restore` — restore files from a checkpoint when checkpointing is enabled
- `/rewind` — walk back through session history and optionally revert changes

## 6. Use a minimal working pattern

For most real tasks:

1. start in the project directory
2. verify loaded context with `/memory show`
3. inspect relevant files with `@path`
4. ask for research first if the task is unclear
5. save checkpoints before major transitions with `/chat save <tag>`
6. compress or resume when the session becomes too large

## 7. Use headless mode only when the output needs to be scripted

For simple scripted use:

```text
gemini -p "Summarize the repo"
```

For structured output:

```text
gemini -p "Summarize the repo" --output-format json
```

For streamed events:

```text
gemini -p "Run a long analysis" --output-format stream-json
```

Headless mode returns standard exit codes. In current documentation:

- `0` success
- `1` general error or API failure
- `42` input error
- `53` turn limit exceeded

## 8. Add project context early

A real Gemini CLI workflow should not depend entirely on repeated prompt text.

Use `GEMINI.md` files to define:

- project purpose
- coding conventions
- architectural boundaries
- testing expectations
- role-specific operating rules

See [project-context.md](project-context.md).

## Pragmatic default

If you are unsure what to do, use this path:

- interactive mode for discovery and implementation
- `@` to bring in only the files that matter
- `/chat save` before risky turns
- `/compress` when context grows large
- headless mode only for automation or machine-readable output
