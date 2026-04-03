# Quick Examples

These examples are designed to make CIRK immediately usable.

---

## Example 1 — UI copy tweak

Task: change button label

```text
C1 I1 R1 K1
```

Implication:

- fully autonomous execution is reasonable
- minimal review required
- low deployment concern

---

## Example 2 — Login API

Task: build login endpoint

```text
C2 I2 R3 K1
```

Implication:

- agent can draft and implement
- human review is mandatory
- auto-merge should be disabled

---

## Example 3 — Payment flow refactor

Task: refactor payment orchestration

```text
C3 I3 R3 K3
```

Implication:

- draft-first workflow
- step-by-step approval
- controlled rollout required
- likely split candidate

---

## Example 4 — Add field to internal model

Task: add optional field to admin-only model

```text
C1 I1 R1 K2
```

Implication:

- autonomous implementation may be acceptable
- simple review path
- moderate rollout awareness because behavior changes

---

## Example 5 — Auth change across systems

Task: update SSO rules across gateway and app

```text
C3 I2 R3 K3
```

Implication:

- strong context dependency
- human review required
- release coordination required

---

## Example 6 — Fix bug in payment calculation

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

Reasoning:

- complex domain logic
- moderate iteration expected
- correctness is business-critical
- production impact is high

---

## Example 7 — Bug fix (trivial)

Task: fix null check in cart total

```text
C1 I1 R1 K1
```

Policy:

- autonomous execution
- auto-approval allowed

Reasoning:

- single function, local fix
- deterministic fix
- low review burden
- safe, localized change

---

## Example 8 — Critical deploy

Task: migrate payment gateway provider

```text
C3 I2 R3 K3
```

Policy:

- supervised execution
- staged rollout required
- deploy runbook mandatory

Reasoning:

- cross-system payment flow understanding
- multiple verification cycles expected
- mandatory human review
- rollout must be staged and monitored

---

## Copy-paste template

```text
Task:
C:
I:
R:
K:

Policy:
```
