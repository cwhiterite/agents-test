# SOLID Design Principles

*Fundamental object-oriented design principles for creating maintainable software*

---

## Overview

SOLID principles guide object-oriented design toward code that is more maintainable, flexible, and testable.

## S - Single Responsibility Principle (SRP)

> A class should have only one reason to change.

### Intent
Each class should have one responsibility, encapsulated within its boundaries.

### Example
```
✅ Good: UserRepository, UserService, UserValidator
❌ Bad: UserManager (handles persistence, validation, AND business logic)
```

### Signs of Violation
- Difficult to test due to many dependencies
- Changes to one aspect affect the entire class
- Class name contains "And" or multiple concepts

---

## O - Open/Closed Principle (OCP)

> Software entities should be open for extension, closed for modification.

### Intent
Allow behavior extension without modifying existing code.

### Example
```
✅ Good: Strategy pattern - add new strategies without changing the context
❌ Bad: Add new payment types by modifying a switch statement in existing code
```

---

## L - Liskov Substitution Principle (LSP)

> Objects of a superclass should be replaceable with objects of a subclass without affecting correctness.

### Intent
Subclasses must honor the contract established by their parent.

### Example
```
✅ Good: Square extends Rectangle, but only if it truly behaves like a rectangle
❌ Bad: Penguin extends Bird but can't fly - violates the "is-a" relationship
```

### Checklist
- Subtypes must implement all parent methods
- Preconditions cannot be strengthened
- Postconditions cannot be weakened
- Invariants must be preserved

---

## I - Interface Segregation Principle (ISP)

> Clients should not be forced to depend on methods they do not use.

### Intent
Prefer small, focused interfaces over large, general-purpose ones.

### Example
```
✅ Good: Printer, Scanner, Fax as separate interfaces
❌ Bad: IMultiFunctionDevice with print(), scan(), fax() that no single class uses fully
```

---

## D - Dependency Inversion Principle (DIP)

> High-level modules should not depend on low-level modules. Both should depend on abstractions.

### Intent
Decouple code by depending on abstractions, not concrete implementations.

### Example
```
✅ Good: UserService depends on IUserRepository (interface), not SqlUserRepository
❌ Bad: UserService directly instantiates new SqlUserRepository()
```

### Implementation
- Depend on interfaces or abstract classes
- Let the container/framework handle concrete implementations
- Use dependency injection

---

## Applying SOLID

| Principle | Ask Yourself | Refactoring Hint |
|-----------|--------------|------------------|
| SRP | Does this class have one reason to change? | Split into smaller classes |
| OCP | Can I extend behavior without modifying code? | Use strategy/template patterns |
| LSP | Can I substitute subclasses freely? | Redesign inheritance hierarchy |
| ISP | Am I implementing methods I don't use? | Split large interfaces |
| DIP | Do I depend on abstractions, not concretions? | Introduce interfaces, use DI |

## When to Apply

- **During design**: Use SOLID to evaluate proposed structures
- **During review**: Identify violations and propose fixes
- **During refactoring**: Use SOLID as a guide for breaking apart monoliths

## Limitations

SOLID principles are guidelines, not rules. Apply them judiciously:
- Over-engineering can be worse than simple violations
- Small, simple classes may not need full decomposition
- Context matters—embedded systems differ from enterprise applications

## Related

- [GoF Object-Oriented Patterns](03-GoF-Object-Oriented-Patterns.md)
- [Anti-Patterns](12-Anti-Patterns.md)
