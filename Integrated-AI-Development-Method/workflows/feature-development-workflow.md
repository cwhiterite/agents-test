# Feature Development Workflow

*Standard workflow for implementing features with AI assistance*

---

## Overview

This workflow guides feature development from planning through implementation, ensuring consistent quality and context preservation.

## Phase 1: Plan

### Before Starting
- [ ] Define the feature using [Feature Planning Template](../brainstorming/feature-planning-template.md)
- [ ] Review relevant context files
- [ ] Identify dependencies and blockers

### Key Questions
- What problem does this feature solve?
- What are the acceptance criteria?
- What patterns should we apply?
- What existing code does this interact with?

---

## Phase 2: Context

### Prepare Context
- [ ] Update `context/progress-tracker.md` with new task
- [ ] Create ADR if significant design decision required
- [ ] Document any new design decisions in relevant context files

### Reference Materials
- [ ] Project overview: `context/project-overview.md`
- [ ] Architecture: `context/architecture.md`
- [ ] Code standards: `context/code-standards.md`
- [ ] Relevant wiki pages for patterns

---

## Phase 3: Build

### Implementation Steps

1. **Setup**
   - Create branch for feature
   - Ensure development environment is ready

2. **Foundation**
   - Implement data model changes
   - Create or modify API endpoints
   - Set up dependencies

3. **Core Logic**
   - Implement business logic
   - Apply appropriate patterns
   - Follow code standards

4. **Integration**
   - Connect components
   - Implement UI if applicable
   - Wire up event handlers

5. **Testing**
   - Write unit tests
   - Write integration tests
   - Verify acceptance criteria

### AI Collaboration

**When asking AI to implement:**
```
Provide:
- Feature description
- Relevant context summary
- Code standards to follow
- Pattern guidance if applicable
- Acceptance criteria

Expect:
- Implementation with explanation
- Any concerns or trade-offs noted
- Suggested tests
```

---

## Phase 4: Review

### Self-Review Checklist
- [ ] Code follows standards
- [ ] Tests cover happy path and edge cases
- [ ] No unintended side effects
- [ ] Documentation updated
- [ ] Context files reflect final state

### AI-Assisted Review
Ask AI to review the implementation for:
- Potential bugs or issues
- Security concerns
- Performance implications
- Pattern violations

---

## Phase 5: Complete

### Pre-Merge Checklist
- [ ] All tests pass
- [ ] Code reviewed and approved
- [ ] Documentation complete
- [ ] Context files updated
- [ ] Progress tracker updated

### Post-Implementation
- [ ] Merge to main branch
- [ ] Deploy to appropriate environment
- [ ] Monitor for issues
- [ ] Update progress tracker

---

## Quick Reference

| Step | Key Question | Output |
|------|-------------|--------|
| Plan | What are we building? | Feature plan |
| Context | What does AI need to know? | Updated context files |
| Build | How do we implement it? | Working code |
| Review | Does it meet criteria? | Approved code |
| Complete | Is it ready to ship? | Deployed feature |

---

## Related

- [Feature Planning Template](../brainstorming/feature-planning-template.md)
- [Problem Exploration Template](../brainstorming/problem-exploration-template.md)
- [AI Workflow Rules](../../context/ai-workflow-rules.md)
