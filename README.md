<div align="center">

<br>

# ✦ TrueDraft ✦

### *The Originality-First Academic Writing Assistant*

*Calibrated onboarding · Constraint-gated planning · Humanise readability · Search-first academic citations*

<br>

[![Version](https://img.shields.io/badge/version-1.2.0-8957e5?style=for-the-badge&labelColor=161b22)](./docs/FEATURES.md)
[![Install](https://img.shields.io/badge/⚡_Install-npx_skills_add-0d1117?style=for-the-badge&labelColor=161b22)](https://github.com/kshanxs/truedraft)
[![License](https://img.shields.io/badge/License-MIT-2ea043?style=for-the-badge&labelColor=161b22)](./LICENSE)
[![Docs](https://img.shields.io/badge/Docs-USAGE.md-f78166?style=for-the-badge&labelColor=161b22)](./docs/USAGE.md)

<br>

*Most AI assistants give you recycled templates and invented citations. TrueDraft gives you process discipline —*
*mapping your arguments first, enforcing structure gates, polishing prose with style randomization, and never hallucinating sources.*

</div>

---

## 🚀 Installation

```bash
npx skills add https://github.com/kshanxs/truedraft --skill truedraft
```

### Update to latest version

```bash
npx skills update truedraft
```

---

## 💬 Quick Start

```text
"Start a new assignment on machine learning"
"Write a 1200-word draft on climate adaptation"
"Use these notes to write my literature review"
"Refine this draft so it sounds less formulaic"
"Humanise this text and make it more conversational"
"Solve this Python homework and analyze complexity"
"Explain as you go / Start learning mode"
```

The AI guides you through setup one question at a time. Every question is skippable.

**→ [Full usage guide with examples](./docs/USAGE.md)**

---

## ✨ Highlights

| | |
|---|---|
| 🛠️ **The Assignment Forge** | 9-question interactive onboarding (rubrics, citation style, constraints) |
| 🛡️ **Originality-First Rewrite** | Style randomization (perplexity/burstiness tuning) to break formulaic phrasing |
| 🧬 **Source Divergence Scan** | Pre-drafting check blacklisting canonical examples and stock analogies |
| 🔍 **Search-First Citation Engine** | Uses host search tools to locate real papers; strictly defaults to placeholders on search fail |
| ✍️ **Humanise Readability passes** | Three levels (Light / Standard / Conversational) with before/after sentence audits |
| 💡 **Inline Learning Mode** | Teaches academic structure as it writes using `💡 Learning note:` annotations |
| 💻 **CS & Data Science Discipline** | Calibrated hybrid prose-code workflows with Big-O complexity checks and algorithm diversity |
| 📁 **Project Memory Bank** | Auto-maintained profiles and audit logs in `project-memory/` |

**→ [See all features and specifications](./docs/FEATURES.md)**

---

## ⚡ Command Reference

| Say this | What happens |
|---|---|
| `"Start a new assignment"` | Launches the Assignment Forge onboarding |
| `"Write my assignment on [topic]"` | Onboarding → Plan → Outline Gate → Draft → Rewrite → Audit |
| `"Reduce similarity in this draft: [paste]"` | Executes the Originality pass and returns a comparison table |
| `"Humanise this"` / `"Make this easier to read"` | Readability pass with standard intensity level |
| `"Make this more conversational"` | Readability pass with high (Conversational) intensity level |
| `"Solve this programming task"` | Launches CS/Data Science hybrid prose-code workflow |
| `"Explain as you go"` / `"Learning mode"` | Activates inline teaching notes explaining structural and lexical choices |

**→ [Full command reference](./docs/FEATURES.md#-command-reference)**

---

## 📁 Project Structure

When active in a project directory, TrueDraft maintains the following structure:

```text
YourDraftProject/
├── README.md               ← Auto-generated project overview
├── working.md              ← Intermediate draft output
├── final.md                ← Final audited, polished manuscript
└── project-memory/         ← Auto-maintained by the AI assistant
    ├── brief.md            ← Onboarding specifications & constraints
    ├── style_profile.md    ← Citations, tone settings, and level profile
    └── audit_log.md        ← History of rewritten sentences & verified citations
```

---

## 🤝 Synergistic Companions: Research Dojo & Calligraph Sensei

TrueDraft works seamlessly with other specialized skills to cover the entire lifecycle of research, drafting, and polishing:

1. **Adversarial Research (Phase 0 — [Research Dojo](https://github.com/kshanxs/research-dojo)):** Use Research Dojo to stress-test your claims, map active academic debates, audit evidence, and build a high-density concept map.
2. **Academic Drafting (Phase 1 — TrueDraft):** Feed the audited synthesis or final judgment notes from Research Dojo directly into TrueDraft's `notes_first` mode to generate a structured, polished, and citation-gated manuscript.
3. **Stylistic Polishing & Proofreading (Phase 2 — Calligraph Sensei):** Install [Calligraph Sensei](https://github.com/kshanxs/calligraph-sensei) to apply advanced perplexity, sentence length variation (burstiness), and diagnostic writing audits under Academic-Formal mode, or run a conservative Proofreading pass to clean up spelling and syntax errors while leaving the academic tone and all citations completely intact.

---

## ⚠️ Limitations & Responsibility

*   **No Plagiarism Measurement:** TrueDraft improves originality through structural and stylistic process discipline. It does **not** check external databases or guarantee a similarity score of `0%`.
*   **Source Verification:** Always review citations listed in `audit_log.md` and resolve any outstanding `[CITE: ...]` placeholders before submitting your work.
*   **Institutional Alignment:** Ensure that your use of TrueDraft aligns with the academic integrity policy of your specific institution.

---

## 📝 Changelog

See [CHANGELOG.md](./CHANGELOG.md) for details on all versions and releases.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

Copyright © 2026 [Shubhanshu Shukla](https://github.com/kshanxs). All rights reserved.

---

<p align="center">
  <sub>MIT License &nbsp;•&nbsp; Permission to Modify & Distribute &nbsp;•&nbsp; No Warranty or Liability</sub><br>
  <sub>Designed for academic integrity and clarity of expression.</sub>
</p>
