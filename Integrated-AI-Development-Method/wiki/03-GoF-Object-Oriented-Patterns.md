# GoF Object-Oriented Patterns

*Classic design patterns from the Gang of Four*

---

## Overview

The Gang of Four (GoF) patterns are 23 foundational object-oriented design patterns categorized into three types: creational, structural, and behavioral.

## Creational Patterns

Deal with object creation mechanisms.

### Abstract Factory
**Intent**: Create families of related objects without specifying concrete classes.

**When to Use**:
- A system should be independent of how products are created
- You need to work with various families of related products

**Structure**:
```
AbstractFactory → ConcreteFactoryA → ProductA1, ProductB1
                              → ConcreteFactoryB → ProductA2, ProductB2
```

---

### Builder
**Intent**: Separate construction of complex objects from representation.

**When to Use**:
- Object creation involves many steps
- Different representations of the same construction process

**Structure**:
```
Director → Builder → Product
                    ↑ ConcreteBuilder
```

---

### Factory Method
**Intent**: Define an interface for creating objects, let subclasses decide which class to instantiate.

**When to Use**:
- A class can't anticipate the class of objects it must create
- Subclasses should specify the objects they create

---

### Prototype
**Intent**: Create objects by copying an existing instance (clone).

**When to Use**:
- Object creation is expensive
- Objects differ in state but share a common structure

---

### Singleton
**Intent**: Ensure a class has only one instance with a global access point.

**When to Use**:
- Exactly one instance is needed
- Single instance should be extensible by subclassing

**Caution**: Consider dependency injection before resorting to Singleton.

---

## Structural Patterns

Deal with object composition and relationships.

### Adapter
**Intent**: Convert the interface of a class into another interface clients expect.

**When to Use**:
- Integrating new components with existing interfaces
- Creating reusable classes that work with incompatible interfaces

---

### Bridge
**Intent**: Decouple an abstraction from its implementation so both can vary independently.

**When to Use**:
- Avoid permanent binding between abstraction and implementation
- Both abstractions and implementations should be extensible

---

### Composite
**Intent**: Compose objects into tree structures to represent part-whole hierarchies.

**When to Use**:
- Part-whole hierarchies (e.g., graphics system, file system)
- Clients should treat individual objects and compositions uniformly

---

### Decorator
**Intent**: Attach additional responsibilities to objects dynamically.

**When to Use**:
- Adding behavior to objects without affecting other instances
- Extension by subclassing would be impractical

---

### Facade
**Intent**: Provide a simplified interface to a complex subsystem.

**When to Use**:
- Simplifying access to a complex system
- Layering a system and defining entry points

---

### Flyweight
**Intent**: Share objects to support large numbers of fine-grained objects efficiently.

**When to Use**:
- Large numbers of similar objects
- Object state can be made extrinsic (context-dependent)

---

### Proxy
**Intent**: Provide a surrogate or placeholder for another object.

**When to Use**:
- Lazy initialization (virtual proxy)
- Access control (protection proxy)
- Remote object access (remote proxy)
- Logging requests (logging proxy)

---

## Behavioral Patterns

Deal with object interaction and responsibility assignment.

### Chain of Responsibility
**Intent**: Avoid coupling sender to receiver by giving multiple objects a chance to handle the request.

**When to Use**:
- More than one object may handle a request
- Handler isn't known in advance

---

### Command
**Intent**: Encapsulate a request as an object, allowing parameterization and queuing.

**When to Use**:
- Parameterizing objects with operations
- Queueing, specifying, and executing requests at different times

---

### Iterator
**Intent**: Provide a way to access elements of a collection sequentially without exposing structure.

**When to Use**:
- Traversing a collection without knowing internals
- Supporting multiple simultaneous traversals

---

### Mediator
**Intent**: Define an object that encapsulates how a set of objects interact.

**When to Use**:
- Communication between objects is complex but well-defined
- Reusing some objects is difficult due to tight coupling

---

### Memento
**Intent**: Capture and externalize an object's internal state without violating encapsulation.

**When to Use**:
- State snapshots for undo operations
- Checkpoint/restore functionality

---

### Observer
**Intent**: Define a one-to-many dependency where observers are notified of state changes.

**When to Use**:
- Change notification is needed
- Broadcast communication is required

**Variants**: Push vs. pull observer pattern

---

### State
**Intent**: Allow an object to alter behavior when its internal state changes.

**When to Use**:
- Behavior depends on state
- Operations have large conditional statements

---

### Strategy
**Intent**: Define a family of algorithms and make them interchangeable.

**When to Use**:
- Multiple algorithms for a specific behavior
- Interchangeable algorithms without modifying context

---

### Template Method
**Intent**: Define the skeleton of an algorithm, deferring some steps to subclasses.

**When to Use**:
- Invariant parts of an algorithm with variable steps
- Common behavior with customization points

---

### Visitor
**Intent**: Separate algorithms from the object structure they operate on.

**When to Use**:
- Operations on a complex object structure
- Adding operations without modifying existing classes

---

## Pattern Selection Guide

| Problem | Patterns to Consider |
|---------|---------------------|
| Object creation | Factory, Abstract Factory, Builder, Prototype |
| Object structure | Adapter, Bridge, Composite, Decorator, Facade, Proxy |
| Object behavior | Chain of Responsibility, Command, Iterator, Observer, State, Strategy |

---

## Related

- [SOLID Design Principles](01-SOLID-Design-Principles.md)
- [Architectural Patterns](04-Architectural-Patterns.md)
- [Pattern Index by Problem](15-Pattern-Index-by-Problem.md)
