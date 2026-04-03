# ADR-0001 — CIRK as an AI-Native Execution Standard

## Status

Active

---

## Context

AI changed software development.

Coding effort is no longer the primary bottleneck for many tasks.
The harder problem is governing how work should execute safely.

Existing estimation models, especially story points, are poorly aligned with that reality because they focus on human effort rather than execution conditions.

---

## Decision

Adopt CIRK as a standard model for classifying AI-assisted work across four dimensions:

- Context
- Iteration
- Review
- Integration Risk

Use the CIRK vector as input for execution policy, autonomy boundaries, review rules, and deployment controls.

---

## Rationale

CIRK was chosen because it:

- models execution rather than effort
- supports governance decisions directly
- is simple enough for teams and systems
- is implementation-agnostic and standard-friendly

---

## Consequences

Adopting CIRK implies that teams can:

- replace or complement story points in AI-native workflows
- formalize when agents may execute autonomously
- make review requirements explicit
- treat deployment sensitivity as part of classification

It also implies a shift toward execution governance as a first-class concern.

---

## Notes

CIRK is intended to remain open and not be tied to a single implementation or vendor.
