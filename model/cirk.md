# CIRK Model

CIRK is an execution classification model for AI-assisted software development.

Each task is represented as:

```text
[C, I, R, K]
```

Each dimension is scored from **1 to 3**:

- **1 — Low**
- **2 — Medium**
- **3 — High**

---

## C — Context

How much system understanding is required for correct execution?

| Score | Description |
| ----- | ----------- |
| C1 | Isolated logic, local change, minimal context |
| C2 | Multiple components, shared patterns, moderate system understanding |
| C3 | Cross-system behavior, architectural reasoning, or domain-critical context |

---

## I — Iteration

How many cycles are likely required before the solution converges?

| Score | Description |
| ----- | ----------- |
| I1 | Deterministic or near one-pass execution |
| I2 | Some iteration expected, usually 2–3 cycles |
| I3 | Ambiguous, exploratory, or high-complexity convergence |

---

## R — Review

How much human validation is required before the work is trusted?

| Score | Description |
| ----- | ----------- |
| R1 | Quick validation or spot-check |
| R2 | Rule-level or functional review required |
| R3 | Deep architectural, product, security, or mission-critical review |

---

## K — Integration Risk

How risky is integration, release, or rollout?

| Score | Description |
| ----- | ----------- |
| K1 | Safe, additive, low-risk rollout |
| K2 | Existing behavior changes, moderate release caution needed |
| K3 | Coordinated rollout, migration, cross-team dependency, or critical risk |

---

## Composite score

```text
Score = C + I + R + K
```

| Score | Classification |
| ----- | -------------- |
| 4–5 | Trivial |
| 6–7 | Simple |
| 8–9 | Medium |
| 10–11 | Complex |
| 12 | Split Required |

---

## Important note

The vector matters more than the total.

Two tasks with the same composite score may require different execution policies.

Example:

- `C3 I1 R1 K3` and `C1 I3 R3 K1` may both sum to 8
- but one is deploy-sensitive, the other is review-sensitive

CIRK should be interpreted as a policy input, not just a math output.
