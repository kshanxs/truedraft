# TrueDraft Usage

This skill features interactive onboarding, five pipeline writing stages, search-first citations, style customization, and inline learning explanations.

---

## 1. Interactive Onboarding (The Forge)

**You say:**
> "Start a new assignment on machine learning"

**What happens:**
TrueDraft initiates the **Assignment Forge** (`pipeline/forge.md`). It asks you one onboarding question at a time (e.g. course level, target word count, citation style, marking rubric, special instructions). Any question can be skipped. TrueDraft then initializes the project memory (`brief.md`, `style_profile.md`) and prompts you to begin the plan and outline stages.

---

## 2. Topic-Only Drafting (Open Generation)

**You say:**
> "Write a 1200-word draft on climate adaptation"

**What happens:**
1. TrueDraft runs onboarding if needed, then builds a claim plan.
2. It proposes an outline detailing section budgets and argument flow.
3. **Approval Gate:** TrueDraft pauses and waits for your outline approval before drafting long-form prose.
4. Once approved, it drafts, rewrites (style + readability), and audits the draft.

---

## 3. Notes-First Drafting

**You say:**
> "Use these notes to draft my literature review: [paste notes]"

**What happens:**
TrueDraft treats your notes as the source of truth. It expands them, fills structural gaps, and uses search tools to locate academic sources for the claims in your notes. Unverifiable claims are left as placeholders.

---

## 4. Draft Rewrite & Humanisation

**You say:**
> "Refine this draft so it sounds less formulaic: [paste draft]"
> or
> "Humanise this text and make it more conversational: [paste text]"

**What happens:**
TrueDraft reads the full text and applies readability and style randomization passes. It removes filler words, improves rhythm with short/long sentence mixtures, and runs tone adjustment (Light, Standard, or Conversational). It returns the updated text followed by a **Before/After change summary table**.

---

## 5. Coding and Data-Science Assignments

**You say:**
> "Solve this Java assignment and explain time complexity"
> or
> "Write the implementation and evaluation section for my ML project"

**What happens:**
TrueDraft auto-detects coding-first or mixed-prose-and-code requirements. It applies CS/data-science conventions (modular functions, descriptive naming, algorithm diversity, complexity analysis, metrics logging) and keeps placeholders for missing dataset facts or benchmark numbers.

---

## 6. Citation & Search-First Engine

**You say:**
> "Add APA citations to this draft"

**What happens:**
1. **Search Attempt:** TrueDraft checks if the host has web search or Google Scholar tools. If available, it searches for real, peer-reviewed studies matching the claims.
2. **Formatting:** It formats retrieved sources in the requested citation style (APA 7th, MLA 9th, Harvard, or IEEE).
3. **No Search/Failure Fallback:** If search is unavailable or returns no definitive matches, it inserts explicit placeholders like `[CITE: source needed for claim about: "..."]`. It never fabricates citations.
4. **Verification Log:** It logs all successfully searched citations in `audit_log.md` with URLs for you to verify.

---

## 7. Learning Mode

**You say:**
> "Explain as you go / Start learning mode"

**What happens:**
TrueDraft activates `references/learning_mode.md`. While drafting and editing, it inserts a `💡 Learning note:` after each block or stage. These notes explain stylistic decisions (e.g., why a sentence rhythm was broken, how a passive voice sentence was activated, or what makes an introduction opener unique).

---

## Common Commands

| What you say | What you get |
|---|---|
| `"Start a new assignment"` | Assignment Forge runs (onboarding) |
| `"Write a draft on [topic]"` | `open_generation` mode with plan and outline gate |
| `"Use these notes to write [topic]"` | `notes_first` mode, using notes as source of truth |
| `"Refine this draft" / "Reduce similarity in this"` | `draft_rewrite` originality pass |
| `"Humanise this" / "Make this easier to read"` | Readability rewrite (Level 2 Standard default) with Before/After table |
| `"Make this more conversational"` | Readability rewrite (Level 3 Conversational) |
| `"Explain as you go" / "Learning mode"` | Activates inline writing/design explanations |
| `"Solve this coding assignment: [problem]"` | coding-first workflow with structured solutions |
| `"Write implementation for this ML project"` | mixed-mode workflow with coding stage + report-safe prose |
| `"Show me the claim plan first"` | Plan stage only |
| `"Build the outline and wait"` | Outline stage only |
| `"Audit this draft before delivery"` | Final checklist audit, web-searched citation URLs list, and trust note |

---

## Tips

- **Paste your rubric:** Pasting marking criteria will automatically calibrate the thesis and section word counts to target top-band marks in high-weight categories.
- **Provide notes:** Grounding the draft in your bullet points or outline ensures the final output keeps your voice and ideas.
- **Verify URLs:** Always check the web-searched sources logged in `project-memory/audit_log.md` to ensure they match your expected literature before submitting.
- **Resolve placeholders:** Never submit a draft containing active `[CITE]` or `[UNVERIFIED]` placeholders.
