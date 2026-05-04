# AI-Assistant Design-Decision Playbook

*Guidelines for effective collaboration with AI in design decisions*

---

## Overview

AI assistants excel at implementation but need human direction for design decisions. This playbook helps you leverage AI effectively while maintaining architectural integrity.

## Core Principle

> **"You are the architect. AI is the implementation engine."**

AI can:
- Generate code patterns
- Explain trade-offs between options
- Apply patterns to specific contexts
- Implement based on your direction

AI cannot (well):
- Understand your business context deeply
- Make value judgments about trade-offs
- Know when patterns don't fit your situation

---

## Collaboration Model

### Human Responsibilities
- Define the problem space
- Evaluate and choose among alternatives
- Assess fit for context
- Make trade-off decisions
- Review and approve AI output

### AI Responsibilities
- Generate implementation code
- Apply patterns following direction
- Explain technical options
- Suggest alternatives when asked
- Refactor and iterate based on feedback

---

## Workflows

### 1. Problem Definition

**You provide**:
- Clear problem statement
- Constraints and requirements
- Success criteria

**AI responds with**:
- Clarifying questions
- Relevant patterns to consider
- Initial approach suggestions

**Best Practice**: Don't ask AI to "design a system." Ask it to help you evaluate approaches to a defined problem.

---

### 2. Pattern Selection

**You provide**:
- The problem to solve
- Context about your architecture
- Any existing patterns in use

**AI responds with**:
- Pattern options with rationale
- Trade-off analysis
- Simple examples in your context

**Best Practice**: When AI suggests a pattern, verify it fits before proceeding.

---

### 3. Implementation

**You provide**:
- Selected pattern
- Specific requirements
- Code standards to follow

**AI responds with**:
- Implementation code
- Explanation of structure
- Test suggestions

**Best Practice**: Review AI code carefully. Understand each section before accepting.

---

### 4. Code Review

**You provide**:
- AI-generated code
- Context files for reference

**AI responds with**:
- Analysis of potential issues
- Improvement suggestions
- Security considerations

**Best Practice**: Use AI for review, but make acceptance decisions yourself.

---

## Prompting Strategies

### Instead of Generic Prompts
```
❌ "Write a user service"
```

### Use Context-Rich Prompts
```
✅ "Implement a UserService following Hexagonal Architecture:
   - Ports: UserRepository (secondary), UserNotifier (secondary)
   - Domain: User entity with email verification logic
   - Use existing project context in context/project-overview.md
   - Follow code standards in context/code-standards.md"
```

---

## Anti-Patterns to Avoid

### Context Blindness
**Problem**: Expecting AI to understand your project without context.

**Solution**: Always provide relevant context files or summarize key points.

---

### Delegating Design Decisions
**Problem**: Asking AI to "decide the best architecture."

**Solution**: Use AI to explore options, but make design decisions yourself.

---

### Approval Without Understanding
**Problem**: Accepting AI output without reviewing it.

**Solution**: Understand every line before approving. AI can introduce subtle issues.

---

### Over-Prompting
**Problem**: Elaborate prompt engineering instead of solid context.

**Solution**: Invest in context files. Good context reduces prompt complexity.

---

## Context for AI Collaboration

Ensure AI has access to:

| Context Type | Purpose |
|--------------|---------|
| Project Overview | Understanding goals and scope |
| Architecture | Design decisions and structure |
| Code Standards | Formatting and style expectations |
| AI Workflow Rules | Interaction guidelines |
| Relevant Patterns | Pattern knowledge for reference |

---

## Handling AI Limitations

### Hallucinations
AI may confidently state incorrect information.
**Mitigation**: Verify facts, especially when referring to external systems or documentation.

### Generic Solutions
AI may provide one-size-fits-all implementations.
**Mitigation**: Provide specific context; customize recommendations.

### Pattern Force-Fitting
AI may apply patterns inappropriately.
**Mitigation**: Evaluate pattern fit yourself; don't accept pattern suggestions blindly.

### Outdated Knowledge
AI training data may be older than recent best practices.
**Mitigation**: Cross-reference with current documentation.

---

## Effective Questions to Ask AI

### For Exploration
- "What patterns address [problem]? What are their trade-offs?"
- "What are the implications of [approach] vs [alternative]?"
- "What could go wrong with [design]?"

### For Implementation
- "Show me how to apply [pattern] to [specific case]"
- "What would this look like following [architecture]?"
- "Generate an implementation with these constraints..."

### For Review
- "What issues do you see in this code?"
- "Does this follow [standard/convention]?"
- "What improvements would you suggest?"

---

## Summary

| Phase | Your Role | AI's Role |
|-------|-----------|-----------|
| Problem Definition | Define clearly | Ask clarifying questions |
| Pattern Selection | Evaluate fit | Explain options |
| Implementation | Direct the approach | Generate code |
| Review | Approve decisions | Identify issues |

---

## Related

- [Design Decision Framework](02-Design-Decision-Framework.md)
- [Context Folder Template](14-Project-Context-Folder-Template.md)
- [SOLID Principles](01-SOLID-Design-Principles.md)
