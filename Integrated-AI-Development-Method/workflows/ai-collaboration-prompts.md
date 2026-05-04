# AI Collaboration Prompts

*Reusable prompts for effective AI collaboration*

---

## Overview

These prompts provide templates for common AI collaboration scenarios. Customize them with your specific context.

---

## Code Generation Prompts

### Generate Feature Implementation

```
Generate a [feature type] for [project name] with the following specifications:

**Feature Description:**
[Clear description of what the feature should do]

**Context:**
- Project: [Brief project description]
- Architecture: [Brief architecture overview]
- Patterns in use: [List relevant patterns]

**Requirements:**
- [Functional requirement 1]
- [Functional requirement 2]

**Code Standards:**
- Follow [naming convention]
- Include documentation for [what]
- Handle errors by [approach]

**Patterns to Apply:**
- [Pattern 1]: [How to apply]
- [Pattern 2]: [How to apply]

**Acceptance Criteria:**
- [ ] [Criterion 1]
- [ ] [Criterion 2]

Please provide:
1. Implementation code
2. Explanation of structure
3. Suggested unit tests
4. Any concerns or trade-offs
```

---

### Generate Unit Tests

```
Generate unit tests for [component/class/function]:

**Code to Test:**
```
[Code to test]
```

**Testing Standards:**
- Framework: [e.g., Jest, pytest, JUnit]
- Naming: [convention]
- Coverage target: [percentage]

**Test Cases to Include:**
- Happy path: [description]
- Edge case 1: [description]
- Edge case 2: [description]
- Error handling: [description]

**Mock Dependencies:**
- [Dependency 1]: [how to mock]
- [Dependency 2]: [how to mock]

Please provide tests with descriptive names and clear assertions.
```

---

### Apply Design Pattern

```
Apply the [pattern name] pattern to [context]:

**Problem to Solve:**
[Description of the problem]

**Current Code:**
```
[current code structure]
```

**Target Structure:**
[Description of desired outcome]

**Constraints:**
- [Constraint 1]
- [Constraint 2]

Please show:
1. Refactored code applying the pattern
2. Explanation of the transformation
3. Benefits of this pattern in this context
```

---

## Code Review Prompts

### Review Implementation

```
Review the following implementation for [purpose]:

**Code:**
```
[code to review]
```

**Context:**
- Project: [project description]
- Purpose: [what this code should do]
- Dependencies: [list dependencies]

**Review Focus Areas:**
- [ ] Correctness
- [ ] Security
- [ ] Performance
- [ ] Maintainability
- [ ] Pattern adherence

Please identify:
1. Any issues or bugs
2. Security concerns
3. Performance implications
4. Suggestions for improvement
```

---

### Review Architecture

```
Review the architecture for [system/component]:

**Current Architecture:**
[Description or diagram]

**Design Decisions:**
- [Decision 1]
- [Decision 2]

**Concerns:**
- [Concern 1]
- [Concern 2]

**Questions:**
1. [Question 1]
2. [Question 2]

Please provide:
1. Assessment of current architecture
2. Potential issues or risks
3. Suggestions for improvement
```

---

## Exploration Prompts

### Explore Patterns for Problem

```
I have the following problem:
[Problem description]

**Context:**
- [Context details]
- [Relevant constraints]

**What I've Considered:**
- [Option 1] - [why it may/may not work]
- [Option 2] - [why it may/may not work]

Please help me explore:
1. What patterns might address this problem?
2. What are the trade-offs of each pattern?
3. Which would you recommend and why?
4. What would implementation look like?
```

---

### Evaluate Alternatives

```
Help me evaluate approaches for [problem]:

**Approach A: [Name]**
- Description: [description]
- Pros: [pros]
- Cons: [cons]

**Approach B: [Name]**
- Description: [description]
- Pros: [pros]
- Cons: [cons]

**My Context:**
- [Context detail 1]
- [Context detail 2]

**My Priorities:**
1. [Priority 1]
2. [Priority 2]

Please analyze:
1. Trade-offs between approaches
2. Fit for my context
3. Risks and mitigations
4. Recommendation with rationale
```

---

## Documentation Prompts

### Generate Documentation

```
Generate documentation for [component/feature]:

**Component:**
```
[code or description]
```

**Documentation Type:**
- [README / API docs / User guide]

**Audience:**
- [Developers / End users / API consumers]

**Sections to Include:**
- [Section 1]
- [Section 2]

**Style:**
- [Formal / Tutorial / Reference]

Please provide well-structured documentation appropriate for the audience.
```

---

### Update Context Files

```
Help me update [context file] to reflect [change]:

**Current State:**
[Current content summary]

**Changes Made:**
- [Change 1]
- [Change 2]

**Purpose:**
[Why these changes were made]

Please suggest updates to the context file that accurately reflect the new state.
```

---

## Quick Reference

| Scenario | Prompt Type | Key Elements |
|----------|-------------|--------------|
| New feature | Code Generation | Requirements, patterns, standards |
| Tests | Code Generation | Code to test, cases, mocking |
| Pattern application | Code Generation | Pattern, current code, target |
| Review | Code Review | Code, focus areas, context |
| Exploration | Exploration | Problem, context, alternatives |
| Documentation | Documentation | Component, audience, sections |

---

## Related

- [AI Workflow Rules](../../context/ai-workflow-rules.md)
- [AI-Assistant Design-Decision Playbook](../../wiki/13-AI-Assistant-Design-Decision-Playbook.md)
