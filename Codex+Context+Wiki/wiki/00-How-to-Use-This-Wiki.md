# How to Use This Wiki

## For Humans

Use this wiki as a design conversation guide:

1. Define the problem and forces.
2. Identify likely pattern families.
3. Compare two or three alternatives.
4. Pick the smallest design that keeps future change affordable.
5. Record the decision and the consequences.

Avoid using patterns to justify complexity after the fact. A pattern should make the design easier to explain, test, operate, or change.

## For AI Assistants

When an AI assistant helps with architecture or implementation, include the project context folder and the relevant wiki pages in context. Ask the assistant to:

- State the forces and constraints first.
- Name relevant patterns and rejected alternatives.
- Explain consequences for testing, operations, security, and future change.
- Keep code consistent with the project's existing architecture.
- Update the progress tracker and decision records when work changes direction.

## Recommended Prompt

```text
Use the project context folder and the design-pattern wiki to help make this design decision.

First summarize the problem, forces, constraints, and existing architecture.
Then compare the simplest viable options.
Recommend one approach, explain trade-offs, identify risks, and list implementation steps.
Do not introduce a pattern unless it solves a named force.
```

## Design Review Checklist

- Is the problem stated in business and technical terms?
- What changes are likely: requirements, integrations, scale, teams, data model, UI, deployment?
- What coupling is being reduced, and what coupling is being added?
- What is the failure mode?
- How will this be tested?
- How will this be observed in production?
- What is the exit strategy if this design is wrong?

