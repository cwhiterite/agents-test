# SOLID Design Principles

SOLID is a set of object-oriented design principles associated with Robert C. Martin and related OO design literature. Treat SOLID as a set of pressure gauges for maintainability, not a law book.

## Quick Index

| Principle | Design Question | Main Smell |
| --- | --- | --- |
| Single Responsibility | Does this unit have one reason to change? | God class, mixed concerns |
| Open/Closed | Can behavior be extended without editing stable code? | Repeated modification of core logic |
| Liskov Substitution | Can subtypes safely replace base types? | Surprising overrides, broken contracts |
| Interface Segregation | Do clients depend only on methods they use? | Fat interfaces, dummy implementations |
| Dependency Inversion | Do policies depend on abstractions instead of details? | High-level logic imports low-level mechanisms |

## Single Responsibility Principle

A module, class, component, or function should have one coherent responsibility and one primary reason to change.

Use when:

- A file changes for unrelated reasons.
- Business rules, persistence, validation, and presentation are tangled.
- Tests require excessive setup because the unit does too much.

Do:

- Separate policy from mechanism.
- Separate orchestration from domain logic.
- Separate formatting, transport, and persistence from core behavior.

Avoid:

- Splitting everything into tiny units with no meaningful names.
- Treating every helper method as a separate responsibility.

AI prompt:

```text
Identify this module's reasons to change. If there is more than one, propose a smaller refactor that separates the most volatile responsibility first.
```

## Open/Closed Principle

Software entities should be open for extension and closed for modification. Stable policy should not be edited every time a new variation appears.

Use when:

- New cases repeatedly require editing the same switch, if-chain, or central registry.
- A product area has stable rules but variable strategies.
- Plugins, providers, workflows, pricing rules, validation rules, or renderers are expected to grow.

Common tools:

- Strategy
- Template Method
- Factory Method
- Command
- Polymorphism
- Configuration-driven composition

Avoid:

- Abstracting before variation exists.
- Creating plugin frameworks for one or two cases.

AI prompt:

```text
Find the axis of variation. Recommend whether this should stay explicit, become a strategy, become configuration, or become a plugin-style extension point.
```

## Liskov Substitution Principle

Subtypes must preserve the promises of their base type. Code using the base type should not need to know which subtype it received.

Use when:

- A subclass throws `NotSupportedException` for inherited behavior.
- A subtype narrows accepted inputs or weakens output guarantees.
- Tests pass for the base implementation but fail for subclasses.

Do:

- Define contracts clearly.
- Prefer composition when inheritance would produce invalid behavior.
- Test shared behavior through the base abstraction.

Avoid:

- Inheriting for code reuse when the domain relationship is not truly substitutable.

AI prompt:

```text
Check this inheritance or interface hierarchy for substitutability. List contract assumptions and show where a subtype violates them.
```

## Interface Segregation Principle

Clients should not depend on methods they do not use. Prefer focused role interfaces over broad interfaces.

Use when:

- Implementers contain no-op methods.
- Consumers mock large interfaces but use one method.
- A dependency gives callers more authority than they need.

Do:

- Model interfaces around consumer roles.
- Keep write interfaces separate from read interfaces when useful.
- Split admin, query, command, lifecycle, and notification concerns.

Avoid:

- Creating one-method interfaces for every class by default.

AI prompt:

```text
Review this interface from the perspective of each consumer. Suggest role-focused interfaces only where they reduce coupling or test burden.
```

## Dependency Inversion Principle

High-level policy should not depend directly on low-level details. Both should depend on stable abstractions.

Use when:

- Business logic imports database, HTTP, queue, filesystem, clock, or framework details directly.
- Tests require real infrastructure for pure policy decisions.
- A system needs replaceable providers or adapters.

Do:

- Put interfaces near the policy that owns the need.
- Inject concrete adapters at the composition root.
- Keep domain code free of infrastructure decisions.

Avoid:

- Abstracting every dependency.
- Placing all interfaces in a generic shared abstractions package.

AI prompt:

```text
Identify high-level policy and low-level details in this design. Recommend dependency boundaries and the composition root.
```

## SOLID in Non-OO Code

SOLID still helps in functional, procedural, and scripting code:

- Single Responsibility: cohesive modules and functions.
- Open/Closed: extensible data-driven dispatch or pure function composition.
- Liskov: functions honor documented input/output contracts.
- Interface Segregation: consumers receive narrow capabilities.
- Dependency Inversion: core logic receives ports, callbacks, or effects instead of importing infrastructure.

