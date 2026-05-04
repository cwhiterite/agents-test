# GoF Object-Oriented Patterns

The Gang of Four catalog contains 23 classic object-oriented design patterns grouped into creational, structural, and behavioral patterns. Use these patterns mainly inside a codebase boundary: modules, classes, components, services, and libraries.

## Creational Patterns

| Pattern | Use When | Watch For |
| --- | --- | --- |
| Abstract Factory | Families of related objects must vary together. | Too many factories can hide simple construction. |
| Builder | Construction has many optional parts or steps. | Avoid when constructors or named params are clear. |
| Factory Method | A superclass or framework delegates object creation to subclasses or providers. | Can be overkill for one concrete type. |
| Prototype | Creating by cloning configured examples is cheaper or clearer than building from scratch. | Copy semantics can become surprising. |
| Singleton | Exactly one shared instance must exist for process-level coordination. | Global state, test pollution, hidden dependencies. |

## Structural Patterns

| Pattern | Use When | Watch For |
| --- | --- | --- |
| Adapter | Existing API shape does not match the needed interface. | Do not let adapters leak both models. |
| Bridge | Abstraction and implementation should vary independently. | Often unnecessary until both dimensions vary. |
| Composite | Clients should treat individual objects and groups uniformly. | Tree operations can hide performance costs. |
| Decorator | Add responsibilities dynamically without subclass explosion. | Ordering and stacking can be hard to reason about. |
| Facade | A simpler API is needed over a complex subsystem. | Facade should not become a god service. |
| Flyweight | Many similar objects can share intrinsic state. | Complexity rarely pays off unless memory is proven issue. |
| Proxy | Access to another object needs control, laziness, caching, remoting, or protection. | Remote proxies can hide network failure. |

## Behavioral Patterns

| Pattern | Use When | Watch For |
| --- | --- | --- |
| Chain of Responsibility | Multiple handlers may process a request in order. | Debugging flow can become opaque. |
| Command | Represent an action as an object for queuing, logging, undo, retries, or permissions. | Command explosion for simple direct calls. |
| Interpreter | A small language or rule grammar must be evaluated. | Use parser libraries for serious languages. |
| Iterator | Traverse collections without exposing representation. | Usually built into modern languages. |
| Mediator | Many objects coordinate through a central collaborator. | Mediator can become a hidden god object. |
| Memento | Capture and restore state without exposing internals. | Snapshots may be expensive or incomplete. |
| Observer | Dependents react to state changes without tight coupling. | Event storms, ordering bugs, memory leaks. |
| State | Object behavior changes based on internal state. | Too many tiny classes for trivial state. |
| Strategy | Swap algorithms behind a stable interface. | Premature abstraction before variation exists. |
| Template Method | Stable algorithm skeleton with customizable steps. | Inheritance coupling and fragile base classes. |
| Visitor | Add operations across stable object structures. | Hard to add new element types. |

## Pattern Selection Shortcuts

- Choose Strategy when behavior varies by policy.
- Choose State when behavior varies by lifecycle state and transitions matter.
- Choose Command when actions need to be stored, retried, audited, authorized, or undone.
- Choose Adapter when integrating a mismatched external or legacy API.
- Choose Facade when callers need a simpler boundary over a subsystem.
- Choose Decorator when features compose around the same interface.
- Choose Factory or Builder when construction complexity is the problem, not ordinary business behavior.

