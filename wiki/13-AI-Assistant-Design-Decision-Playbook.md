# AI Assistant Design Decision Playbook

Use this page to guide AI assistants toward grounded design help.

## Required Context for Design Work

Provide:

- `ai-workflow-rules.md`
- `project-overview.md`
- `project-architecture.md`
- `code-standards.md`
- `ui-context.md` when UI is involved
- `progress-tracker.md`
- Relevant source files or module summaries
- Relevant wiki pages from this design-pattern wiki

## Standard Design Prompt

```text
You are helping with a software design decision.

Use the provided project context and design-pattern wiki.
First identify the problem, forces, constraints, existing architecture, and likely future changes.
Then compare viable options in a decision table.
Recommend the simplest option that satisfies the forces.
Explain how the design affects testing, operations, security, performance, and future change.
List concrete implementation steps and update the progress tracker.
```

## Guardrails for AI Recommendations

The assistant should:

- Prefer existing project patterns over new abstractions.
- Avoid introducing a pattern unless it solves a named force.
- Distinguish business rules from infrastructure mechanics.
- Keep decisions reversible where uncertainty is high.
- Name consequences, not only benefits.
- Recommend tests at the same boundary as the design risk.
- Record rejected alternatives.

The assistant should not:

- Add microservices because code is large.
- Add repositories, factories, or interfaces for every class by default.
- Hide network calls behind local-looking abstractions without failure handling.
- Recommend eventual consistency without explaining user-visible behavior.
- Recommend event-driven designs without idempotency and observability.
- Treat UI state, server state, and domain state as the same thing.

## Decision Output Template

```markdown
## Recommendation

Choose [option] because [named forces].

## Forces

- [force]
- [force]

## Options

| Option | Benefits | Costs | Risks | Best Fit |
| --- | --- | --- | --- | --- |
| | | | | |

## Implementation Plan

1. [step]
2. [step]
3. [step]

## Tests

- [test]

## Operations

- [logging/metrics/tracing/recovery]

## ADR Entry

[short ADR draft]
```

