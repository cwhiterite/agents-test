# Anti-Patterns

Anti-patterns are recurring solutions that usually create more harm than value. Use this page during reviews when a design feels familiar in the wrong way.

| Anti-Pattern | Symptom | Better Direction |
| --- | --- | --- |
| Big Ball of Mud | No clear boundaries; changes ripple everywhere. | Modular boundaries, tests, strangler refactor. |
| God Object | One class/service knows too much. | Split responsibilities by reason to change. |
| Spaghetti Code | Control flow is tangled. | Extract workflows, state machines, or explicit commands. |
| Golden Hammer | Same favorite tool applied everywhere. | Re-evaluate forces and alternatives. |
| Premature Abstraction | Abstraction exists before real variation. | Inline until variation is proven. |
| Lava Flow | Dead or obsolete code remains because nobody understands it. | Characterization tests, telemetry, deletion plan. |
| Distributed Monolith | Services deploy separately but remain tightly coupled. | Redesign service boundaries and data ownership. |
| Chatty Interface | Many small remote calls needed for one task. | Coarser API, gateway aggregation, BFF. |
| Shared Database Integration | Apps couple through database schema. | API/events/ACL unless simplicity wins intentionally. |
| Anemic Domain Model | Domain objects hold data but rules live elsewhere. | Move invariants and behavior into domain model. |
| Service Locator | Dependencies are hidden behind global lookup. | Explicit dependency injection. |
| Singleton Abuse | Global state hides dependencies and order. | Composition root and scoped lifetimes. |
| Boolean Parameter Trap | Flags create unclear call behavior. | Named methods, option objects, strategy. |
| Callback Hell | Async flow becomes nested and unreadable. | Promises, async/await, pipeline, state machine. |
| Retry Storm | Every layer retries and amplifies failure. | Central retry policy, backoff, circuit breaker. |
| Event Soup | Events have unclear ownership and semantics. | Event contracts, naming, schema versioning, tracing. |

## Review Prompt

```text
Review this design for common anti-patterns. For each concern, identify the symptom, the future cost, and the smallest correction that improves the design.
```

