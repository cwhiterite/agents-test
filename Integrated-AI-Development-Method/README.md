# Integrated Context-Driven AI Development Method (ICDADM)

A unified approach combining tactical execution with strategic design knowledge for effective AI-assisted development.

---

## Purpose

The **Integrated Context-Driven AI Development Method (ICDADM)** unifies two complementary approaches:

| Approach | Focus | Key Components |
|----------|-------|----------------|
| **Tactical Execution** | Day-to-day implementation | Six-File+Context+Method |
| **Strategic Design** | Long-term architecture | Codex+Context+Wiki |

This synthesis creates a complete workflow where AI serves as a powerful implementation engine while you maintain creative direction and architectural vision.

---

## Core Philosophy

> **"You are the architect. AI is the implementation engine."**

> **"Patterns are vocabulary, not goals."**

### What This Means

- **You** define the problem space, make design decisions, and evaluate solutions
- **AI** accelerates implementation, generates code patterns, and handles routine tasks
- **Patterns** provide shared language for communication—not templates to force-fit onto problems

The relationship is collaborative: your judgment guides the work, while AI amplifies your productivity.

---

## Folder Structure

```
Integrated-AI-Development-Method/
├── README.md                          # This file
├── context/                           # Project context template files
│   ├── project-overview.md            # Project vision and goals
│   ├── architecture.md                # System design and structure
│   ├── code-standards.md              # Coding conventions and practices
│   ├── ui-context.md                  # User interface design decisions
│   ├── ai-workflow-rules.md          # AI interaction guidelines
│   ├── progress-tracker.md           # Development status and milestones
│   └── decisions/                     # Architecture Decision Records (ADRs)
│       └── ADR-000-template.md       # Template for documenting decisions
├── wiki/                              # Design knowledge base
│   ├── 00-How-to-Use-This-Wiki.md    # Wiki navigation guide
│   ├── 01-SOLID-Design-Principles.md # Object-oriented design fundamentals
│   ├── 02-Design-Decision-Framework.md # Decision-making methodology
│   ├── 03-GoF-Object-Oriented-Patterns.md # Classic OOP patterns
│   ├── 04-Architectural-Patterns.md  # System-level patterns
│   ├── 05-Enterprise-Application-Patterns.md # Enterprise design patterns
│   ├── 06-Integration-and-Messaging-Patterns.md # System integration
│   ├── 07-Cloud-and-Distributed-Systems-Patterns.md # Cloud-native patterns
│   ├── 08-Data-and-Domain-Patterns.md # Data modeling and domain design
│   ├── 09-UI-and-Frontend-Patterns.md # Interface design patterns
│   ├── 10-Concurrency-Patterns.md    # Parallelism and async patterns
│   ├── 11-Testing-and-Quality-Patterns.md # Testing strategies
│   ├── 12-Anti-Patterns.md           # Common mistakes and how to avoid
│   ├── 13-AI-Assistant-Design-Decision-Playbook.md # AI collaboration guide
│   ├── 14-Project-Context-Folder-Template.md # Context template reference
│   ├── 15-Pattern-Index-by-Problem.md # Patterns organized by use case
│   ├── 16-Security-and-API-Patterns.md # Security and API design
│   ├── 99-Sources-and-Further-Reading.md # Learning resources
│   └── _Sidebar.md                   # Wiki navigation sidebar
├── brainstorming/                      # Ideation and planning templates
│   └── (templates for exploration and planning)
└── workflows/                         # Development workflow templates and prompts
    └── (templates for common development tasks)
```

---

## The Three Phases

### Phase 1: Brainstorm

Explore problems, generate ideas, and plan approaches before committing to implementation.

**Key Activities:**
- Problem space exploration
- Requirements gathering
- Solution brainstorming
- Initial architecture sketching

**Artifacts:**
- Problem statements
- Feature ideas
- Rough diagrams
- Decision criteria

---

### Phase 2: Context

Build comprehensive project context that AI can use to maintain consistency and make appropriate decisions.

**Key Activities:**
- Document project overview and goals
- Define architecture and design decisions
- Establish coding standards and conventions
- Record UI/UX decisions
- Create AI workflow rules

**Key Principle:**
> Good context prevents AI from filling gaps with assumptions. The more precise your context, the more aligned the AI's output with your vision.

---

### Phase 3: Build

Execute implementation using the context as a foundation for AI-assisted development.

**Key Activities:**
- Generate code using context-guided AI interactions
- Apply patterns appropriately (not force-fit)
- Iterate based on feedback
- Maintain documentation
- Track progress

**Key Principle:**
> AI is most effective when working from solid context. Build the foundation first, then let AI amplify your implementation capacity.

---

## How to Use This Method

### Getting Started

1. **Create project context** in the `context/` folder
   - Start with `project-overview.md`
   - Define architecture in `architecture.md`
   - Set standards in `code-standards.md`

2. **Consult the wiki** for design patterns and principles
   - Use `Pattern-Index-by-Problem.md` to find relevant patterns
   - Study `Design-Decision-Framework.md` for decision-making methodology
   - Reference `AI-Assistant-Design-Decision-Playbook.md` for effective AI collaboration

3. **Use brainstorming** for exploration
   - When facing ambiguous problems
   - When evaluating multiple approaches
   - When planning new features

4. **Follow workflows** for consistent execution
   - Use templates for common tasks
   - Adapt prompts to your specific needs

### Integration with Existing Methods

This method builds upon and integrates:

- **Six-File+Context+Method**: Tactical execution framework for day-to-day AI interactions
- **Codex+Context+Wiki**: Strategic design knowledge base for architectural decisions

You can use these components together or selectively, depending on your needs.

---

## Design Principles

### 1. Context Over Prompt Engineering

Spend more time building context and less time crafting perfect prompts. Good context enables AI to infer intent.

### 2. Patterns as Vocabulary

Patterns provide shared language, not solutions to force-fit. Understand the problem before reaching for a pattern.

### 3. Human Direction, AI Execution

You maintain creative control. AI handles implementation details and accelerates execution.

### 4. Documentation as Collaboration

Keep context files updated. They're the contract between your vision and AI's understanding.

### 5. Iterate and Refine

Start with essential context, then refine based on AI output and project evolution.

---

## Quick Reference

| Phase | Question to Ask | Primary Folder |
|-------|-----------------|----------------|
| **Brainstorm** | "What are we trying to solve?" | `brainstorming/` |
| **Context** | "What does AI need to know?" | `context/` |
| **Build** | "How do we implement this?" | `workflows/` + wiki |

---

## Contributing

This method is designed to evolve with your practice. When you discover improvements:

1. Update the relevant template or documentation
2. Document new patterns or anti-patterns
3. Refine workflows based on experience

---

## Resources

- [Six-File+Context+Method](../Six-File+Context+Method/README.md) - Tactical execution framework
- [Codex+Context+Wiki](../Codex+Context+Wiki/README.md) - Strategic design knowledge base
- [Wiki Index](wiki/00-How-to-Use-This-Wiki.md) - Complete wiki navigation

---

*You are the architect. AI is the implementation engine.*
