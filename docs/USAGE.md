# TrueDraft Usage

This skill has three main writing modes plus automatic coding detection. The safest output still comes from stronger user input.

## 1. Topic-Only Drafting

**You say:**
> "Write a 1200-word draft on climate adaptation"

**What happens:**

1. TrueDraft builds a claim plan
2. It proposes an outline
3. It waits for approval
4. Only then does it draft, rewrite, and audit

If the user skips approval, TrueDraft should offer a shorter exploratory draft rather than a polished final submission.

## 2. Notes-First Drafting

**You say:**
> "Use these notes to draft my literature review: [paste notes]"

**What happens:**

The notes become the anchor. TrueDraft expands them, fills structural gaps, and marks unsupported claims rather than pretending they are sourced.

## 3. Draft Rewrite

**You say:**
> "Refine this draft so it sounds less formulaic: [paste draft]"

**What happens:**

TrueDraft reads the full draft, flags the sections that need intervention, rewrites those sections, and returns a change summary with any unresolved support gaps.

## 4. Coding and Data-Science Assignments

**You say:**
> "Solve this Java assignment and explain time complexity"

or

> "Write the implementation and evaluation section for my ML project"

**What happens:**

1. TrueDraft auto-detects coding-first or mixed-mode intent
2. It activates CS/data-science discipline guidance
3. It generates a structured solution with approach, implementation details, and complexity/metrics notes
4. It keeps placeholders when dataset, benchmark, or citation support is missing

For mixed report + code submissions, TrueDraft keeps prose stages and inserts a coding stage for implementation-heavy parts.

## Citation Requests

**You say:**
> "Add APA citations"

**What happens:**

- if you provided sources, TrueDraft formats them
- if you did not provide sources, TrueDraft inserts placeholders
- it does not invent a reference list

## Common Commands

| What you say | What you get |
|---|---|
| `"Write a draft on [topic]"` | `open_generation` with plan and outline gate |
| `"Use these notes to write [topic]"` | `notes_first` |
| `"Refine this draft"` | `draft_rewrite` |
| `"Solve this coding assignment: [problem]"` | coding-first workflow with structured solution sections |
| `"Write implementation for this ML project"` | mixed-mode workflow with coding stage + report-safe prose |
| `"Show me the claim plan first"` | Plan stage only |
| `"Build the outline and wait"` | Outline stage only |
| `"Audit this draft before delivery"` | Final audit only |
| `"Add placeholders for unsupported claims"` | Citation-policy pass without invented sources |

## Tips

- Paste your rubric if you have one.
- Give notes or a rough outline whenever possible; that produces stronger drafts.
- For coding tasks, provide constraints, language/version, and sample input/output when possible.
- For data-science projects, include dataset source, split strategy, and evaluation metric requirements.
- Treat topic-only generation as the lowest-trust mode.
- Resolve every placeholder before submission.
