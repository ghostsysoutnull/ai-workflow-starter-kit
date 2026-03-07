# Repository Overview

## Purpose

This repository powers the Acme Tasks application, a team task management product with a web UI, backend API, and scheduled background jobs.

## Main areas

- `src/web` — user interface
- `src/api` — backend API
- `src/jobs` — scheduled or asynchronous jobs
- `tests` — unit and integration tests
- `docs` — project and operational documentation

## System boundaries

The application supports:

- user authentication
- project and task management
- notifications
- admin reporting

Out of scope for this repo:

- billing platform ownership
- data warehouse analytics pipelines

## Known operational rules

- API changes require backward compatibility review
- user-visible behavior changes require docs updates
- risky work should be split into thin slices
