# Agent Fleet Operating Policy

## Purpose

This repository defines a production-oriented, adaptive fleet of specialized
software delivery agents. Each agent owns one primary responsibility and
collaborates through bounded assignments, explicit evidence, and auditable
handoffs.

## Operating Rules

1. Read `README.md`, `docs/orchestration/workflow.md`, the assigned task, and the
   relevant agent configuration before acting.
2. Work only within the explicitly assigned scope.
3. Request the appropriate specialist when work falls outside the assigned role.
4. Use `docs/handoffs/TEMPLATE.md` for durable cross-agent handoffs.
5. Report changed artifacts, decisions, validations actually executed, and
   residual risks.
6. Never declare completion without verifiable evidence.
7. Never expose or commit secrets, credentials, personal data, or sensitive
   operational information.
8. Obtain human approval before destructive actions, external writes, material
   costs, scope expansion, accepted high or critical risks, or production work.

## Git Policy

- `main` represents production and receives changes only from `develop`.
- `develop` is the integration and validation branch.
- Work branches use `feature/`, `bugfix/`, `fix/`, or `chore/` prefixes.
- Words in branch names are separated with underscores.
- Agents never push directly to `main` or `develop`.
- Commit messages follow Conventional Commits, remain concise, and contain fewer
  than fifteen words.

Example:

```text
chore(css): remove unused legacy poll selectors
```

## Autonomy Boundaries

Agents may inspect repository content, modify in-scope workspace files, and run
safe local validation. Human approval is required for production deployments,
production data access, sensitive external writes, destructive operations,
financial commitments, material scope changes, and risk acceptance.

## Responsibility Routing

| Need | Responsible agent |
|---|---|
| Decompose, assign, coordinate, or escalate work | `orchestrator` |
| Define product outcomes and acceptance criteria | `product_manager` |
| Plan or analyze user research | `user_researcher` |
| Design journeys, interactions, and interfaces | `ux_ui_designer` |
| Define architecture and technical boundaries | `solution_architect` |
| Design data contracts, models, and migrations | `data_engineer` |
| Implement product changes | `implementation_engineer` |
| Independently verify deliverables | `qa_reviewer` |
| Assess security threats and findings | `security_engineer` |
| Build delivery automation and environments | `devops_engineer` |
| Maintain durable documentation | `documentation_writer` |
| Define reliability and incident response | `site_reliability_engineer` |
| Consolidate release readiness | `release_manager` |

The orchestrator selects the smallest set of agents required by the scope and
risk. The authoritative lifecycle, gates, correction loops, and approval rules
are defined in `docs/orchestration/workflow.md`.
