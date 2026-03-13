# assignment-writer — Usage Guide

A practical guide with real example dialogues for every stage of using this skill.

---

## Starting a New Assignment

**You say:**
> "Write my assignment on neural networks for my Machine Learning course"

**What happens:**
The skill runs the Assignment Forge — a short onboarding conversation to understand your course level, word count, citation style, and deadline. Every question is skippable.

> "What subject or course is this for? And is it high school, undergraduate, or postgraduate level?"

You answer, it moves on. After 2–3 questions (or if you skip them all), it starts writing immediately.

---

## Direct — No Forge Needed

If you give enough context upfront, the forge is skipped entirely:

**You say:**
> "Write a 1000-word undergraduate essay on the challenges of Big Data, APA citations, due tomorrow"

**What happens:**
Enough context detected. Pipeline starts immediately — no questions asked.

---

## Coding Assignments

**You say:**
> "I have a Python homework problem: find the longest common subsequence of two strings"

**What happens:**
The coding pipeline activates. You get:
- Approach explanation (algorithm choice + reasoning)
- Structurally original implementation (non-textbook structure)
- Time + space complexity
- Possible improvements

---

## Reducing Plagiarism in Existing Text

**You say:**
> "Make this less likely to be flagged. Here's my draft: [paste text]"

**What happens:**
The plagiarism guard scans every section and rates it LOW / MEDIUM / HIGH risk. Only HIGH and MEDIUM sections are rewritten. LOW stays as-is to preserve your voice.

---

## Section-Only Writing

**You say:**
> "Just write the introduction for my report on climate change adaptation"

**What happens:**
Introduction only is written following the analytical intro rules (no definitions, context-first). Offered: "Want me to write the rest of the report?"

---

## Making It Sound Less Like AI

**You say:**
> "This sounds too AI-generated, fix it"

**What happens:**
Style pass runs first — sentence types are varied across all paragraphs. Then plagiarism guard rewrites high-risk phrases. The result reads more natural and analytically distinct.

---

## Citation Pass

**You say:**
> "Add Harvard citations to this essay"

**What happens:**
References are identified from factual claims in the text. Citations are added in Harvard format inline and in a reference list at the end.

---

## Common Commands

| What you say | What you get |
|---|---|
| `"Write my assignment on [topic]"` | Full 6-stage pipeline output |
| `"Do my [language] homework: [problem]"` | Coding solution with approach + complexity |
| `"Reduce plagiarism in: [text]"` | Guard + style pass on your text |
| `"Write just the intro for [topic]"` | Introduction only |
| `"Make this sound less like AI"` | Style variation + phrase rewrite |
| `"Add APA citations"` | Citation pass |
| `"Start a new assignment"` | Assignment Forge runs |

---

## Tips

- **Paste your rubric** — if you paste your professor's marking criteria, the skill writes directly to those requirements.
- **Paste your partial draft** — even if you've started, the skill can continue from where you left off or refine what you have.
- **Specify your university** — some institutions have formatting rules; mentioning "Oxford style" or "MIT formatting" helps calibrate the output.
- **Use "section-only" mode** for tight deadlines — it's faster and you can chain requests ("now write the methodology").
