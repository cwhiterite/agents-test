# Software Design Principles and Patterns Wiki

This repository contains a GitHub-wiki-ready knowledge base for software engineering design principles, design patterns, architecture patterns, and AI-assisted project decision making.

The goal is not to collect patterns as trivia. The goal is to create a practical reference that helps humans and AI assistants make better design decisions inside real projects.

Use this repository to:

- Learn and compare SOLID principles and software design patterns.
- Guide architecture and implementation decisions with trade-off thinking.
- Give AI assistants stable design vocabulary and project context.
- Create reusable `context/` folders for projects so AI agents understand architecture, coding standards, UI context, workflow rules, and progress.
- Record design decisions with ADRs.

## Repository Contents

```text
i-need-to-research-and-create/
  README.md
  wiki/
    Home.md
    _Sidebar.md
    00-How-to-Use-This-Wiki.md
    01-SOLID-Design-Principles.md
    02-Design-Decision-Framework.md
    03-GoF-Object-Oriented-Patterns.md
    04-Architectural-Patterns.md
    05-Enterprise-Application-Patterns.md
    06-Integration-and-Messaging-Patterns.md
    07-Cloud-and-Distributed-Systems-Patterns.md
    08-Data-and-Domain-Patterns.md
    09-UI-and-Frontend-Patterns.md
    10-Concurrency-Patterns.md
    11-Testing-and-Quality-Patterns.md
    12-Anti-Patterns.md
    13-AI-Assistant-Design-Decision-Playbook.md
    14-Project-Context-Folder-Template.md
    15-Pattern-Index-by-Problem.md
    16-Security-and-API-Patterns.md
    99-Sources-and-Further-Reading.md
  project-context-template/
    ai-workflow-rules.md
    project-overview.md
    project-architecture.md
    code-standards.md
    ui-context.md
    progress-tracker.md
    decisions/
      ADR-000-template.md
```

## What Is in the Wiki

The `wiki/` directory is designed to be copied directly into a GitHub Wiki repository.

### Main Pages

- `Home.md`: Wiki landing page and navigation.
- `_Sidebar.md`: GitHub Wiki sidebar navigation.
- `00-How-to-Use-This-Wiki.md`: How humans and AI assistants should use the wiki.
- `01-SOLID-Design-Principles.md`: Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion.
- `02-Design-Decision-Framework.md`: A repeatable process for making design choices.
- `03-GoF-Object-Oriented-Patterns.md`: The 23 Gang of Four patterns.
- `04-Architectural-Patterns.md`: Layered, hexagonal, clean architecture, microservices, modular monoliths, CQRS, event-driven architecture, and related styles.
- `05-Enterprise-Application-Patterns.md`: Domain logic, persistence, transaction, and web presentation patterns.
- `06-Integration-and-Messaging-Patterns.md`: Enterprise integration and message routing patterns.
- `07-Cloud-and-Distributed-Systems-Patterns.md`: Reliability, scaling, API gateway, saga, outbox, strangler fig, and cloud patterns.
- `08-Data-and-Domain-Patterns.md`: Domain-driven design, persistence, and data architecture patterns.
- `09-UI-and-Frontend-Patterns.md`: Frontend architecture, state, data fetching, interaction, and accessibility patterns.
- `10-Concurrency-Patterns.md`: Coordination, async, worker, actor, lock, and backpressure patterns.
- `11-Testing-and-Quality-Patterns.md`: Test structure, test doubles, contract testing, characterization testing, and rollout quality patterns.
- `12-Anti-Patterns.md`: Common design traps and better directions.
- `13-AI-Assistant-Design-Decision-Playbook.md`: Prompt and output structure for design work with AI assistants.
- `14-Project-Context-Folder-Template.md`: Explains the reusable project context folder.
- `15-Pattern-Index-by-Problem.md`: Problem-first lookup table for choosing pattern families.
- `16-Security-and-API-Patterns.md`: Identity, authorization, boundary protection, secrets, and API evolution patterns.
- `99-Sources-and-Further-Reading.md`: Source links and recommended books.

## What Is in the Project Context Template

The `project-context-template/` directory is a reusable starting point for each software project.

For a real project, copy it into the project root as:

```text
context/
  ai-workflow-rules.md
  project-overview.md
  project-architecture.md
  code-standards.md
  ui-context.md
  progress-tracker.md
  decisions/
    ADR-000-template.md
```

Each file has a specific job:

| File | Purpose |
| --- | --- |
| `ai-workflow-rules.md` | Rules for how AI agents should work in the project. |
| `project-overview.md` | Product purpose, users, goals, non-goals, constraints, and success metrics. |
| `project-architecture.md` | Architecture style, module boundaries, dependency rules, data flow, integrations, and risks. |
| `code-standards.md` | Language, framework, naming, error handling, testing, tooling, and design conventions. |
| `ui-context.md` | Design system, UX principles, routes, state management, accessibility, and responsive behavior. |
| `progress-tracker.md` | Current objective, tasks, completed work, blockers, decisions needed, and next steps. |
| `decisions/ADR-000-template.md` | Architecture Decision Record template. |

## How to Use This With an AI Assistant

When asking an AI assistant for design help, provide:

1. The relevant files from your project's `context/` folder.
2. Any relevant source files or module summaries.
3. The relevant pages from `wiki/`.
4. The specific design question you want answered.

Recommended prompt:

```text
Use the project context folder and the software design patterns wiki to help make this design decision.

First summarize the problem, forces, constraints, and existing architecture.
Then compare the simplest viable options.
Recommend one approach, explain trade-offs, identify risks, and list implementation steps.
Do not introduce a pattern unless it solves a named force.
Update the progress tracker and draft an ADR if this is an architectural decision.
```

## Design Decision Workflow

Use this workflow for architecture and pattern decisions:

1. State the problem in plain language.
2. Identify the forces: coupling, cohesion, volatility, scale, consistency, latency, reliability, security, operability, team ownership, and user experience.
3. Use `15-Pattern-Index-by-Problem.md` to find candidate pattern families.
4. Compare two or three options.
5. Choose the simplest design that satisfies the named forces.
6. Define tests and operational checks.
7. Record the decision in an ADR.
8. Update `progress-tracker.md`.

## GitHub Wiki Publishing

GitHub Wikis are separate git repositories. If your main repository is:

```text
https://github.com/OWNER/REPO.git
```

Then the wiki repository is usually:

```text
https://github.com/OWNER/REPO.wiki.git
```

To publish these pages:

```powershell
git clone https://github.com/OWNER/REPO.wiki.git
Copy-Item -Path .\wiki\* -Destination .\REPO.wiki\ -Recurse -Force
Set-Location .\REPO.wiki
git add .
git commit -m "Add software design principles and patterns wiki"
git push
```

If the wiki repo does not exist yet, enable the Wiki feature in the GitHub repository settings and create an initial wiki page first.

## Suggested Project Setup Workflow

For each software project:

1. Copy `project-context-template/` into the project as `context/`.
2. Fill in `project-overview.md`.
3. Fill in `project-architecture.md` with current boundaries and dependency rules.
4. Fill in `code-standards.md` with repo-specific commands and conventions.
5. Fill in `ui-context.md` for frontend or product UI work.
6. Use `progress-tracker.md` during implementation.
7. Create ADRs in `context/decisions/` for important architecture decisions.
8. Link relevant wiki pages in ADRs and design discussions.

## Maintenance Guidelines

Keep the wiki and project context useful by updating them when:

- A pattern is adopted or rejected.
- A project architecture boundary changes.
- A new coding standard is introduced.
- A major feature changes the UI or user workflow.
- A design decision is accepted, rejected, or superseded.
- AI assistants repeatedly need context that is not currently documented.

Good project context should be concise, current, and opinionated. Stale context is worse than missing context because it can lead agents toward confident wrong decisions.

## Sources

The wiki summarizes established software design literature and public pattern catalogs, including:

- SOLID design principles.
- Gang of Four object-oriented design patterns.
- Martin Fowler's enterprise application architecture patterns.
- Enterprise Integration Patterns by Gregor Hohpe and Bobby Woolf.
- Microsoft Azure Architecture Center cloud design patterns.
- Microservices patterns from Chris Richardson.
- AWS modernization guidance for the Strangler Fig pattern.

See `wiki/99-Sources-and-Further-Reading.md` for links and recommended books.

## Guiding Principle

Patterns are vocabulary, not goals.

Start with the forces in the problem. Choose the smallest design that makes the system easier to understand, test, operate, and change.

