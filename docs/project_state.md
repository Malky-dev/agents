# État du projet

## Objectif courant

Construire et comprendre une flotte adaptative minimale avant d'ajouter des
spécialistes ou une orchestration automatisée.

## Phase

Phase 2 — Configuration exécutable des agents.

## Flotte active

| Agent | Responsabilité | État |
|---|---|---|
| `orchestrator` | Décomposer et coordonner | configuré |
| `implementation_engineer` | Implémenter | configuré |
| `qa_reviewer` | Vérifier indépendamment | configuré |

## Décisions

- Git conserve les règles, décisions et livrables durables.
- Les secrets, caches, journaux et états d'exécution restent hors de Git.
- La flotte commence avec trois rôles et grandit selon les responsabilités.
- Les interactions utilisent un contrat de transmission commun.

## Prochaine expérience

Vérifier la détection des agents dans une nouvelle session, puis faire exécuter
une tâche simple par les trois rôles : planification, implémentation et revue.

## Critère de passage à la phase 3

Une tâche exemple traverse le cycle complet avec un livrable et des preuves
compréhensibles par une personne extérieure au projet.
