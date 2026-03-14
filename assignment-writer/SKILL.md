---
name: assignment-writer
description: "Academic writing assistant for assignments, essays, lab reports, research papers, and coding homework. Produces analytically written, structurally original content with built-in plagiarism resistance (anti-n-gram, style variation, algorithm diversity). Use this skill when a user asks to write, complete, improve, or de-risk any academic work — including homework, university submissions, coding problems, or when pasting text they want rewritten to sound less like AI."
---

# assignment-writer

Academic writing assistant. Produces analytically structured essays, reports, and code solutions — argument-first, source-resistant, discipline-calibrated.

---

## Context Efficiency Rule

**CRITICAL — Read this before loading any files.**

Use **lazy loading** — only read a reference file when its specific feature is needed:

| Only load this file… | When… |
|---|---|
| `references/academic_skill.md` | Starting the writing phase or reviewing final output |
| `references/style_randomization.md` | Running the style pass |
| `references/self_review.md` | Running the plagiarism guard or final review |
| `references/grammar.md` | Running the final review pass (always load alongside self_review.md) |
| `references/assignment_forge.md` | At initialization / first use / session resumption |
| `references/rubric_guide.md` | User provides a rubric or marking criteria |
| `references/citation_guide.md` | Adding citations or user specifies a citation style |
| `references/learning_mode.md` | User says "explain as you go" or "learning mode" |
| `references/disciplines/science.md` | Course is science, engineering, medicine, or general CS |
| `references/disciplines/humanities.md` | Course is literature, history, philosophy, or arts |
| `references/disciplines/law.md` | Course is law or legal studies |
| `references/disciplines/business.md` | Course is business, management, or economics (MBA/corporate level) |
| `references/disciplines/data_science_cs.md` | Course is Data Science, Computer Science, ML, AI, Software Engineering, or Statistics |
| `references/disciplines/commerce.md` | Course is Commerce, Business Studies, introductory Economics, or Accounting |
| `pipeline/research.md` | Analyzing the assignment topic |
| `pipeline/writer.md` | Drafting the initial content |
| `pipeline/style.md` | Applying sentence variation |
| `pipeline/humanise.md` | Making writing natural and easy to read |
| `pipeline/coding.md` | Task includes programming |
| `pipeline/plagiarism_guard.md` | Scanning for similarity risks (internal OR rewrite mode) |
| `pipeline/review.md` | Final quality check |

**Never load more than 3–4 files in a single pass unless the task explicitly requires it.**

---

## ✨ Features

- **Assignment Forge** — 9-question onboarding: topic, level, word count, citation, institution, rubric, instructions, draft/notes, learning mode. All skippable. Resumes previous sessions automatically.
- **Assignment Memory Bank** — Persists topic, style profile, and plagiarism risk log across sessions in `assignment-memory/`
- **6-Stage Pipeline** — Research → Write → Style → Code → Guard → Review. Each stage independently loadable.
- **Draft-First Mode** — Paste your own notes or outline; the pipeline builds on your ideas instead of starting from scratch
- **Analytical Intro Engine** — Never generates definition-based openings. Chooses from: analytical context, problem framing, historical perspective.
- **Semantic Expansion** — Each concept gets: explain → example → implication. Increases semantic distance from source material.
- **Style Randomization** — Rotates 5 sentence types per paragraph + perplexity/burstiness simulation (sentence length variation + low-frequency vocabulary)
- **N-gram Disruption** — Actively breaks 4+ word sequences that match common academic phrasing.
- **Dual-Mode Plagiarism Guard** — *Internal mode*: scans pipeline output. *Rewrite mode*: accepts pasted text, scores each section LOW/MEDIUM/HIGH, rewrites only flagged parts.
- **Change Summary** — After every rewrite pass, shows a before/after diff table of every altered sentence
- **Risk Log** — Plagiarism guard writes a full audit trail to `assignment-memory/risk_log.md` after every pass.
- **Rubric Awareness** — Parses marking criteria, identifies highest-weight dimensions, injects critical analysis to target top-band marks.
- **Discipline-Specific Rules** — Science (IMRAD, passive, hedging) · Humanities (argument-first, textual analysis) · Law (IRAC, citation authority) · Business (exec summary, quantified claims) · Data Science/CS (code-prose hybrid, Big-O, dataset methodology, ML hedging) · Commerce (theory-first, evaluation scaffolding, ratio analysis)
- **Institution Awareness** — Adjusts formatting conventions based on institution (e.g. Oxford = Chicago footnotes, MIT = IEEE)
- **Word Count Pacing** — Distributes word budget proportionally across sections before writing begins
- **Code Originality Framework** — Algorithm diversity rule, descriptive naming, modular structure, complexity analysis.
- **Self-Review Layer** — 8-stage verified checklist: every item actively confirmed, not skimmed. Failing items fixed inline before being checked off.
- **Citation Engine** — Full formatting support for APA 7, MLA 9, Harvard, and IEEE.
- **Learning Mode** — Explains every writing decision as it’s made: what technique, why, before/after examples
- **Section-only mode** — Write just the introduction, conclusion, or a specific section.
- **Humanise Mode** — Makes writing genuinely easy to read: cuts filler phrases, activates voice, adds analogies, varies rhythm. Three intensity levels (Light / Standard / Conversational). Runs standalone on pasted text or as a pipeline stage after the Style Agent. Shows a Before/After table of the most changed sentences.

→ Full features catalog: `../docs/FEATURES.md`

---

## 💬 Quick Start

```
"Write my assignment on machine learning for Data Science 101"
"Do my Python homework — Two Sum problem"
"I have a draft essay, help me reduce plagiarism"
"Write just the introduction for my Networks report"
"Write a 1000-word lab report on osmosis, APA style"
```

The skill guides you through the Assignment Forge one question at a time. Every question is skippable.

→ Full usage guide with examples: `../docs/USAGE.md`

---

## ⚡ Command Reference

| Say this… | What happens |
|---|---|
| `"Write my assignment on [topic]"` | Full pipeline runs end-to-end |
| `"Do my [language] homework: [problem]"` | Coding pipeline activates |
| `"Reduce plagiarism in this text: [paste]"` | Guard + Review on existing content |
| `"Write just the introduction for [topic]"` | Section-only mode |
| `"Add APA citations"` | Citation pass added |
| `"Make this sound less like AI"` | Style + Guard pass only |
| `"Humanise this"` / `"Make this easier to read"` | Humanise Agent runs on pasted text |
| `"Make this more conversational"` | Humanise Agent runs at Level 3 |
| `"Improve my essay"` / `"Make this better"` | Critique + Humanise + Style + Guard + Review |
| `"Start a new assignment"` | Assignment Forge runs |

---

## 📁 Project Structure

When you start a new assignment project, the following is auto-created in your working directory:

```
YourAssignment/
├── README.md              ← Auto-generated with assignment details
├── draft.md               ← Working draft
├── final.md               ← Polished output
└── assignment-memory/
    ├── topic.md            ← Subject, course, requirements
    ├── style_profile.md   ← Tone, citation style, word count
    └── risk_log.md        ← Plagiarism Guard audit trail
```

---

## Workflows

### 1. Initialization — Assignment Forge

When the user says "start a new assignment", "help me with my assignment", or provides an assignment topic for the first time:

1. **Run the Assignment Forge first.** Read `references/assignment_forge.md` and follow its onboarding questions one at a time. Every question is skippable.
2. Create the `YourAssignment/assignment-memory/` directory and populate `topic.md` and `style_profile.md` from the forge answers.
3. Auto-generate `README.md` using the template in `assets/templates/readme_template.md`.
4. Begin the pipeline only after — or skip forge and go straight to writing if the user provides enough context upfront.

### 2. Full Pipeline — Write an Assignment

When the user asks to write or complete an assignment:

1. Load `pipeline/research.md` → Analyze topic, produce structured notes
2. Load `pipeline/writer.md` + `references/academic_skill.md` → Draft analytically
3. Load `pipeline/style.md` + `references/style_randomization.md` → Vary sentence types
4. Load `pipeline/humanise.md` + `references/humanise.md` → Make writing natural and readable
5. *(If coding)* Load `pipeline/coding.md` → Generate structurally original code
6. Load `pipeline/plagiarism_guard.md` + `references/self_review.md` → Score + rewrite HIGH/MEDIUM risks
7. Load `pipeline/review.md` → Final checklist audit
8. Deliver the final output. Save to `final.md` if a project directory exists.

### 3. Rewrite / De-risk Existing Text

When the user pastes text and asks to reduce plagiarism or make it less AI-sounding:

1. Load `pipeline/plagiarism_guard.md` → Score all sections, rewrite flagged ones
2. Load `pipeline/style.md` → Apply sentence variation
3. Load `pipeline/humanise.md` + `references/humanise.md` → Apply readability pass
4. Load `pipeline/review.md` → Final check
5. Return the improved version with a note on what was changed.

### 4. Section-Only Mode

When the user asks for just one section (intro, conclusion, body paragraph):

1. Load `pipeline/research.md` → Context notes for that section only
2. Load `pipeline/writer.md` + `references/academic_skill.md` → Write that section
3. Load `pipeline/plagiarism_guard.md` → Quick scan
4. Deliver the section. Offer to write adjacent sections next.

### 5. Coding Assignment

When the task involves programming:

1. Load `pipeline/research.md` → Understand the problem, note algorithm options
2. Load `pipeline/coding.md` → Generate structurally original solution
3. Load `pipeline/plagiarism_guard.md` → Code similarity check (token patterns, variable names)
4. Load `pipeline/review.md` → Verify approach explanation + complexity analysis

### 6. Learning Mode

When the user says "explain as you go", "learning mode", "teach me", or "show me why":

1. Load `references/learning_mode.md` and keep active for the entire session
2. Run the full pipeline normally
3. After each stage, insert a `💡 Learning note:` explaining the technique used and why

### 7. Improve My Essay

When the user pastes a finished or near-finished essay and asks to improve it ("make this better", "improve my essay", "give me feedback and fix it"):

1. **Read the full text silently first** — understand scope, argument, and discipline
2. **Produce a brief critique** before changing anything:
   - Structure: does the argument flow logically?
   - Depth: are claims supported with evidence and analysis?
   - Tone: is it appropriately academic?
   - Risk: any obvious plagiarism or AI-detection risks?
3. Load `pipeline/humanise.md` → Readability pass (Level 2 default)
4. Load `pipeline/style.md` → Sentence variation
5. Load `pipeline/plagiarism_guard.md` → Score + rewrite flagged sections
6. Load `pipeline/review.md` → Final checklist
7. Deliver the improved essay with a summary of what was changed and why

---

## 📄 References

| File | Purpose |
|---|---|
| `references/assignment_forge.md` | Onboarding: collects topic, level, word count, rubric, citations. Initialises memory bank. |
| `references/academic_skill.md` | Core writing rules — intro, structure, n-gram prevention, citations |
| `references/style_randomization.md` | Five sentence types, rotation rules, burstiness simulation |
| `references/humanise.md` | Readability rules: filler removal, active voice, analogies, rhythm variation, tone modes, intensity levels |
| `references/self_review.md` | 8-stage similarity audit checklist |
| `references/grammar.md` | Grammar and punctuation rules: subject-verb agreement, commas, hyphenation, dashes, apostrophes, parallelism |
| `references/rubric_guide.md` | Rubric parsing, mark-band targeting, required section detection |
| `references/citation_guide.md` | APA 7, MLA 9, Harvard, IEEE in-text and reference list formats |
| `references/learning_mode.md` | Explains every writing decision inline — technique, why, before/after |
| `references/disciplines/science.md` | IMRAD structure, passive voice, hedging, evidence-before-interpretation |
| `references/disciplines/humanities.md` | Argument-first, textual analysis, interpretation over description |
| `references/disciplines/law.md` | IRAC structure, citing authority, precision language |
| `references/disciplines/business.md` | Exec summary first, quantified claims, framework application (MBA/corporate) |
| `references/disciplines/data_science_cs.md` | Code-prose hybrid, Big-O analysis, dataset methodology, ML hedging, IEEE/ACM citation |
| `references/disciplines/commerce.md` | Theory-first writing, evaluation scaffolding, ratio analysis, A-level/undergraduate economics |
| `pipeline/research.md` | Topic analysis → structured notes |
| `pipeline/writer.md` | Analytical draft generation with draft-first mode + word count pacing |
| `pipeline/style.md` | Sentence variety pass |
| `pipeline/humanise.md` | Readability pass — 3 intensity levels, standalone or pipeline, Before/After table |
| `pipeline/coding.md` | Original code generation |
| `pipeline/plagiarism_guard.md` | Dual-mode risk detection + targeted rewriting + risk_log.md output |
| `pipeline/review.md` | Verified checklist audit — every item actively confirmed |
| `assets/templates/topic_template.md` | Memory bank template — assignment requirements |
| `assets/templates/style_profile_template.md` | Memory bank template — tone and style settings |
| `assets/templates/risk_log_template.md` | Memory bank template — plagiarism audit trail |
| `assets/templates/readme_template.md` | Auto-generated project README |
| `../docs/USAGE.md` | Human-readable guide with example dialogues |
| `../docs/FEATURES.md` | Full features catalog |
| `examples/essay_example.md` | Sample STEM essay (Machine Learning) |
| `examples/coding_example.md` | Sample original coding solution (Two Sum) |
| `examples/humanities_example.md` | Sample humanities essay (Political Polarisation) |
| `examples/data_science_example.md` | Sample Data Science essay (Overfitting in ML) |
| `examples/commerce_example.md` | Sample Commerce essay (Minimum Wage and Employment) |
