# Changelog

All notable changes to the `truedraft` skill will be documented in this file.

## v1.1.0 — 2026-06-21
- **Synergistic Integration (Research Dojo):** Integrated modular cross-referencing capabilities with the companion `Research Dojo` skill.
  - Added the Research Dojo workflow integration documentation to `README.md`.
  - Added conditional checks inside `open_generation` and `notes_first` pipelines in `SKILL.md` and `plan.md` to leverage Dojo's stress-tested arguments, and pre-populate onboarding details.

## v1.0.0 — 2026-06-21
- **TrueDraft Rebranding & Baselining:** Re-baselined the skill from `assignment-writer-skill` to `truedraft`. Reorganized the entire project structure and renamed paths to align with the core originality-first positioning.
- **Interactive Onboarding (The Forge):** Standardized a 9-question setup mapping institutional guidelines, word budget, and rubrics directly to project context.
- **Five-Stage Writing Pipeline:** Restructured the core flow into distinct stages: `plan`, `outline`, `draft`, `rewrite` (incorporating originality and readability passes), and `audit`.
- **Search-First Citation Engine:** Strict policy to search real scholarly databases/web using host tools, and default entirely to placeholders on search failure to prevent hallucinated references.
- **Originality & Readability Rewriter:** Implemented style-randomization (perplexity/burstiness tuning) and the `Humanise` readability passes (Light, Standard, Conversational) to remove robotic, predictable writing patterns.
- **CS/Data Science Stage:** Calibrated programming and report workflow supporting modular design, computational complexity mapping, and algorithm variety.

---

## Legacy Version History (as assignment-writer-skill)

Before rebranding and baselining as `truedraft v1.0.0`, the following iterations were released under the name `assignment-writer-skill`:

### v1.2.2 — 2026-03-14
- **Source Divergence Awareness:** Added a Source Divergence Audit stage to research and identify authoritative sources on a topic, blacklist their examples and framings, and require alternative illustrations to prevent n-gram and structure overlap.
- **Canonical Example Scan:** Integrated a pre-drafting scanner into the originality pass to identify and replace 14 common pedagogical illustrations (e.g., spam filters, bias-variance tradeoff graphs) with domain-shifted alternatives.

### v1.2.1 — 2026-03-14
- **Grammar & Punctuation Pass:** Added `references/grammar.md` containing 8 rule categories (including introductory clauses, em/en dash formatting, tense consistency, and Oxford commas) along with a grammar checklist inside the audit stage.

### v1.2.0 — 2026-03-14
- **Humanise Readability Mode:** Integrated a readability pass with three levels (Light, Standard, and Conversational) and two tone settings to produce human-sounding flow, outputting a detailed before/after sentence comparison table.
- **Discipline-Specific Support (Data Science & Commerce):** Added custom writing structures and defaults for Data Science/CS (mandating Big-O analysis and dataset sizing methodology) and Commerce (utilizing theory-first evaluation structures and financial work ratios).
- **Essay Improvement Pipeline:** Added a custom workflow to critique, humanise, style, and review pre-written drafts pasted by the user.

### v1.1.0 — 2026-03-13
- **Context Footprint Optimization:** Split core documentation out of `SKILL.md` into `docs/FEATURES.md` and `docs/USAGE.md` to optimize agent context window usage during execution.

### v1.0.0 — 2026-02-24
- **Initial Release:** Launched the initial version featuring the onboarding engine, 6-stage pipeline, analytical intro engine, style randomization, n-gram disruption, citation support, learning mode, and rubric-aware self-review checklists.
