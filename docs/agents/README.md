# Agent Library

This section defines reusable agent roles for Gemini CLI workflows.

## Why role cards matter

A role card reduces ambiguity. It answers:

- what the agent is trying to do
- what inputs it needs
- what outputs it should return
- what it should avoid
- when to hand work to another role

## Recommended default roles

- [planner-agent.md](planner-agent.md) — turns goals into scoped execution plans
- [research-agent.md](research-agent.md) — gathers context and reduces unknowns
- [implementer-agent.md](implementer-agent.md) — makes targeted changes and explains them
- [reviewer-agent.md](reviewer-agent.md) — checks quality, risk, and completeness

## Suggested usage pattern

For non-trivial work, chain roles in this order:

1. Research Agent
2. Planner Agent
3. Implementer Agent
4. Reviewer Agent

For small, well-defined work, the `Implementer Agent` may be enough.

## Shared role design rules

Every role in this kit includes:

- purpose
- ideal inputs
- expected outputs
- operating rules
- anti-patterns
- example prompts

## How to adapt these docs

Keep the role name but customize:

- stack or language focus
- required validation steps
- team-specific constraints
- approval rules
- output verbosity
