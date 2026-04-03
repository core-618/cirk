# Scoring Guidance

CIRK should be scored pragmatically and consistently.

The goal is not theoretical precision.
The goal is consistent execution governance.

---

## Scoring flow

For each task, ask:

1. **Context** — how much of the system must be understood?
2. **Iteration** — how likely is it that multiple cycles are needed?
3. **Review** — how much human validation is required?
4. **Integration Risk** — how risky is rollout or integration?

Then assign a value from 1 to 3 for each dimension.

---

## Practical advice

### Prefer relative consistency over perfect precision

If one team scores slightly differently from another, that is acceptable.
What matters is that the scoring is stable enough to drive predictable policy.

### Score the execution reality, not the political preference

Do not lower a score just because the team wants faster approval.
Do not raise a score just to block work.

CIRK should describe the task honestly.

### Use the highest meaningful signal

If review is truly critical, score **R3** even if the rest of the task feels simple.
If rollout is sensitive, score **K3** even if implementation is small.

---

## Example

Task: update copy on marketing page

```
C1 I1 R1 K1
```

Task: modify billing webhook behavior

```
C2 I2 R3 K3
```

These tasks may both be quick to draft with AI, but their execution conditions are radically different.
