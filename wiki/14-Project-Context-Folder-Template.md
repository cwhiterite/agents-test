# Project Context Folder Template

Each project should include a context folder for AI agents. Suggested path:

```text
context/
  ai-workflow-rules.md
  project-overview.md
  project-architecture.md
  code-standards.md
  ui-context.md
  progress-tracker.md
  decisions/
    ADR-000-template.md
```

## File Purposes

| File | Purpose |
| --- | --- |
| `ai-workflow-rules.md` | How AI agents should work in this repo. |
| `project-overview.md` | Product purpose, users, goals, non-goals, constraints. |
| `project-architecture.md` | Current architecture, boundaries, data flow, dependencies. |
| `code-standards.md` | Naming, style, testing, error handling, dependency rules. |
| `ui-context.md` | Design system, UX principles, routes, components, accessibility. |
| `progress-tracker.md` | Current work, status, blockers, completed changes, next steps. |
| `decisions/ADR-000-template.md` | Standard decision record format. |

## AI Context Loading Rule

For every design task, load:

1. `ai-workflow-rules.md`
2. `project-overview.md`
3. `project-architecture.md`
4. `code-standards.md`
5. `progress-tracker.md`
6. `ui-context.md` if UI is affected
7. Relevant ADRs
8. Relevant wiki pages

## Maintenance Rule

The context folder should be treated as living project memory. Update it when:

- Architecture changes.
- A new pattern or boundary is adopted.
- Coding standards change.
- UI conventions change.
- A major task starts, pauses, completes, or changes direction.
- A design decision is accepted or superseded.

