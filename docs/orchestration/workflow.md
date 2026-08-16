# Workflow d'orchestration adaptative

## Principe

L'orchestrateur choisit le plus petit ensemble d'agents couvrant le périmètre et
les risques. Une phase facultative peut être ignorée uniquement avec une raison
explicite. Une porte n'est franchie qu'avec des preuves vérifiables.

## Phases et portes

| Porte | Objectif | Responsables habituels | Preuve minimale |
|---|---|---|---|
| `G0_intake` | Comprendre l'objectif et les contraintes | `orchestrator`, humain | objectif, périmètre, contraintes, inconnues |
| `G1_product` | Approuver le problème et les critères | `product_manager`, `user_researcher` si nécessaire | exigences, priorités, critères d'acceptation |
| `G2_design` | Rendre la solution concevable | `ux_ui_designer`, `solution_architect`, `data_engineer`, `security_engineer` selon le risque | parcours, décisions, contrats, menaces et approbations |
| `G3_build` | Produire un incrément vérifiable | `implementation_engineer`, `data_engineer`, `devops_engineer` | modifications, validations locales, migrations et automatisation |
| `G4_verify` | Vérifier indépendamment l'incrément | `qa_reviewer`, `security_engineer` | verdicts, preuves, défauts et risques résiduels |
| `G5_operate` | Préparer l'exploitation et la compréhension | `documentation_writer`, `devops_engineer`, `site_reliability_engineer` | documentation, déploiement, rollback, observabilité et runbooks |
| `G6_release` | Consolider la préparation de version | `release_manager`, humain | manifeste, matrice des portes, risques, décision humaine |

## Sélection adaptative

- `user_researcher` intervient lorsqu'une hypothèse utilisateur importante manque
  de preuve.
- `ux_ui_designer` intervient pour toute expérience visible ou interaction.
- `solution_architect` intervient pour une nouvelle frontière, dépendance ou
  décision structurelle.
- `data_engineer` intervient pour un schéma, une migration, un pipeline ou une
  règle de cycle de vie des données.
- `security_engineer` intervient pour l'identité, les permissions, les secrets,
  les données sensibles, une exposition réseau ou un risque significatif.
- `devops_engineer` intervient pour la construction, les environnements, la
  livraison ou l'infrastructure.
- `site_reliability_engineer` intervient pour un service exploité, un objectif de
  disponibilité, l'observabilité ou la réponse aux incidents.
- `documentation_writer` intervient dès qu'une décision ou un mode opératoire
  doit survivre à la tâche.
- `release_manager` intervient uniquement sur un candidat de version défini.

`product_manager`, `implementation_engineer` et `qa_reviewer` forment le chemin
minimal d'une modification produit. L'orchestrateur et l'humain encadrent toutes
les variantes.

## Parallélisme

Trois missions au maximum s'exécutent simultanément. Le parallélisme est autorisé
si les missions ont des entrées stables, aucune dépendance mutuelle et aucun
fichier partagé susceptible d'être modifié. Les résultats convergent vers une
transmission de synthèse avant la porte suivante.

## Boucle de correction

1. Le contrôleur décrit le critère échoué et fournit sa preuve.
2. L'orchestrateur renvoie une mission bornée à l'auteur responsable.
3. Un contrôleur indépendant vérifie la correction.
4. Après trois échecs sur la même porte, l'orchestrateur arrête la boucle et
   demande à l'humain de choisir entre réduction du périmètre, changement de
   solution, acceptation explicite du risque ou abandon.

Un auteur ne valide jamais sa propre correction. Une preuve manquante ne vaut
jamais validation.

## Approbations humaines obligatoires

- modification matérielle du périmètre, du budget ou de l'architecture ;
- service payant, dépendance externe engageante ou opération irréversible ;
- acceptation d'un risque élevé ou critique ;
- écriture externe sensible, action destructive ou accès aux données réelles ;
- fusion de `develop` vers `main` ;
- déploiement ou modification de la production.

## État final

L'orchestrateur termine par `completed`, `blocked` ou
`awaiting_human_approval`. Il cite les transmissions et preuves, indique les
risques résiduels, les décisions attendues et le prochain responsable. Le
`documentation_writer` persiste les décisions durables et l'état utile dans Git.
