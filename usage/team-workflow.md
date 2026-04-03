# Using CIRK in a Team

CIRK works best when every task receives a score before execution starts.

---

## Suggested workflow

1. A task is created
2. The task receives a CIRK score
3. The score determines execution policy
4. Agents and humans follow the same rules
5. Outcomes are used to calibrate future scoring

---

## Example policy interpretation

- **Low R** → more autonomy is acceptable
- **High R** → human review is mandatory
- **High K** → rollout needs stronger control
- **High I** → draft-first behavior is preferred

---

## What CIRK replaces

CIRK helps replace:

- vague estimation
- inconsistent review expectations
- unclear autonomy boundaries
- hidden deployment risk

---

## How teams talk using CIRK

Once a team uses CIRK consistently, people start speaking in a shared operational language:

- “This is high R.”
- “This is low K, we can ship safely.”
- “This looks like I3, let the agent draft first.”
- “This is high C, prepare context before execution.”

That shared language is what makes a standard adoptable.
