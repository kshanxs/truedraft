# TrueDraft

*Originality-first drafting and revision for assignment-style writing.*

`TrueDraft` is a prompt-only skill for producing fresher drafts, refining existing writing, and keeping unsupported claims visible instead of bluffing through them.

It does three things well:

- builds a claim plan before drafting
- requires outline approval for topic-only generation
- rewrites formulaic phrasing without inventing citations

It does not measure similarity against an external corpus, and it does not guarantee `0 plagiarism`.

## What It Is

TrueDraft is for:

- topic-only drafting with tighter structure control
- notes-first drafting that stays anchored to the user's ideas
- draft rewrite when the user wants less overlap and less templated phrasing

TrueDraft is not:

- a plagiarism detector
- a citation generator that fabricates sources
- a guarantee that a submission will pass institutional checks

## Workflow

The core workflow is:

1. `Plan` — thesis, claims, examples to avoid, citation placeholders
2. `Outline` — structure and word budget, then approval gate
3. `Draft` — full prose from the approved plan
4. `Rewrite` — reduce formulaic phrasing and stock examples
5. `Audit` — trust note, unsupported claims, and delivery status

## Modes

| Mode | Use case | Trust |
|---|---|---|
| `open_generation` | User provides only a topic | Lowest |
| `notes_first` | User provides notes or an outline | Highest |
| `draft_rewrite` | User pastes an existing draft | Medium |

## Citation Policy

- If the user provides sources, format those sources.
- If the user does not provide sources, keep placeholders.
- Never invent citations or bibliography entries.

## Quick Start

```text
"Write a 1200-word draft on climate adaptation"
"Use these notes to write my literature review"
"Refine this draft so it sounds less formulaic"
"Show me the claim plan first"
"Add placeholders for unsupported claims"
```

See [USAGE.md](/Users/shubh/Developer/awf/assignment-writer-skill/docs/USAGE.md) for examples and [FEATURES.md](/Users/shubh/Developer/awf/assignment-writer-skill/docs/FEATURES.md) for the stage contracts.

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
    ├── references/
    ├── assets/templates/
    └── examples/
```

## Installation

```bash
cp -r truedraft /path/to/.agents/skills/truedraft
```

## Limitation

TrueDraft reduces similarity risk through process discipline, not through corpus-backed verification. The user remains responsible for source verification, citation accuracy, and compliance with their institution's rules.
