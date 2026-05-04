# Refactoring Workflow

*Standard workflow for safely refactoring code with AI assistance*

---

## Overview

Refactoring improves code quality without changing behavior. This workflow ensures safe, incremental refactoring with preserved context.

## Golden Rule

> **Never refactor without tests. If tests don't exist, create them first.**

---

## Phase 1: Assessment

### Before Refactoring
- [ ] Identify code to refactor
- [ ] Understand current behavior
- [ ] Review existing tests
- [ ] Identify dependencies

### Key Questions
- Why is this code being refactored?
- What specific problems exist?
- What is the scope of changes?
- What could break if we change this?

---

## Phase 2: Protect

### Create Safety Net
- [ ] Ensure tests exist covering the code
- [ ] Run tests to establish baseline
- [ ] Document current behavior
- [ ] Identify integration points

### Backup Plan
- [ ] Note how to rollback if needed
- [ ] Identify checkpoints for testing

---

## Phase 3: Plan

### Refactoring Plan
- [ ] Break into small, incremental steps
- [ ] Order changes for minimal risk
- [ ] Identify patterns to apply
- [ ] Set intermediate verification points

### Incremental Approach

| Step | Change | Verification |
|------|--------|---------------|
| 1 | [Small change 1] | [Test to run] |
| 2 | [Small change 2] | [Test to run] |
| 3 | [Small change 3] | [Test to run] |

---

## Phase 4: Execute

### Implementation
- Make one change at a time
- Run tests after each change
- Commit after each successful step

### AI Collaboration

**When asking AI to refactor:**
```
Provide:
- Current code to refactor
- Reason for refactoring
- Target pattern or structure
- Code standards to follow

Expect:
- Refactored code with explanation
- Behavior preserved (verified by tests)
- Any concerns noted
```

---

## Phase 5: Verify

### Verification Checklist
- [ ] All tests pass
- [ ] Behavior unchanged
- [ ] Code follows standards
- [ ] No new code smells introduced
- [ ] Documentation still accurate

### Common Refactoring Issues

| Issue | Detection | Fix |
|-------|-----------|-----|
| Behavior change | Test failure | Revert and replan |
| Incomplete extraction | Duplicated logic | Complete the extraction |
| Over-engineering | Unnecessary complexity | Simplify |

---

## Phase 6: Complete

### Final Checklist
- [ ] Tests pass consistently
- [ ] Code review completed
- [ ] Old code removed
- [ ] Context files updated if needed
- [ ] Progress tracker updated

---

## Quick Reference

| Phase | Focus | Key Action |
|-------|-------|------------|
| Assessment | Understanding | Review code and tests |
| Protect | Safety | Ensure test coverage |
| Plan | Incremental steps | Break into small changes |
| Execute | One change at a time | Test after each step |
| Verify | Behavior preserved | Run full test suite |
| Complete | Cleanup | Update documentation |

---

## Related

- [Code Standards](../../context/code-standards.md)
- [SOLID Principles](../../wiki/01-SOLID-Design-Principles.md)
- [Anti-Patterns](../../wiki/12-Anti-Patterns.md)
