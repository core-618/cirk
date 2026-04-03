# Backend Examples

## Add non-critical endpoint

Task: add read-only status endpoint

```text
C1 I1 R1 K1
```

Reasoning:

- local, isolated change
- deterministic implementation
- low review burden
- low rollout risk

---

## Login API

Task: implement login endpoint

```text
C2 I2 R3 K1
```

Reasoning:

- moderate context across auth components
- validation and edge cases likely require iteration
- security-sensitive behavior requires strong review
- rollout can remain relatively contained

---

## Billing webhook change

Task: modify billing event handling

```text
C2 I2 R3 K3
```

Reasoning:

- touches business-critical logic
- correctness may require several cycles
- review is mandatory
- bad rollout can create financial issues

---

## Fix bug in payment calculation

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
- correctness is critical
- production impact is high
