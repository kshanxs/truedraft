# Rewrite Stage

## Purpose

Reduce similarity-risk patterns without pretending to measure plagiarism. This stage removes templated phrasing, stock examples, and repetitive structure, then reports what changed.

The goal is targeted intervention. In `draft_rewrite`, preserve the user's voice outside flagged sections.

---

## Modes

- `generated_draft`: revise output from the draft stage
- `draft_rewrite`: revise text provided by the user

## Required Work

1. Read the full text before changing anything
2. Identify sections that need:
   - `rewrite now`
   - `light edit`
   - `leave`
3. Rewrite formulaic openings, repeated phrasing, filler, and stock analogies
4. Keep meaning intact
5. Keep citations and placeholders intact
6. Return a concrete change summary

## Rewrite Targets

- definition-style intros
- generic openers
- repeated sentence shapes
- filler phrases
- overused examples listed in the plan stage
- weak conclusions that only restate earlier points

## Output Contract

Return:

```text
Rewrite Actions:
- Section X: rewrite now | light edit | leave

Changes Made:
| # | Original | Revised | Reason |
|---|---|---|---|

Revised Draft:
...
```

## Final Rule

Never claim a measured similarity score. Describe unresolved issues as `originality risks` or `support gaps` only.
