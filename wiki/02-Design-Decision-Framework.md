# Design Decision Framework

Use this page before picking a pattern.

## Step 1: Name the Decision

```text
We need to decide how to [design choice] for [project/system] so that [desired outcome].
```

Examples:

- How should the app validate pluggable business rules?
- How should services coordinate an order workflow?
- How should the UI share state across nested components?
- How should legacy code be replaced incrementally?

## Step 2: List Forces

Forces are pressures that make the decision non-obvious.

| Force | Questions |
| --- | --- |
| Change frequency | What is likely to vary? How often? |
| Coupling | What should know about what? |
| Cohesion | Which behavior belongs together? |
| Consistency | Does the design require strong, eventual, or best-effort consistency? |
| Latency | Is the operation user-blocking, async, batch, or streaming? |
| Scale | Is load dominated by reads, writes, fan-out, fan-in, or bursts? |
| Reliability | What breaks when a dependency is slow or unavailable? |
| Security | What trust boundary is crossed? |
| Operability | How will failures be observed, retried, and repaired? |
| Team ownership | Which team owns each part and release cycle? |

## Step 3: Select Candidate Pattern Families

| Problem Shape | Start With |
| --- | --- |
| Object creation varies | Factory Method, Abstract Factory, Builder |
| Algorithm varies | Strategy, Template Method |
| Behavior triggered by events | Observer, Publish/Subscribe, Domain Events |
| Work must be undoable or queued | Command |
| Object shape must adapt | Adapter, Facade, Decorator |
| Complex workflow across services | Saga, Process Manager, Choreography |
| High read/write asymmetry | CQRS, Materialized View, Cache-Aside |
| Unreliable dependency | Retry, Circuit Breaker, Timeout, Bulkhead |
| Legacy migration | Strangler Fig, Anti-Corruption Layer |
| UI state complexity | Container/Presenter, State Machine, MVVM, Store |

## Step 4: Compare Options

Use this lightweight decision table:

| Option | Solves | Costs | Failure Modes | Test Strategy | Exit Strategy |
| --- | --- | --- | --- | --- | --- |
| Option A | | | | | |
| Option B | | | | | |
| Option C | | | | | |

## Step 5: Record the Decision

Use an ADR:

```markdown
# ADR-NNN: Title

## Status
Proposed | Accepted | Superseded | Rejected

## Context
What problem, forces, and constraints led to this decision?

## Decision
What are we choosing?

## Consequences
What improves, what gets harder, and what risks remain?

## Alternatives Considered
What did we reject and why?
```

