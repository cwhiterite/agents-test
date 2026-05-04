# AI Workflow Rules

## Operating Rules

- Read project context before making design or code changes.
- Prefer existing architecture and local patterns.
- State assumptions when context is missing.
- Do not introduce a design pattern unless it solves a named force.
- Keep changes small, reversible, and covered by tests proportional to risk.
- Update `progress-tracker.md` after meaningful work.
- Create or update an ADR for architectural decisions.

## Required Response Shape for Design Tasks

1. Problem summary.
2. Relevant constraints and forces.
3. Options considered.
4. Recommendation and trade-offs.
5. Implementation plan.
6. Tests and operational considerations.

## Repository Safety

- Do not revert user changes unless explicitly asked.
- Do not change unrelated files.
- Do not add dependencies without explaining why.
- Do not ignore failing tests.

