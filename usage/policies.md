# Execution Policies

CIRK is useful because it can map classification into execution behavior.

---

## Common execution modes

### Autonomous

Typical signals:

- score 4–5
- R1
- K1 or K2

Behavior:

- agent may implement directly
- human validation can be lightweight

---

### Guided

Typical signals:

- score 6–9
- R2 or mixed vectors

Behavior:

- agent executes with normal human review
- merge remains review-gated

---

### Draft-first

Typical signals:

- I3 or R3

Behavior:

- agent produces draft, analysis, or proposal first
- implementation proceeds after review or approval

---

### Supervised

Typical signals:

- score 10+
- K3 or R3 with system sensitivity

Behavior:

- step-by-step execution
- explicit approvals
- rollout controls required

---

### Split required

Typical signals:

- score 12
- or execution is too broad to govern safely as one task

Behavior:

- break work into smaller units
- score each unit independently

---

## Policy rules by signal

| Signal | Suggested behavior |
| ------ | ------------------ |
| I3 | Draft-first required |
| R3 | No auto-approval or auto-merge |
| K3 | Deploy runbook or staged rollout required |
| C3 | Context preparation should be explicit |

---

## Key idea

CIRK is not just descriptive.
It can act as policy-as-code input for execution governance.
