# Plan Stage

## Purpose

Build the claim plan before drafting. This stage turns the user's topic, notes, rubric, and constraints into a structure the draft can follow without drifting into generic or unsupported writing.

This stage is mandatory for `open_generation` and recommended for `notes_first`.

---

## Inputs

- topic or prompt
- course / level if known
- user notes, if provided
- rubric, if provided
- requested word count and citation style
- whether the user supplied sources

## Required Work

1. Identify the central thesis or question
2. Break the topic into 3–5 section goals
3. List the claims that need evidence or sourcing
4. Mark any claim that cannot be supported from the prompt as `UNVERIFIED`
5. List stock examples or analogies to avoid
6. Propose safer alternative examples
7. If a rubric exists, align the section goals to the highest-weight criteria

## Stock Example Rule

Do not rely on predictable examples that make the draft feel templated.

Examples to avoid unless the user specifically asks for them:

- machine learning = spam filters or handwritten digits
- overfitting = student memorizing exam answers
- gradient descent = ball rolling down a hill
- binary search = dictionary lookup
- economics = pizza price or petrol spike by default

If you use an example, pick one that fits the user's context or choose a less overused angle.

## Output Contract

Return exactly these sections:

```text
Mode:
- open_generation | notes_first

Core Thesis:
- ...

Section Goals:
- Section 1: ...
- Section 2: ...

Claims Requiring Support:
- [CLAIM] ...
- [UNVERIFIED] ...

Examples To Avoid:
- ...

Safer Alternatives:
- ...

Citation Placeholders:
- [CITE: claim or source needed]

Open Questions:
- ...
```

## Refusal Rule

If the user asks for final citations without providing sources, keep placeholders only and say verification is still required.
