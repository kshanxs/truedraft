# TrueDraft

*Originality-first drafting and revision with interactive onboarding, humanise readability tuning, and search-first citations.*

`TrueDraft` is a prompt-only skill for producing fresh drafts, refining existing writing, explaining structural choices inline, and resolving factual claims using web search without fabricating sources.

It combines four core capabilities:
- **Interactive Onboarding (The Forge):** A 9-question setup mapping institutional requirements, word count, and marking rubrics.
- **5-Stage Writing Pipeline:** Plan → Outline Checkpoint Gate → Draft → Rewrite (Originality + Readability) → Audit.
- **Search-First Citations:** Uses host search tools to locate real papers/books to support claims; strictly defaults to placeholders on search failure (never invents sources).
- **Style & Readability Polish:** Integrates style randomization (perplexity/burstiness) and Humanise readability levels (Light/Standard/Conversational) to remove robotic, formulaic patterns.

It does not measure similarity against an external corpus, and it does not guarantee `0 plagiarism`.

---

## What It Is

TrueDraft is for:
- Interactive, rubric-calibrated drafting.
- Notes-first drafting that stays anchored to the user's ideas.
- Draft rewrite when the user wants less overlap and less templated phrasing.
- Standalone humanisation to improve reading flow and rhythm.
- Coding-first and mixed-mode assignment workflows (report + implementation).
- Learning-focused writing that explains stylistic and structural choices inline.

TrueDraft is not:
- A plagiarism detector.
- A citation generator that fabricates or hallucinates sources.
- A guarantee that a submission will pass institutional checks.

---

## Workflow

The core workflow is:
1. **Assignment Forge** — 9-question interactive onboarding (skippable).
2. **Plan** — Thesis formulation, claims mapping, and stock examples to avoid.
3. **Outline Gate** — Structure and word budget, pausing for user approval before drafting.
4. **Draft** — Full prose from the approved plan.
5. **Coding** (conditional) — Modular, descriptive, algorithm-diverse implementations.
6. **Rewrite** — Originality edit, style randomization, and Humanise readability pass.
7. **Audit** — Checklist check, web-searched source summary, placeholders review, and trust note.

---

## Modes

| Mode | Use case | Trust |
|---|---|---|
| `notes_first` | User provides notes or an outline | Highest |
| `draft_rewrite` | User pastes an existing draft | Medium |
| `open_generation` | User provides only a topic | Lowest |

---

## Citation Policy

- **Search First:** If citations are needed, the agent attempts to search the web using host tools to find real papers/sources.
- **Placeholder Fallback:** If search tools are unavailable or fail to find reliable academic matches, the agent inserts placeholders like `[CITE: source needed for claim about: "..."]`.
- **Zero Fabrication:** Never invent authors, journal names, or references.
- **Validation:** All searched citations are logged in the project's audit log for user verification.

---

## Quick Start

```text
"Start a new assignment on machine learning"
"Write a 1200-word draft on climate adaptation"
"Use these notes to write my literature review"
"Refine this draft so it sounds less formulaic"
"Humanise this text and make it more conversational"
"Solve this Python homework and analyze complexity"
"Explain as you go / Start learning mode"
```

See [USAGE.md](file:///Users/shubh/Developer/awf/assignment-writer-skill/docs/USAGE.md) for examples and [FEATURES.md](file:///Users/shubh/Developer/awf/assignment-writer-skill/docs/FEATURES.md) for full capability details.

---

## Structure

```text
assignment-writer-skill/
├── README.md
├── docs/
│   ├── USAGE.md
│   ├── FEATURES.md
│   └── superpowers/specs/
└── truedraft/
    ├── SKILL.md
    ├── pipeline/
    │   ├── forge.md
    │   ├── plan.md
    │   ├── outline.md
    │   ├── draft.md
    │   ├── coding.md
    │   ├── rewrite.md
    │   └── audit.md
    ├── references/
    │   ├── academic_rules.md
    │   ├── citation_policy.md
    │   ├── citation_guide.md
    │   ├── learning_mode.md
    │   ├── style_randomization.md
    │   ├── humanise.md
    │   └── ...
    ├── assets/templates/
    └── examples/
```

---

## Installation

```bash
cp -r truedraft /path/to/.agents/skills/truedraft
```

---

## Limitations & Responsibility

TrueDraft reduces similarity risk through process discipline and style tuning, not through corpus-backed verification. The user remains responsible for checking web-searched sources in `audit_log.md`, resolving remaining placeholders, and complying with their institution's academic integrity policies.
