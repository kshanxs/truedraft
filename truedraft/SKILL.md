---
name: truedraft
description: "Originality-first writing workflow for essays, reports, case studies, and assignment-style drafting. Builds a claim plan before writing, requires outline approval for open generation, rewrites formulaic phrasing, and never invents citations. Use this skill when a user wants a fresh draft, wants to build from notes, or wants an existing draft refined to reduce overlap and stock phrasing."
---

# TrueDraft

Prompt-only writing workflow. Produces fresher academic drafting through planning, structure control, originality-focused rewriting, and explicit unresolved-claim tracking.

This skill is not a plagiarism detector and must not present measured similarity scores.

---

## Context Efficiency Rule

Use lazy loading. Read only the files needed for the active stage.

| Only load this file… | When… |
|---|---|
| `references/academic_rules.md` | Writing or revising the draft |
| `references/citation_policy.md` | The user asks for citations or any claim needs sourcing |
| `references/review_checklist.md` | Running the audit stage |
| `references/grammar.md` | Tightening final prose during audit |
| `references/rubric_guide.md` | The user provides a rubric or marking criteria |
| `references/disciplines/science.md` | Course is science, engineering, medicine, or general CS |
| `references/disciplines/humanities.md` | Course is literature, history, philosophy, or arts |
| `references/disciplines/law.md` | Course is law or legal studies |
| `references/disciplines/business.md` | Course is business, management, or economics (MBA/corporate level) |
| `references/disciplines/data_science_cs.md` | Course is Data Science, Computer Science, ML, AI, Software Engineering, or Statistics |
| `references/disciplines/commerce.md` | Course is Commerce, Business Studies, introductory Economics, or Accounting |
| `pipeline/plan.md` | Mapping thesis, claims, and examples to avoid |
| `pipeline/outline.md` | Creating the draft structure and waiting for approval |
| `pipeline/draft.md` | Writing the first full draft |
| `pipeline/rewrite.md` | Reducing formulaic phrasing and overlap |
| `pipeline/audit.md` | Final trust note and unresolved-issue review |

Never load more than 3–4 files in a single pass unless the task clearly requires it.

---

## Features

- `open_generation`, `notes_first`, and `draft_rewrite` modes
- Five-stage workflow: Plan → Outline → Draft → Rewrite → Audit
- Outline approval gate for topic-only generation
- Originality rewrite focused on stock examples, filler, and repeated structure
- No invented citations or bibliography entries
- Final trust note based on the active mode
- Project memory stored in `project-memory/`
- Rubric-aware planning when the user provides marking criteria

---

## Quick Start

```text
"Write a 1200-word draft on climate adaptation"
"Use these notes to write my literature review"
"Refine this draft so it sounds less formulaic"
"Build the outline first, then wait for my approval"
"Add placeholders for missing citations"
```

---

## Project Structure

When the host agent supports file creation, a writing project should use:

```text
YourDraft/
├── README.md
├── working.md
├── final.md
└── project-memory/
    ├── brief.md
    ├── style_profile.md
    └── audit_log.md
```

---

## Workflows

### 1. Open Generation

When the user provides only a topic or a broad brief:

1. Load `pipeline/plan.md`
2. Build the thesis, claim map, and examples to avoid
3. Load `pipeline/outline.md`
4. Wait for approval before long-form drafting
5. Load `pipeline/draft.md`
6. Load `pipeline/rewrite.md`
7. Load `pipeline/audit.md`

### 2. Notes-First

When the user provides notes, bullets, or an outline:

1. Treat the user's notes as the source of truth
2. Load `pipeline/plan.md` to organize claims and support gaps
3. Load `pipeline/draft.md`
4. Load `pipeline/rewrite.md`
5. Load `pipeline/audit.md`

### 3. Draft Rewrite

When the user pastes a draft and wants lower overlap or less formulaic writing:

1. Read the entire draft first
2. Load `pipeline/rewrite.md`
3. Rewrite flagged sections only unless the user asks for a full rewrite
4. Load `pipeline/audit.md`

### 4. Citations

If the user wants citations:

1. Load `references/citation_policy.md`
2. If sources exist, format them
3. If sources do not exist, keep placeholders
4. Never invent citations

---

## References

| File | Purpose |
|---|---|
| `references/academic_rules.md` | Core drafting rules — analytical openings, reasoning, structure |
| `references/citation_policy.md` | Placeholder-only citation policy and source handling |
| `references/review_checklist.md` | Final audit checklist and trust-note rules |
| `references/grammar.md` | Grammar and punctuation checks |
| `references/rubric_guide.md` | Rubric parsing and section priority |
| `references/disciplines/*` | Discipline-specific structure and tone guidance |
| `pipeline/plan.md` | Thesis, claim map, source gaps, and examples to avoid |
| `pipeline/outline.md` | Section structure and user approval checkpoint |
| `pipeline/draft.md` | Originality-first draft generation |
| `pipeline/rewrite.md` | Similarity-risk rewrite and change summary |
| `pipeline/audit.md` | Final trust note, unresolved issues, and delivery check |
| `assets/templates/brief_template.md` | Project brief template |
| `assets/templates/style_profile_template.md` | Style settings template |
| `assets/templates/audit_log_template.md` | Rewrite and audit log template |
| `assets/templates/readme_template.md` | Project README template |
| `examples/open_generation_example.md` | Topic-only workflow example |
| `examples/notes_first_example.md` | Notes-first workflow example |
| `examples/draft_rewrite_example.md` | Draft revision workflow example |

## Final Rule

Never claim a measured plagiarism score. Never invent citations. If the draft still contains unresolved claims or placeholders, say so clearly before delivery.
