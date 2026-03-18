# TrueDraft Features

## Core Positioning

TrueDraft is an originality-first drafting workflow. It helps generate fresher writing and revise existing drafts, but it does not claim detector-backed plagiarism scores.

## Workflow Stages

| Stage | Purpose |
|---|---|
| `plan` | Build the thesis, section goals, examples to avoid, and source placeholders |
| `outline` | Create the section structure and wait for approval in topic-only mode |
| `draft` | Write the first full draft from the approved plan |
| `coding` | Produce coding solutions or implementation-heavy CS/data-science sections |
| `rewrite` | Reduce formulaic phrasing, stock examples, and repeated structure |
| `audit` | Report support gaps, placeholder citations, trust note, and delivery status |

## Input Modes

| Mode | Description |
|---|---|
| `open_generation` | Draft from a topic alone, with plan and outline approval gates |
| `notes_first` | Expand user notes into a full draft while keeping their framing |
| `draft_rewrite` | Improve an existing draft with targeted rewrites and a change summary |

Automatic mode detection routes requests into prose-first, coding-first, or mixed mode depending on prompt signals.

## Originality Controls

| Control | Description |
|---|---|
| Analytical opening rule | Avoids dictionary-style intros and generic filler |
| Stock-example avoidance | Replaces overused analogies with fresher examples |
| Explain → example → implication | Keeps paragraphs reasoned instead of flat |
| Change summary | Shows what the rewrite stage changed and why |
| Trust note | Makes mode-specific confidence explicit instead of bluffing certainty |

## Coding and Data-Science Controls

| Control | Description |
|---|---|
| Structured coding output | Uses problem restatement, approach, implementation, complexity, testing, and improvements |
| Algorithm choice reasoning | Requires explanation of why the selected method fits constraints |
| Descriptive naming and modularity | Reduces template-like code structure and improves readability |
| Metrics and limitations discipline | Requires explicit metrics, implementation assumptions, and model/pipeline limits |
| Integrity-safe claims | Never invents benchmark numbers, dataset facts, or references |

## Citation Controls

| Rule | Description |
|---|---|
| Placeholder-only when unsourced | Missing sources remain marked |
| No invented references | Bibliographies are only built from user-supplied sources |
| Delivery warning | Output is not labeled submission-ready if placeholders remain |

## Project Memory

| File | Purpose |
|---|---|
| `project-memory/brief.md` | Topic, rubric, scope, and notes |
| `project-memory/style_profile.md` | Tone, citation style, and writing constraints |
| `project-memory/audit_log.md` | Rewrite actions and unresolved issues |

## Discipline Support

TrueDraft keeps discipline-specific guidance for:

- science
- humanities
- law
- business
- commerce
- data science / CS

## Examples

| File | Demonstrates |
|---|---|
| `examples/open_generation_example.md` | Topic-only generation with placeholders and trust note |
| `examples/notes_first_example.md` | Notes-led drafting with stronger user grounding |
| `examples/draft_rewrite_example.md` | Targeted rewrite with a sentence-level change summary |
| `examples/coding_assignment_example.md` | Coding-first assignment with complexity and testing notes |
| `examples/ml_project_report_example.md` | Mixed-mode ML project report with implementation, metrics, and unresolved-citation audit |
