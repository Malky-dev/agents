# Transmission de tâche

Copier ce modèle dans `docs/handoffs/` uniquement lorsqu'une transmission mérite
d'être conservée dans l'historique du projet.

```yaml
task_id: TASK-000
parent_task_id: null
phase: discovery
gate: G0_intake
from: orchestrator
to: implementation_engineer
status: requested
objective: Résultat observable à obtenir
scope:
  include: []
  exclude: []
inputs: []
expected_artifacts: []
acceptance_criteria: []
constraints: []
dependencies: []
evidence: []
risks: []
decisions: []
assumptions: []
approval_required: false
correction_attempt: 0
next_recipient: qa_reviewer
stop_condition: Condition mesurable de fin ou de blocage
```

## Cycle de statut

```text
requested -> in_progress -> review -> accepted
    |              |           |
    v              v           v
cancelled       blocked   changes_requested -> in_progress
```

Une transmission ne contient jamais de secret, de journal brut volumineux ou de
raisonnement interne. Elle conserve les décisions et preuves utiles.
