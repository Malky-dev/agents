# Adaptive Agent Fleet

Laboratoire pédagogique pour concevoir une flotte adaptative d'agents capable
d'accompagner un projet depuis l'idée jusqu'à la production.

## Branches

- `main` : production ; reçoit uniquement `develop`.
- `develop` : intégration et validation.
- `feature/*`, `bugfix/*`, `fix/*`, `chore/*` : branches de travail.

Les mots d'un nom de branche sont séparés par `_`.

## Flotte

La flotte comprend treize rôles spécialisés et reste adaptative :

- l'orchestrateur sélectionne uniquement les spécialistes nécessaires ;
- les travaux indépendants peuvent être parallélisés dans la limite configurée ;
- chaque passage utilise un contrat de transmission vérifiable ;
- les contrôles échoués retournent à l'auteur avant une nouvelle validation ;
- toute mise en production reste soumise à une décision humaine.

Le [workflow d'orchestration](docs/orchestration/workflow.md) décrit les phases,
les portes, les boucles de correction et les responsabilités.

## Parcours pédagogique

- [Instructions communes](AGENTS.md)
- [Leçon 1 : contrats des agents](docs/learning/01_agent_contracts.md)
- [Leçon 2 : agents exécutables](docs/learning/02_executable_agents.md)
- [État courant](docs/project_state.md)
- [Modèle de transmission](docs/handoffs/TEMPLATE.md)
- [Workflow d'orchestration](docs/orchestration/workflow.md)

Les fichiers de `agents/` documentent les rôles. Les configurations exécutables
correspondantes vivent dans `.codex/agents/` et la flotte est réglée par
`.codex/config.toml`.
