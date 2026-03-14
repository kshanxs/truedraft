<div align="center">

<br>

# assignment-writer

### *The Academic Writing Studio*

*Plagiarism-resistant writing · Anti-AI-pattern engine · Rubric-aware mark targeting · Code originality toolkit*

<br>

[![Version](https://img.shields.io/badge/version-1.2.2-8957e5?style=for-the-badge&labelColor=161b22)](./CHANGELOG.md)
[![License](https://img.shields.io/badge/License-MIT-2ea043?style=for-the-badge&labelColor=161b22)](./LICENSE)
[![Docs](https://img.shields.io/badge/Docs-USAGE.md-f78166?style=for-the-badge&labelColor=161b22)](./docs/USAGE.md)
[![Features](https://img.shields.io/badge/Features-FEATURES.md-0d9488?style=for-the-badge&labelColor=161b22)](./docs/FEATURES.md)
[![Changelog](https://img.shields.io/badge/Changelog-CHANGELOG.md-e3b341?style=for-the-badge&labelColor=161b22)](./CHANGELOG.md)

<br>

</div>

> [!CAUTION]
> **This skill is not a shortcut for skipping learning.**
> Using AI to write your assignments wholesale — without understanding the content — defeats the purpose of education. You will fall behind in exams, practical work, and your career. This tool is most useful when you already understand the material and need help expressing it clearly, structuring your argument, or reducing unintentional similarity from legitimate paraphrasing.

---

## What it actually does

A skill that helps AI assistants write academic content — essays, reports, and coding assignments — in a way that avoids common plagiarism detection patterns.

- Writes academic content in an analytical style, avoiding textbook phrasing that plagiarism detectors flag
- Helps restructure poorly worded existing drafts
- Generates code solutions with explanations — not just answers
- Supports rubric-based writing when you provide marking criteria
- Handles citations in APA, MLA, Harvard, and IEEE formats

It does **not** guarantee any particular plagiarism score. Detection tools are constantly improving. If your institution uses AI-detection alongside plagiarism checking, this skill cannot circumvent that.

---

## ✨ Highlights

| | |
|---|---|
| 🔬 **6-Stage Pipeline** | Research → Write → Style → Guard → Review — each stage lazily loaded |
| 🛡️ **Dual-Mode Plagiarism Guard** | Scans pipeline output or pasted external text, scores LOW / MEDIUM / HIGH per section |
| 📋 **Rubric Awareness** | Parses marking criteria, identifies highest-weight dimensions, targets top-band marks |
| ✍️ **Analytical Intro Engine** | Never generates definition openers — analytical context, problem framing, or historical perspective |
| 🔀 **Style Randomization** | Rotates 5 sentence types per paragraph to break AI-pattern fingerprinting |
| 💻 **Code Originality** | Algorithm diversity rule, descriptive naming, modular structure — beats MOSS / JPlag |
| 📚 **Citation Engine** | APA 7, MLA 9, Harvard, IEEE — in-text and full reference list |
| 🧠 **Assignment Memory Bank** | Persists topic, style profile, and risk log across sessions |
| ✅ **Verified Checklist Review** | Every quality gate actively confirmed — failing items fixed inline before delivery |

**→ [See all features](./docs/FEATURES.md)**

---

## 💬 Quick Start

```
"Write my assignment on neural networks for my Machine Learning course"
"Do my Python homework — Two Sum problem"
"I have a draft, help me reduce plagiarism"
"Here's my rubric: [paste] — write to it"
"Write a 1000-word lab report on osmosis, APA style"
```

The AI guides you through setup one question at a time. Every question is skippable.

**→ [Full usage guide with examples](./docs/USAGE.md)**

---

## ⚡ Command Reference

| Say this… | What happens |
|---|---|
| `"Write my assignment on [topic]"` | Full pipeline — research, draft, style pass, guard, review |
| `"Do my [language] homework: [problem]"` | Coding solution with approach + complexity |
| `"Check/reduce plagiarism in: [paste]"` | Rewrite mode — guard + style pass on your text |
| `"Write just the [intro/conclusion] for [topic]"` | Section-only mode |
| `"Here's my rubric: [paste]"` | Rubric-aware writing |
| `"Add APA citations"` | Citation pass |
| `"Make this sound less like AI"` | Style + guard pass |
| `"Start a new assignment"` | Assignment Forge onboarding |

**→ [Full command reference](./docs/FEATURES.md)**

---

## 📁 Structure

```
assignment-writer-skill/        ← GitHub repo root
├── README.md
├── LICENSE
├── docs/                       ← Human-readable guides (browse on GitHub)
│   ├── USAGE.md
│   └── FEATURES.md
└── assignment-writer/          ← Skill folder (drop into .agents/skills/)
    ├── SKILL.md                ← Entry point
    ├── pipeline/               ← 6 processing stages
    ├── references/             ← Writing rules, disciplines, rubric, citations
    │   └── disciplines/        ← Science · Data Science/CS · Humanities · Law · Business · Commerce
    ├── assets/templates/       ← Memory bank templates
    └── examples/               ← STEM, coding, humanities, data science, commerce sample outputs
```

### Installation

Drop the `assignment-writer/` folder into your agent skills directory:

```bash
# Claude Code / Antigravity / any .agents/skills/ compatible agent
cp -r assignment-writer /path/to/.agents/skills/assignment-writer
```

---

## Intended use cases

- **Drafting assistance** — you have an outline or rough ideas, need help forming them into coherent sentences
- **Paraphrase improvement** — your existing writing is flagged because of how a concept is phrased, not because it was copied
- **Structural guidance** — you understand the topic but aren't sure how to organise it
- **Coding explanations** — you need a worked solution you can actually learn from, not just copy

---

## Ethical note

Academic integrity policies exist for a reason. Before using this tool, check your institution's rules on AI assistance. Many universities now permit AI for drafting or editing — but require disclosure. Some do not permit it at all. That boundary is yours to respect, not this skill's to enforce.

---

<div align="center">

[MIT License](LICENSE) · [Changelog](CHANGELOG.md) © [Shubhanshu](https://github.com/kshanxs)

*An open-source academic writing skill for AI assistants.*

</div>
