# Changelog

All notable changes to the assignment-writer skill are documented here.  
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [1.2.1] — 2026-03-14

### Added
- **Grammar & Punctuation pass** — new `references/grammar.md` with 8 rule categories and active quick-check protocol:
  - Subject-verb agreement
  - Comma rules (introductory clauses, Oxford comma, compound sentences, which/that)
  - Hyphenation of compound modifiers; em/en dash vs hyphen usage
  - Apostrophes (`its` vs `it's`, possessive plurals)
  - Parallelism in lists
  - Comma splice and rogue fragment detection
  - Academic-specific rules (tense consistency, "however" placement, number formatting)
- **Grammar checklist section** added to `pipeline/review.md` — 9 active checks, inline fixes, reported in the pass/fail summary

---

## [1.2] — 2026-03-14

### Added
- **Humanise Mode** — new `references/humanise.md` and `pipeline/humanise.md`
  - 10 core readability rules (filler removal, active voice, analogies, rhythm variation)
  - Two tone modes: Academic-Conversational and Fully Conversational
  - Three intensity levels: Light / Standard / Conversational
  - Runs standalone on pasted text or as a pipeline stage (after Style, before Plagiarism Guard)
  - Outputs a Before/After table of the most-changed sentences
- **Data Science / CS discipline** — new `references/disciplines/data_science_cs.md`
  - Code-prose hybrid rules, mandatory Big-O complexity analysis
  - Dataset methodology requirements (source, size, splits, bias)
  - ML hedging language guidelines
  - Figure and visualisation description standards
  - IEEE / ACM / APA 7 citation defaults
- **Commerce discipline** — new `references/disciplines/commerce.md`
  - Theory-first writing structure (identify concept → apply → evaluate)
  - Explicit evaluation scaffolding ("however", "in the long run", "this assumes...")
  - Economics frameworks: PED/YED/XED, market structures, externalities, fiscal/monetary policy
  - Accounting ratio analysis with workings requirements
  - Harvard citation defaults
- **Workflow 7: Improve My Essay** — defined pipeline for students with finished work
  - Critique → Humanise → Style → Guard → Review with a change summary at the end
- **Two new examples**
  - `examples/data_science_example.md` — overfitting in ML (code-prose, ML hedging, evidence-before-interpretation)
  - `examples/commerce_example.md` — minimum wage economics essay (theory-first, evaluation scaffolding)

### Changed
- **Full pipeline extended** — Humanise stage inserted between Style and Plagiarism Guard
- **Rewrite workflow updated** — Humanise now included after Style in the de-risk flow
- **Command reference expanded** — new triggers: `"Humanise this"`, `"Make this more conversational"`, `"Improve my essay"`
- **Discipline detection updated** in `references/assignment_forge.md` and `pipeline/writer.md` — Data Science/CS and Commerce now correctly routed; `science.md` and `business.md` trigger conditions clarified for MBA/corporate vs. school-level use
- **Discipline-Specific Rules feature** description updated to include the two new disciplines
- **README structure listing** updated to reflect new disciplines and examples

### Fixed
- **Broken file path** in `pipeline/style.md` — `frameworks/style_randomization.md` corrected to `references/style_randomization.md` (was silently skipping the style framework on every run)
- **Duplicate Q5 label** in `references/assignment_forge.md` — rubric question renumbered; full sequence now correctly Q1–Q10
- **Learning mode gap** — `references/learning_mode.md` now includes a Humanise stage note with before/after examples
- **Missing discipline routes** — `pipeline/writer.md` discipline table was missing Data Science/CS and Commerce

---

## [1.1] — 2026-03-13

### Changed
- Restructured skill directory for publication — separated `docs/` from core skill files
- Trimmed `SKILL.md` to reduce context load; moved extended documentation to `docs/FEATURES.md` and `docs/USAGE.md`
- Ensured all reference file links in `SKILL.md` resolve to correct relative paths

---

## [1.0] — 2026-02-24

### Initial release

- **Assignment Forge** — 9-question onboarding (topic, level, word count, citation, institution, rubric, instructions, draft/notes, learning mode). All questions skippable. Resumes previous sessions.
- **Assignment Memory Bank** — persists topic, style profile, and risk log across sessions in `assignment-memory/`
- **6-Stage Pipeline** — Research → Write → Style → Code → Guard → Review, each stage independently loadable
- **Analytical Intro Engine** — never generates definition-based openings
- **Semantic Expansion** — explain → example → implication per concept
- **Style Randomization** — 5 sentence types rotated per paragraph; perplexity/burstiness simulation
- **N-gram Disruption** — actively breaks 4+ word sequences matching common academic phrasing
- **Dual-Mode Plagiarism Guard** — internal mode (pipeline text) and rewrite mode (pasted text), with risk scores and change summary
- **Rubric Awareness** — parses marking criteria, targets highest-weight dimensions
- **Discipline support** — Science / Humanities / Law / Business
- **Citation Engine** — APA 7, MLA 9, Harvard, IEEE
- **Learning Mode** — explains every writing decision inline
- **Code Originality Framework** — algorithm diversity, descriptive naming, modular structure, complexity analysis
- **Self-Review Layer** — 8-stage verified checklist with inline fixes
