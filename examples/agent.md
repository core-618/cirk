# Agent Execution Examples

## Simple autonomous change

Task: rename internal variable and update references

```text
C1 I1 R1 K1
```

Implication:

- agent can execute directly
- lightweight validation is enough

---

## Draft-first implementation

Task: refactor repository layer for shared patterns

```text
C2 I3 R2 K2
```

Implication:

- agent should propose plan or draft first
- review before full implementation is useful

---

## Controlled execution

Task: change identity propagation across services

```text
C3 I2 R3 K3
```

Implication:

- strong context requirements
- mandatory human review
- rollout must be controlled
- ideal candidate for staged execution

---

## High-risk financial fix

Task: fix bug in payment calculation

```text
C3 I2 R3 K3
```

Policy:

- no auto-merge
- requires senior review
- staged rollout

Outcome:

- safe execution
- predictable deployment
