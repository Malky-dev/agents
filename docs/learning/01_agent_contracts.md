# Leçon 1 — Les contrats avant l'automatisation

## Ce que nous construisons

Un agent n'est pas seulement un nom ou une consigne de personnalité. Dans cette
première phase, c'est un rôle défini par six éléments :

1. une responsabilité unique ;
2. des entrées attendues ;
3. une autorité explicite ;
4. des interdictions ;
5. une sortie vérifiable ;
6. une condition d'arrêt.

## Pourquoi commencer par des fichiers

Les fichiers versionnés rendent le comportement attendu visible, révisable et
reproductible. Ils constituent la mémoire normative de la flotte. L'exécution
temporaire d'un agent peut disparaître ; le contrat reste dans Git.

## Comment les agents interagissent

L'orchestrateur transmet un objectif borné à l'ingénieur. L'ingénieur produit un
artefact accompagné de preuves. Le responsable qualité examine ensuite le
livrable indépendamment et remet son verdict à l'orchestrateur.

```text
humain -> orchestrator -> implementation_engineer -> qa_reviewer
             ^                                      |
             +--------------------------------------+
```

L'agent suivant ne dépend donc pas d'une conversation implicite : il reçoit un
contrat et des artefacts qu'il peut vérifier.

## Ce qui n'est pas encore automatisé

Ces fiches ne lancent pas seules des processus. Elles préparent l'étape suivante,
où un orchestrateur exécutera réellement les rôles et conservera leurs états.
