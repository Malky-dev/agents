# Adaptive Agent Fleet

Laboratoire pédagogique pour concevoir une flotte adaptative d'agents capable
d'accompagner un projet depuis l'idée jusqu'à la production.

## Branches

- `main` : production ; reçoit uniquement `develop`.
- `develop` : intégration et validation.
- `feature/*`, `bugfix/*`, `fix/*`, `chore/*` : branches de travail.

Les mots d'un nom de branche sont séparés par `_`.

## Démarrage

La première version de la flotte sera volontairement réduite à trois rôles :

1. orchestrateur ;
2. ingénieur d'implémentation ;
3. responsable qualité.

Chaque extension sera ajoutée lorsqu'une responsabilité distincte le justifiera.

## Parcours pédagogique

- [Instructions communes](AGENTS.md)
- [Leçon 1 : contrats des agents](docs/learning/01_agent_contracts.md)
- [État courant](docs/project_state.md)
- [Modèle de transmission](docs/handoffs/TEMPLATE.md)

Les fichiers de `agents/` définissent les rôles. Ils ne constituent pas encore
une application d'orchestration : cette automatisation sera construite après la
validation manuelle du premier cycle complet.
