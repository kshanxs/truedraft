# Coding Stage

## Purpose

Handle coding assignments and technical implementation sections for CS and data science projects.

This stage produces original, explainable solutions with explicit tradeoffs, testing intent, and complexity analysis.

It does not claim measured plagiarism or similarity scores.

---

## Activation

Run this stage when the request is primarily code-first or implementation-first, for example:

- algorithm or DSA homework
- programming tasks in Python, Java, C++, JavaScript, or similar
- ML or data-science assignments that require implementation details
- requests such as "solve this coding problem", "write the code", "implement", or "debug this assignment code"

If the task is a full report with a methodology plus code, use this stage for the implementation section and keep `plan`, `draft`, `rewrite`, and `audit` for the prose sections.

---

## Core Rules

1. Do not default to the most common textbook template when alternatives exist.
2. Explain why the selected approach fits the assignment constraints.
3. Use descriptive naming and helper functions to keep logic modular.
4. Keep comments focused on reasoning, constraints, and design choices.
5. Include complexity analysis for algorithms and runtime/memory notes for data pipelines.
6. Preserve placeholders and source markers if claims about libraries, datasets, or benchmarks need citations.
7. Never fabricate benchmark numbers, dataset facts, or references.

---

## Output Contract

For coding assignments, return:

```text
### Problem Restatement
...

### Approach
...

### Implementation
...

### Complexity Analysis
- Time Complexity: ...
- Space Complexity: ...

### Testing Notes
...

### Possible Improvements
...
```

For data science / ML project implementation sections, return:

```text
### Implementation Design
...

### Data and Preprocessing Notes
...

### Model / Pipeline Choices
...

### Evaluation Metrics
...

### Limitations and Risks
...
```

---

## Rewrite Compatibility

When this stage is followed by `rewrite`:

- keep code behavior intact
- only adjust surrounding explanation text for clarity and originality
- do not rename API surface or variable names if the user already integrated the code

---

## Final Rule

Never claim detector-backed originality for code. Describe remaining issues as `originality risks`, `testing gaps`, or `support gaps`.