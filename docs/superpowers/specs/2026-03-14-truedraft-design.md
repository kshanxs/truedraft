# TrueDraft Design

Date: 2026-03-14
Status: Approved design, pending implementation

## Summary

`TrueDraft` is a prompt-only writing skill focused on originality-first drafting and revision. It is not a plagiarism detector and must not present itself as one. Its purpose is to help users produce fresher assignment-style writing, reduce overlap in existing drafts, and avoid common formulaic patterns that increase similarity risk.

The redesign keeps three operating modes:

- `open_generation`: draft from a topic alone
- `notes_first`: draft from user notes or outline
- `draft_rewrite`: refine an existing draft

These modes do not have equal trust:

- `notes_first` has the highest trust
- `draft_rewrite` has medium trust
- `open_generation` has the lowest trust

The system remains prompt-only. It improves originality through process discipline, not through corpus-backed similarity measurement.

## Goals

- Rebrand the project from `assignment-writer` to `TrueDraft`
- Remove unsupported detector-style claims and fake certainty
- Support fresh drafting and draft refinement with lower similarity risk
- Prevent invented citations when the user has not supplied sources
- Replace loose prose instructions with stricter stage contracts
- Make open generation safer through mandatory planning and approval gates

## Non-Goals

- Guarantee `0 plagiarism` or any specific similarity score
- Claim compatibility or superiority against external detectors
- Generate verified citations without user-provided sources
- Build external verification or retrieval in this iteration

## Product Positioning

Public positioning should emphasize:

- originality-first writing
- fresh drafts designed to avoid common similarity patterns
- refinement of existing drafts to reduce overlap and formulaic phrasing

Public positioning should avoid:

- `plagiarism detector`
- `LOW / MEDIUM / HIGH plagiarism score`
- `beats MOSS`, `beats JPlag`, or similar claims
- `close to 0 plagiarism` guarantees

Recommended product tone:

- premium
- subtle
- professional

Approved name: `TrueDraft`

## User Modes

### Open Generation

Use when the user provides a topic but no draft or notes.

Constraints:

- lowest-trust mode
- must not draft immediately to final form
- must require planning and outline approval before long-form drafting

### Notes-First

Use when the user provides notes, bullet points, or an outline.

Constraints:

- treat user notes as the source of truth
- expand from the notes rather than replacing them
- mark unsupported claims with citation placeholders if no source is provided

### Draft Rewrite

Use when the user pastes a draft and asks to improve originality or reduce overlap.

Constraints:

- read the full draft before editing
- rewrite only flagged sections by default
- return a change summary and unresolved risks

## Architecture

The current pipeline should be replaced with five explicit stages:

1. `plan`
2. `outline`
3. `draft`
4. `rewrite`
5. `audit`

Discipline references remain as support files, but they no longer imply detector-like functionality.

Suggested repository shape after implementation:

```text
truedraft/
  SKILL.md
  pipeline/
    plan.md
    outline.md
    draft.md
    rewrite.md
    audit.md
  references/
    academic_rules.md
    citation_policy.md
    review_checklist.md
    disciplines/
  examples/
    open_generation_example.md
    notes_first_example.md
    draft_rewrite_example.md
```

## Stage Contracts

### Stage 1: Plan

Purpose:
- establish the thesis, argument path, risky stock examples to avoid, and claims needing citations

Required output:
- core thesis
- section goals
- banned examples or stock analogies
- factual claims needing citation
- citation placeholders only

Refusal conditions:
- if the user requests ready-to-submit citations without sources, do not proceed with real references

### Stage 2: Outline

Purpose:
- produce the structure that the draft must follow

Required output:
- approved section structure
- target word count per section
- argument progression
- user approval checkpoint

Refusal conditions:
- if the outline is not approved, do not continue to full draft generation in `open_generation`

### Stage 3: Draft

Purpose:
- generate prose strictly from the approved plan and outline

Required output:
- sectioned draft
- content aligned to the approved plan
- no bibliography unless sources were supplied

Refusal conditions:
- if the user demands final citations but only placeholders exist, stop and note the gap

### Stage 4: Rewrite

Purpose:
- remove similarity-prone phrasing and generic patterns

Required output:
- rewritten sections
- exact change summary
- list of removed patterns, such as generic intros, repeated phrasing, stock analogies, and filler

Default behavior:
- in `draft_rewrite`, rewrite only flagged sections unless the user requests a full rewrite

### Stage 5: Audit

Purpose:
- perform the final trust and readiness check

Required output:
- originality risks still present
- unsupported claims
- placeholder citations remaining
- final trust note by mode

Refusal conditions:
- do not claim submission readiness if placeholders or unresolved factual gaps remain

## Open Generation Flow

This mode must include all three gates requested by the user:

1. `claim_plan`
2. `outline_approval`
3. `self_audit`

Recommended flow:

1. build a claim plan
2. identify banned examples and stock framings
3. generate an outline
4. wait for user approval
5. draft from the approved plan only
6. run originality-focused rewrite
7. run final audit

## Citation Policy

This is mandatory:

- never invent citations
- never fabricate references
- if sources are missing, use explicit placeholders
- if the user asks for citations without sources, return placeholder citations and a verification warning

Approved rule:

`No invented citations. Unverified claims stay marked.`

## Originality Rules

The originality strategy should be framed as process discipline, not measurement.

Required rewrite targets:

- generic introductions
- repeated sentence structures
- stock analogies
- canonical examples already blacklisted in the planning stage
- filler and robotic phrasing

The system may describe these as `similarity-risk patterns` or `originality risks`, but not as measured plagiarism scores.

## Messaging Changes

The implementation should revise all public-facing copy:

- replace `plagiarism-resistant` with `originality-first`
- replace `plagiarism guard` with `originality rewrite` or `similarity-risk review`
- remove `LOW / MEDIUM / HIGH plagiarism risk` labels from examples and docs
- remove claims about beating external detectors
- clarify that the workflow reduces risk but does not verify against external corpora

## Example Strategy

All examples should be rewritten to match the new system.

Required examples:

- one `open_generation` example
- one `notes_first` example
- one `draft_rewrite` example

Each example should show:

- its input mode
- whether sources were provided
- placeholders where claims remain unverified
- a short trust note
- what still needs user verification before submission, if anything

Examples must not use banned stock examples that the planning rules say to avoid.

## Error Handling and Failure Rules

The prompt pack must prefer explicit failure over bluffing.

Mandatory failure rules:

- if no sources exist, do not invent them
- if a required claim cannot be supported, mark it unresolved
- if the user wants a submission-ready bibliography without sources, stop at placeholders
- if a banned example appears in the draft, replace it before final delivery
- if a user skips outline approval in `open_generation`, the skill may produce a shorter exploratory draft, not a polished final assignment

## Testing and Validation

This repository is documentation-driven, so validation must also be documentation-driven.

Implementation acceptance checks:

- every pipeline file defines required inputs, required outputs, and refusal conditions
- every public README claim maps to a real rule in the skill files
- no doc claims detector-like scoring without a measurable system
- no example contains fabricated citations
- no example declares a plagiarism score
- no example uses banned stock analogies without flagging them

Manual review checklist:

- verify naming is consistently `TrueDraft`
- verify the old `assignment-writer` terminology is removed or clearly deprecated
- verify citation instructions always prefer placeholders over invention
- verify `open_generation` includes plan, outline approval, and audit gates

## Migration Plan

### Pass 1: Repositioning and Contracts

- rename `assignment-writer/` to `truedraft/`
- update `README.md`
- update `docs/FEATURES.md`
- update `docs/USAGE.md`
- replace the current pipeline docs with `plan`, `outline`, `draft`, `rewrite`, and `audit`
- remove unsupported score language and detector claims
- enforce placeholder-only citation rules

### Pass 2: Examples and Validation

- replace the current examples with mode-specific examples
- add audit checklists for unsupported claims and unresolved placeholders
- add a repository review checklist to prevent regression in messaging

## Risks

- users may still interpret originality-focused wording as a plagiarism guarantee
- open generation will remain the weakest mode without external verification
- prompt-only enforcement depends on host model compliance

These risks should be acknowledged directly in the README.

## Success Criteria

The redesign is successful when:

- the project clearly presents itself as originality-first, not detector-backed
- citation invention is prohibited everywhere
- open generation is gated by plan, outline approval, and final audit
- the docs, examples, and skill instructions are internally consistent
- the repo can support drafting, notes-first writing, and draft rewrite without unsupported claims
