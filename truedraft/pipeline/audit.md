# Audit Stage

## Purpose

Perform the final readiness check. Confirm what is solid, what was rewritten, and what still needs the user's attention before submission.

---

## Inputs

- current draft
- rewrite output
- citation policy if placeholders remain
- `references/review_checklist.md`

## Required Work

1. Confirm the introduction is analytical
2. Confirm the structure matches the approved outline or explain the deviation
3. Confirm unsupported claims are still marked
4. Confirm citations were not invented
5. Confirm stock examples from the avoid-list were removed
6. Confirm the conclusion offers a perspective
7. Add a final trust note based on mode
8. List all web-searched citations from `project-memory/audit_log.md` that need verification

## Trust Note

Use one of these labels:

- `Notes-first: highest trust`
- `Draft rewrite: medium trust`
- `Open generation: lowest trust`

## Output Contract

Return:

```text
Audit Summary:
- Strengths: ...
- Rewrites applied: ...
- Originality risks still present: ...
- Unsupported claims: ...
- Citation placeholders remaining: ...
- Web-searched Citations (Please Verify URLs):
  - [ ] Citation 1: <source details> (<URL>)
- Trust note: ...

Delivery Status:
- Ready for user review
- Not submission-ready until placeholders, support gaps, or citation verifications are completed
```
