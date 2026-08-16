# Leçon 2 — Rendre les agents exécutables

## Les deux représentations

Chaque rôle possède désormais deux représentations complémentaires :

- `agents/*.md` explique le métier et facilite la revue humaine ;
- `.codex/agents/*.toml` configure l'agent réellement chargé par Codex.

Le fichier TOML est la source opérationnelle. Lorsqu'un comportement change, sa
documentation Markdown doit être vérifiée dans la même pull request.

## Anatomie minimale

Un agent personnalisé exige trois propriétés :

```toml
name = "qa_reviewer"
description = "Indique à l'orchestrateur quand employer cet agent."
developer_instructions = """
Définit comment l'agent travaille, ses obligations et ses interdictions.
"""
```

Les propriétés facultatives peuvent régler le modèle, l'effort de raisonnement,
le bac à sable, les serveurs MCP et les compétences.

## Permissions retenues

| Agent | Bac à sable | Justification |
|---|---|---|
| `orchestrator` | lecture seule | Il coordonne sans implémenter. |
| `implementation_engineer` | écriture du workspace | Il produit les changements. |
| `qa_reviewer` | lecture seule | Il contrôle sans corriger son propre constat. |

Les permissions effectives restent soumises aux autorisations de la session
parente. Un agent ne peut pas élargir seul les droits accordés par l'utilisateur.

## Premier test attendu

1. lancer une nouvelle session Codex à la racine du dépôt ;
2. demander la liste des agents personnalisés disponibles ;
3. confier au `qa_reviewer` une inspection en lecture seule ;
4. vérifier que son verdict respecte le format demandé ;
5. consigner les écarts avant de modifier ses instructions.
