---
name: truedraft
description: "Originality-first writing workflow for essays, reports, case studies, coding assignments, and assignment-style drafting. Builds a claim plan before writing, requires outline approval for open generation, rewrites formulaic phrasing, supports CS and data-science project workflows, and never invents citations. Use this skill when a user wants a fresh draft, wants to build from notes, wants an existing draft refined, or needs coding and implementation support in academic work."
---

# TrueDraft

Prompt-first academic workflow. Produces fresher drafting through planning, structure control, originality-focused rewriting, coding-stage support for CS/data-science tasks, and explicit unresolved-claim tracking.

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
| `pipeline/coding.md` | Producing coding solutions or implementation sections |
| `pipeline/rewrite.md` | Reducing formulaic phrasing and overlap |
| `pipeline/audit.md` | Final trust note and unresolved-issue review |

Never load more than 3–4 files in a single pass unless the task clearly requires it.

---

## Features

- `open_generation`, `notes_first`, and `draft_rewrite` modes
- automatic mode detection for prose-first, code-first, and mixed CS/data-science assignments
- Five-stage workflow: Plan → Outline → Draft → Rewrite → Audit
- optional coding stage for implementation-heavy assignments
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
"Solve this Python assignment problem and explain complexity"
"Write the implementation section for my ML project"
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
6. If implementation-heavy, load `pipeline/coding.md`
7. Load `pipeline/rewrite.md`
8. Load `pipeline/audit.md`

### 2. Notes-First

When the user provides notes, bullets, or an outline:

1. Treat the user's notes as the source of truth
2. Load `pipeline/plan.md` to organize claims and support gaps
3. Load `pipeline/draft.md`
4. If notes include coding tasks or technical build details, load `pipeline/coding.md`
5. Load `pipeline/rewrite.md`
6. Load `pipeline/audit.md`

### 3. Draft Rewrite

When the user pastes a draft and wants lower overlap or less formulaic writing:

1. Read the entire draft first
2. Load `pipeline/rewrite.md`
3. Rewrite flagged sections only unless the user asks for a full rewrite
4. Load `pipeline/audit.md`

### 4. Coding and Data Science Assignments

When the request is coding-first or implementation-first:

1. Load `references/disciplines/data_science_cs.md`
2. If the task includes a written report, load `pipeline/plan.md` for structure
3. Load `pipeline/coding.md` for the solution body
4. If prose quality tuning is needed, load `pipeline/rewrite.md`
5. Load `pipeline/audit.md`

Automatic detection hints:

- coding-first: "solve this", "implement", "write code", "debug"
- data-science implementation: "model training", "pipeline", "evaluation metrics"
- mixed mode: report sections plus code requirements

### 5. Citations

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
| `pipeline/coding.md` | Coding and implementation-stage contract for CS/data-science tasks |
| `pipeline/rewrite.md` | Similarity-risk rewrite and change summary |
| `pipeline/audit.md` | Final trust note, unresolved issues, and delivery check |
| `assets/templates/brief_template.md` | Project brief template |
| `assets/templates/style_profile_template.md` | Style settings template |
| `assets/templates/audit_log_template.md` | Rewrite and audit log template |
| `assets/templates/readme_template.md` | Project README template |
| `examples/open_generation_example.md` | Topic-only workflow example |
| `examples/notes_first_example.md` | Notes-first workflow example |
| `examples/draft_rewrite_example.md` | Draft revision workflow example |
| `examples/coding_assignment_example.md` | Coding-first and mixed-mode CS/data-science workflow example |
| `examples/ml_project_report_example.md` | End-to-end ML report example with implementation, evaluation, and audit placeholders |

## Final Rule

Never claim a measured plagiarism score. Never invent citations. If the draft still contains unresolved claims or placeholders, say so clearly before delivery.
