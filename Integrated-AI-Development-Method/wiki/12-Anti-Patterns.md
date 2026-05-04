# Anti-Patterns

*Common mistakes and how to avoid them*

---

## Overview

Anti-patterns are common solutions that appear helpful but ultimately cause problems. Recognizing them helps prevent costly mistakes.

## Code-Level Anti-Patterns

### God Object/Class
**Problem**: Single class/module that does too much.

**Symptoms**:
- Class with 50+ methods
- Difficult to test due to many responsibilities
- Fear of changing—affects many parts of system

**Solution**: Apply Single Responsibility Principle, split into focused classes.

---

### Shotgun Surgery
**Problem**: One change requires modifications across many classes.

**Symptoms**:
- Adding a feature requires touching 10+ files
- Changes are scattered and inconsistent
- High coupling

**Solution**: Identify missed abstractions, co-locate related behavior.

---

### Spaghetti Code
**Problem**: Unstructured, tangled control flow.

**Symptoms**:
- Deep nesting, complex control flow
- Few comments explaining intent
- Difficult to trace execution

**Solution**: Refactor to clear structure, extract methods, add meaningful names.

---

### Magic Numbers/Strings
**Problem**: Unnamed constants scattered in code.

**Symptoms**:
- `if (status === 1)` instead of named constants
- Repeated literal values
- Changing a value requires multiple edits

**Solution**: Extract to named constants, enums, or configuration.

---

### Premature Optimization
**Problem**: Optimizing before knowing if it's needed.

**Symptoms**:
- Complex code that handles "future" performance
- Obscured intent for marginal gains
- Wasted development time

**Solution**: Write clear code first, profile to identify bottlenecks.

---

### Copy-Paste Programming
**Problem**: Duplicating code instead of abstracting.

**Symptoms**:
- Nearly identical code blocks
- Bugs fixed in one place but not others
- Bloated codebase

**Solution**: Extract shared behavior into reusable functions/classes.

---

## Design-Level Anti-Patterns

### Cargo Cult Programming
**Problem**: Using patterns/technologies without understanding why.

**Symptoms**:
- "We need microservices because Netflix uses them"
- Patterns applied mechanically without purpose
- Complexity without benefit

**Solution**: Understand the problem the pattern solves before applying it.

---

### Gold Plating
**Problem**: Adding unnecessary features or polish.

**Symptoms**:
- Features that aren't used
- Over-engineered solutions for simple problems
- Scope creep

**Solution**: YAGNI—implement what's needed now, not what might be needed.

---

### Vendor Tunnel Vision
**Problem**: Over-dependence on a single technology vendor.

**Symptoms**:
- Tying everything to proprietary APIs
- No strategy for migration
- Locked into expensive upgrades

**Solution**: Abstract external dependencies, maintain portability.

---

### Big Ball of Mud
**Problem**: System with no clear architecture.

**Symptoms**:
- Everything connects to everything
- No clear boundaries or responsibilities
- Fear of any major change

**Solution**: Identify bounded contexts, establish clear interfaces, incrementally refactor.

---

### Stovepipe Enterprise
**Problem**: Siloed systems that don't communicate effectively.

**Symptoms**:
- Same data maintained in multiple systems
- Manual processes to move data between systems
- Duplicated functionality

**Solution**: Establish integration points, consider ESB or messaging.

---

## Architecture-Level Anti-Patterns

### Waterfall Development
**Problem**: Rigid, sequential phase-based approach.

**Symptoms**:
- Requirements "finalized" before design begins
- Late discovery of fundamental problems
- Resistance to change

**Solution**: Adopt iterative development, continuous feedback.

---

### Architecture by Implication
**Problem**: No explicit architectural decisions.

**Symptoms**:
- Architecture exists only in developers' heads
- Inconsistent implementation
- Difficulty onboarding new team members

**Solution**: Document architecture explicitly, maintain ADRs.

---

### Design by Committee
**Problem**: Too many decision-makers with no clear direction.

**Symptoms**:
- Inconsistent architecture
- Feature flags for pet features
- Committee-designed Frankenstein

**Solution**: Design authority with clear process for input.

---

## AI Collaboration Anti-Patterns

### Context Blindness
**Problem**: Not providing context to AI, expecting mind-reading.

**Symptoms**:
- Generic AI responses that don't fit the project
- Repeated corrections
- Frustration with AI output

**Solution**: Provide comprehensive context files, reference architecture.

---

### Prompt Engineering Over Context
**Problem**: Spending more time on prompts than context.

**Symptoms**:
- Elaborate prompt engineering
- Fragile, context-dependent results
- AI behavior varies wildly with prompt changes

**Solution**: Invest in solid context; prompts become simpler.

---

### Approval Without Review
**Problem**: Accepting AI output without understanding it.

**Symptoms**:
- Bugs introduced that "shouldn't be there"
- Code that doesn't match requirements
- Accumulated technical debt

**Solution**: Always review AI output; understand before approving.

---

## Recognition Checklist

| Anti-Pattern | Quick Check |
|--------------|-------------|
| God Object | Does one class exceed 500 lines? |
| Shotgun Surgery | Does one change require 5+ file edits? |
| Magic Numbers | Are there unnamed constants in code? |
| Gold Plating | Are all features actually used? |
| Big Ball of Mud | Can you trace data flow easily? |

---

## Related

- [SOLID Design Principles](01-SOLID-Design-Patterns.md)
- [Design Decision Framework](02-Design-Decision-Framework.md)
- [Pattern Index by Problem](15-Pattern-Index-by-Problem.md)
