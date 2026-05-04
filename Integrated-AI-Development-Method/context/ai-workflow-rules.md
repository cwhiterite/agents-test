# AI Workflow Rules

*Template for documenting guidelines for AI interactions*

---

## General Principles

1. **Context First**: Always read relevant context files before making changes
2. **Preserve Intent**: Don't change functionality without explicit approval
3. **Explain Changes**: When modifying code, explain what and why
4. **Ask for Clarification**: When requirements are ambiguous, ask

## Interaction Patterns

### When Starting a Task
- [ ] Read project overview
- [ ] Review relevant architecture decisions
- [ ] Check progress tracker for current state
- [ ] Identify affected components

### When Making Changes
- [ ] Follow code standards exactly
- [ ] Update related documentation
- [ ] Consider ripple effects on dependencies
- [ ] Test changes locally if possible

### When Facing Ambiguity
- [ ] State assumptions clearly
- [ ] Propose multiple approaches if unclear
- [ ] Wait for confirmation before proceeding
- [ ] Document the ambiguity for future reference

## Prohibited Actions

- DO NOT modify files outside the scope of the current task
- DO NOT introduce breaking changes without approval
- DO NOT skip error handling or validation
- DO NOT hardcode sensitive values
- DO NOT reduce test coverage

## Code Generation Guidelines

### Required Outputs
- [What the AI must always produce]

### Quality Gates
- [Quality requirements before presenting code]

### Pattern Usage
- [When to apply specific patterns]
- [When to avoid force-fitting patterns]

## Communication Style

- Be concise but complete
- Use technical precision
- Provide code with explanations
- Highlight trade-offs when relevant
- Include usage examples where helpful

## Task-Specific Rules

### [Task Type 1]
[Specific rules for this task type]

### [Task Type 2]
[Specific rules for this task type]

---

*Last updated: [Date]*
