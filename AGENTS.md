# Instructions communes des agents

## Mission

Ce dépôt est un laboratoire pédagogique pour construire une flotte adaptative
d'agents logiciels. Chaque agent possède une responsabilité principale et
collabore au moyen de livrables vérifiables.

## Principes de travail

1. Lire `README.md`, `docs/project_state.md` et sa fiche de rôle avant d'agir.
2. Travailler uniquement dans le périmètre explicitement confié.
3. Demander un spécialiste lorsqu'une tâche sort de sa responsabilité.
4. Transmettre les résultats avec le format `docs/handoffs/TEMPLATE.md`.
5. Citer les fichiers modifiés et les validations réellement exécutées.
6. Ne jamais déclarer une tâche terminée sans preuve vérifiable.
7. Ne jamais exposer ou versionner de secret, jeton ou donnée personnelle.
8. Demander une autorisation avant toute action destructive ou externe.

## Politique Git

- `main` représente la production et reçoit uniquement `develop`.
- `develop` reçoit les branches de travail après validation.
- Les branches commencent par `feature/`, `bugfix/`, `fix/` ou `chore/`.
- Les mots des noms de branches sont séparés par `_`.
- Un agent ne pousse jamais directement sur `main` ou `develop`.
- Un commit reste synthétique, suit Conventional Commits et contient moins de
  quinze mots.

Exemple :

```text
chore(css): remove unused legacy poll selectors
```

## Limites d'autonomie

Les agents peuvent lire les fichiers, modifier le code demandé et exécuter des
validations locales non destructives. Une confirmation humaine est requise pour
un déploiement, une écriture externe, une suppression importante, une dépense ou
un élargissement matériel du périmètre.

## Routage initial

| Besoin | Agent responsable |
|---|---|
| Décomposer, assigner ou arbitrer | `orchestrator` |
| Clarifier le besoin et les critères produit | `product_manager` |
| Produire ou analyser une recherche utilisateur | `user_researcher` |
| Concevoir les parcours et interfaces | `ux_ui_designer` |
| Définir l'architecture et les contrats | `solution_architect` |
| Concevoir les données et migrations | `data_engineer` |
| Implémenter une modification | `implementation_engineer` |
| Vérifier un livrable | `qa_reviewer` |
| Examiner les risques de sécurité | `security_engineer` |
| Préparer CI/CD et environnements | `devops_engineer` |
| Maintenir la documentation durable | `documentation_writer` |
| Définir fiabilité et réponse aux incidents | `site_reliability_engineer` |
| Consolider la préparation d'une version | `release_manager` |

Le cycle et ses portes sont décrits dans `docs/orchestration/workflow.md`. Tous
les agents ne sont pas convoqués à chaque tâche : l'orchestrateur sélectionne le
plus petit ensemble couvrant le périmètre et les risques.
