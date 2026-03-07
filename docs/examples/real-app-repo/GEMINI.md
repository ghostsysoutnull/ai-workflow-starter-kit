# Project: Acme Tasks

## Purpose
- Web application for shared project and task tracking.
- Main user value: create, organize, and complete tasks with low friction.

## Operating rules
- Preserve public API contracts unless the task explicitly allows breaking changes.
- Keep changes small and local when possible.
- Add or update tests when behavior changes.
- Update docs when setup, workflow, or user-visible behavior changes.
- Do not mix feature work with broad cleanup unless the task explicitly requests it.

## Repository map
- `src/web` contains the user interface.
- `src/api` contains backend endpoints and business rules.
- `src/jobs` contains background or scheduled work.
- `tests` contains automated coverage.
- `docs` contains contributor and operational documentation.

## Validation defaults
- Run targeted tests for changed behavior.
- Record manual verification for UI changes.
- State clearly when validation could not be completed.

## Documentation defaults
- Prefer short linked pages.
- Remove stale instructions instead of layering warnings on top of them.
- Save durable prompts and workflows after successful use.
