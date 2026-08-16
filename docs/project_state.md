# État du projet

## Objectif courant

Valider la flotte adaptative complète sur un premier projet pilote avant toute
mise en production.

## Phase

Phase 3 — Orchestration adaptative prête pour une expérience de bout en bout.

## Flotte active

| Agent | Responsabilité | État |
|---|---|---|
| `orchestrator` | Décomposer et coordonner | configuré |
| `product_manager` | Formaliser le besoin produit | configuré |
| `user_researcher` | Produire des enseignements utilisateurs | configuré |
| `ux_ui_designer` | Concevoir l'expérience et l'interface | configuré |
| `solution_architect` | Définir l'architecture | configuré |
| `data_engineer` | Concevoir données et migrations | configuré |
| `implementation_engineer` | Implémenter | configuré |
| `qa_reviewer` | Vérifier indépendamment | configuré |
| `security_engineer` | Évaluer les risques de sécurité | configuré |
| `devops_engineer` | Préparer la livraison | configuré |
| `documentation_writer` | Maintenir la documentation | configuré |
| `site_reliability_engineer` | Préparer la fiabilité opérationnelle | configuré |
| `release_manager` | Consolider la préparation de version | configuré |

## Décisions

- Git conserve les règles, décisions et livrables durables.
- Les secrets, caches, journaux et états d'exécution restent hors de Git.
- La flotte comprend treize rôles, sélectionnés de manière adaptative.
- Les interactions utilisent un contrat de transmission commun.
- Trois tâches indépendantes au maximum peuvent être exécutées en parallèle.
- Trois corrections infructueuses sur une même porte déclenchent une escalade
  humaine.
- Seul l'humain autorise une action de production.

## Prochaine expérience

Faire traverser à un petit projet pilote le cycle adaptatif complet, depuis le
cadrage produit jusqu'à une recommandation de version sans déploiement réel.

## Critère de passage à la phase 4

Le projet pilote produit des transmissions traçables, franchit toutes les portes
requises, démontre au moins une boucle de correction et aboutit à une décision
humaine documentée.
