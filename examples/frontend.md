# Frontend Examples

## Button color adjustment

Task: update button color token

```
C1 I1 R1 K1
```

Reasoning:

- local visual change
- deterministic implementation
- minimal review burden
- low rollout risk

---

## Dashboard layout revision

Task: restructure dashboard cards and states

```
C2 I3 R2 K2
```

Reasoning:

- touches multiple components
- iteration is likely because UX refinement matters
- review is functional rather than architectural
- rollout changes existing behavior

---

## Authentication UI redesign

Task: redesign login and recovery flows

```
C3 I3 R3 K2
```

Reasoning:

- cross-flow understanding is required
- multiple design and functional iterations are likely
- review must include UX and correctness
- rollout changes a critical entry point
