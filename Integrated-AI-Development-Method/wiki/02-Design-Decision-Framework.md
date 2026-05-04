# Design Decision Framework

*Methodology for making and documenting architectural decisions*

---

## Overview

Design decisions shape the long-term structure and maintainability of software. This framework provides a structured approach to making, documenting, and revisiting decisions.

## When to Use This Framework

Use this framework when facing:
- Architectural decisions that affect multiple components
- Technology choices with significant implications
- Trade-offs between competing non-functional requirements
- Irreversible or costly decisions

## The Decision Process

### 1. Define the Problem

| Element | Description |
|---------|-------------|
| **Statement** | Clear description of the problem |
| **Context** | Forces, constraints, and stakeholders |
| **Scope** | What is and isn't in scope |

### 2. Gather Requirements

- **Functional**: What must the solution accomplish?
- **Non-functional**: Performance, scalability, security, etc.
- **Constraints**: Budget, time, technology, team skills

### 3. Explore Alternatives

For each alternative, document:
- **Description**: What it entails
- **Pros**: Advantages
- **Cons**: Disadvantages and risks
- **Fit**: How well it addresses the problem

### 4. Evaluate and Decide

| Criterion | Weight | Option A | Option B | Option C |
|-----------|--------|----------|----------|----------|
| [Criterion 1] | [High/Med/Low] | [Rating] | [Rating] | [Rating] |
| [Criterion 2] | [High/Med/Low] | [Rating] | [Rating] | [Rating] |

### 5. Document the Decision

Use an Architecture Decision Record (ADR):
- Context that led to the decision
- Decision made
- Consequences (positive, negative, neutral)

### 6. Review Periodically

| Decision Type | Review Frequency |
|---------------|------------------|
| Technology choice | 6-12 months |
| Architecture | 12-24 months |
| API design | Before major version changes |

---

## Decision Categories

### Reversible Decisions
Easier to change later. Prioritize speed of iteration.
- Package/folder organization
- Naming conventions
- Internal module boundaries

### Semi-Reversible Decisions
Changeable with moderate effort. Balance analysis with speed.
- Service boundaries
- Database schema design
- API contract design

### Irreversible Decisions
Difficult or costly to change. Prioritize thorough analysis.
- Programming language choice
- Core architectural patterns
- Public API contracts

---

## Common Decision Pitfalls

| Pitfall | Description | Prevention |
|---------|-------------|-------------|
| Analysis Paralysis | Endless analysis without decision | Set time-boxes for exploration |
| Sunk Cost Fallacy | Sticking with bad decisions | Regularly review and revisit |
| Groupthink | Accepting dominant opinion | Encourage dissenting views |
| Confirmation Bias | Seeking evidence for preferred option | Explicitly evaluate alternatives |
| Over-Engineering | Designing for hypothetical future needs | YAGNI—focus on current requirements |

---

## Documentation with ADRs

Architecture Decision Records capture decisions for future reference:

1. **Context**: What forces are at play?
2. **Decision**: What was decided?
3. **Consequences**: What are the outcomes?

### When to Create an ADR
- Decision affects multiple teams
- Decision is difficult to reverse
- Decision took significant analysis
- Decision deviates from established patterns

### When ADRs May Not Be Needed
- Routine implementation decisions
- Trivial choices
- Decisions easily changed

---

## Related

- [ADR Template](../../context/decisions/ADR-000-template.md)
- [Anti-Patterns](12-Anti-Patterns.md)
- [Pattern Index by Problem](15-Pattern-Index-by-Problem.md)
