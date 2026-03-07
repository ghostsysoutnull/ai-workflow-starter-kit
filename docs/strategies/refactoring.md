# Refactoring Strategy

Use this strategy to improve maintainability without intentionally changing behavior.

## Goal

Make code easier to understand, change, and test while preserving the expected behavior.

## Sequence

### 1. Define the refactoring target
Examples:

- reduce duplication
- improve module boundaries
- simplify a large function
- improve naming or structure

### 2. Protect behavior first
Before refactoring, identify:

- tests that already cover the behavior
- gaps that need temporary checks
- user-visible areas that must remain stable

### 3. Plan in thin slices
Prefer small steps such as:

- extract a helper
- rename a concept
- move one responsibility
- normalize one interface

### 4. Keep functionality stable
The `Implementer Agent` should avoid combining refactoring with unrelated feature work.

### 5. Review for hidden behavior changes
The `Reviewer Agent` should verify that the change is structural, not accidental functional drift.

## Warning signs

- massive diff justified as cleanup
- no tests or checks before starting
- new abstractions introduced without clear payoff
- readability improved in one area but worsened across the whole module

## Recommended supporting docs

- [../best-practices/repo-hygiene.md](../best-practices/repo-hygiene.md)
- [../prompts/code-implementation.md](../prompts/code-implementation.md)
- [../prompts/test-and-debug.md](../prompts/test-and-debug.md)
