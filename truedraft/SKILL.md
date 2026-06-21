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
| `pipeline/forge.md` | Initializing a new topic, course, or running onboarding |
| `references/academic_rules.md` | Writing or revising the draft |
| `references/citation_policy.md` | The user asks for citations or any claim needs sourcing |
| `references/citation_guide.md` | Formatting bibliographies or citation structures |
| `references/learning_mode.md` | Running in learning mode ("explain as you go") |
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
| `pipeline/rewrite.md` | Reducing formulaic phrasing, applying readability (Humanise), or style randomization |
| `pipeline/audit.md` | Final trust note, citation search verification, and unresolved-issue review |

Never load more than 3–4 files in a single pass unless the task clearly requires it.

---

## Features

- **Assignment Forge** — 9-question onboarding: topic, level, word count, citations, institution, rubric, instructions, draft/notes, learning mode. All skippable.
- **Three Core Modes** — `open_generation` (gated by outline approval), `notes_first` (treats notes as source of truth), and `draft_rewrite` (improves prose originality).
- **Five-Stage Workflow** — Plan → Outline → Draft → Rewrite (Originality + Humanise) → Audit.
- **Search-First Citation Engine** — Searches web/scholarly sources using host tools to resolve factual claims; strictly defaults to placeholders if search fails or is unavailable.
- **Originality & Readability Rewrite** — Integrates style randomization (perplexity/burstiness) and Humanise readability modes (Light/Standard/Conversational levels) to remove formulaic patterns.
- **Learning Mode** — Inline `💡 Learning note:` annotations explaining style and structural choices as they are written.
- **CS/Data Science Stage** — Calibrated support for mixed-mode coding tasks, including modular structure, algorithm diversity, complexity analysis, and descriptive naming.
- **Project memory** stored in `project-memory/` (style profile, brief, and audit log).

---

## Quick Start

```text
"Start a new assignment on machine learning"
"Write a 1200-word draft on climate adaptation"
"Use these notes to write my literature review"
"Refine this draft so it sounds less formulaic"
"Humanise this pasted text and make it more conversational"
"Solve this Python assignment problem and explain complexity"
"Explain as you go during this drafting process"
```

---

## Command Reference

| Say this… | What happens |
|---|---|
| `"Start a new assignment"` | Assignment Forge runs (onboarding) |
| `"Write my assignment on [topic]"` | Onboarding → Plan → Outline Gate → Draft → Rewrite → Audit |
| `"Reduce similarity in this draft: [paste]"` | Rewrite (Originality pass) + Audit on existing text |
| `"Humanise this"` / `"Make this easier to read"` | Rewrite (Humanise pass) with Before/After change log |
| `"Make this more conversational"` | Rewrite (Humanise Level 3) |
| `"Explain as you go"` / `"Learning mode"` | Activates inline Learning Mode for all subsequent draft actions |
| `"Solve this programming task"` | Activates Coding stage |

---

## Project Structure

When the host agent supports file creation, a writing project uses:

```text
YourDraft/
├── README.md              ← Main project summary
├── working.md             ← Intermediate draft
├── final.md               ← Final audited and polished output
└── project-memory/
    ├── brief.md            ← Collected onboarding requirements
    ├── style_profile.md   ← Citations, level, and tone profile
    └── audit_log.md       ← Log of rewritten sentences and web search citations
```

---

## Workflows

### 1. Initialization — Assignment Forge

When the user starts a new assignment, topic, or asks to begin:
1. Run the **Assignment Forge** (`pipeline/forge.md`). Collect topics, constraints, and rubrics interactively.
2. Initialize `project-memory/brief.md` and `project-memory/style_profile.md`.
3. Create `README.md` from templates.
4. Prompt the user to proceed to the Plan & Outline stage.

### 2. Open Generation

When the user provides only a topic or broad brief:
1. **Adversarial Check:** If the user requires deep adversarial criticism, debate mapping, or thesis stress-testing before writing, recommend they run the `research-dojo` skill (if installed) or add it: `npx skills add https://github.com/kshanxs/research-dojo --skill research-dojo`.
2. Load `pipeline/plan.md` to define thesis, claim map, and examples to avoid.
3. Load `pipeline/outline.md` to establish structure and section word counts.
4. **Outline Checkpoint Gate:** Stop and wait for user approval of the outline before long-form drafting.
5. Load `pipeline/draft.md` to draft initial sections.
6. If implementation-heavy, load `pipeline/coding.md`.
7. Load `pipeline/rewrite.md` for originality and readability pass.
8. Load `pipeline/audit.md` to verify citation status and issue the final trust note.

### 3. Notes-First

When the user provides notes, bullets, or an outline:
1. **Synergistic Import:** If the notes look like they are a research summary or brief exported from the `research-dojo` skill (e.g., mapping thesis, contradiction table, evidence audit), treat this as the high-trust source of truth, pre-populate the brief/outline accordingly, and skip redundant topic onboarding questions.
2. Treat the user's notes as the source of truth.
3. Load `pipeline/plan.md` to map claims and missing details.
4. Load `pipeline/draft.md` to build directly on user notes (never throw away notes content).
5. If notes include technical coding instructions, load `pipeline/coding.md`.
6. Load `pipeline/rewrite.md` to smooth and randomize style.
7. Load `pipeline/audit.md` to check unresolved claims.

### 4. Draft Rewrite

When the user pastes a draft and wants lower overlap or less formulaic writing:
1. Read the entire draft first.
2. Load `pipeline/rewrite.md` to apply targeted style randomization and Humanise readability modes.
3. Rewrite only flagged sections by default unless a full rewrite is requested.
4. Load `pipeline/audit.md` to output the change summary tables.

### 5. Coding and Data Science Assignments

When the request is coding-first or implementation-first:
1. Load `references/disciplines/data_science_cs.md`.
2. Load `pipeline/coding.md` to generate modular code, algorithm explanations, complexity analysis, and descriptive names.
3. Load `pipeline/audit.md` to check execution logic.

### 6. Learning Mode

When the user says "explain as you go", "learning mode", "teach me", or "show me why":
1. Load `references/learning_mode.md` and keep it active for the entire session.
2. Perform drafting and rewriting normally.
3. After each output block or stage, insert a `💡 Learning note:` explaining the choice of sentence length, vocabulary reduction, or rhetorical technique.

### 7. Citations & Search-First Policy

If the user wants citations or the draft contains factual claims:
1. Load `references/citation_policy.md` and `references/citation_guide.md`.
2. **Search Step:** Search the web/Google Scholar using host tools for verified sources supporting the claims.
3. **Formatting Step:** Format retrieved sources in the requested style (APA 7, MLA 9, Harvard, IEEE).
4. **Fallback:** If search returns no verified results or is unavailable, use explicit placeholders like `[CITE: source needed for claim about ...]`.
5. **No Invention:** Never invent, hallucinate, or guess citations or references.

---

## References

| File | Purpose |
|---|---|
| `references/academic_rules.md` | Core drafting rules — analytical openings, reasoning, structure |
| `references/citation_policy.md` | Search-first citation engine guidelines and placeholder rules |
| `references/citation_guide.md` | Specific formats for APA 7, MLA 9, Harvard, IEEE |
| `references/learning_mode.md` | Rules for writing inline explanations |
| `references/review_checklist.md` | Final audit checklist and trust-note rules |
| `references/grammar.md` | Grammar and punctuation checks |
| `references/rubric_guide.md` | Rubric parsing and section priority |
| `references/disciplines/*` | Discipline-specific structure and tone guidance |
| `pipeline/forge.md` | Interactive onboarding questions |
| `pipeline/plan.md` | Thesis, claim map, source gaps, and examples to avoid |
| `pipeline/outline.md` | Section structure and user approval checkpoint |
| `pipeline/draft.md` | Originality-first draft generation |
| `pipeline/coding.md` | Coding and implementation-stage contract for CS/data-science tasks |
| `pipeline/rewrite.md` | Similarity-risk rewrite, Humanise readability pass, and change summary |
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

Never claim a measured plagiarism score. Never invent citations. If the draft still contains unresolved claims or placeholders, say so clearly before delivery. Use web search to resolve claims, but fall back to placeholders rather than fabricating references.
