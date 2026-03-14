# Outline Stage

## Purpose

Turn the claim plan into a section structure the draft must follow.

For `open_generation`, this stage is an approval gate. Do not continue to a polished full draft until the user approves the outline.

---

## Inputs

- claim plan from `pipeline/plan.md`
- word count target, if available
- rubric or special instructions, if available

## Required Work

1. Build a section-by-section outline
2. Assign a rough word count to each section
3. Show the argument progression
4. Note where source support is still missing
5. Ask for approval before drafting

## Output Contract

Return exactly these sections:

```text
Proposed Structure:
1. ...
2. ...

Section Budget:
- Introduction: ...
- Body Section 1: ...

Argument Progression:
- ...

Support Gaps:
- [CITE] ...
- [UNVERIFIED] ...

Approval Check:
- Waiting for user approval before drafting.
```

## Rule

If the user does not approve the outline in `open_generation`, you may offer a shorter exploratory sample, but not a polished final assignment.
