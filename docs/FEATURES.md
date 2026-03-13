# assignment-writer — Full Features

## Writing Features

| Feature | Description |
|---|---|
| **Assignment Forge** | Onboarding conversation: topic, course, level, word count, citations, deadline, rubric — all skippable |
| **6-Stage Pipeline** | Research → Write → Style → Code → Guard → Review — each stage lazily loaded |
| **Analytical Intro Engine** | Never generates definition openers. Uses: analytical context / problem framing / historical perspective |
| **Semantic Expansion** | Every concept: explain → example → implication. Increases semantic distance from source material |
| **Style Randomization** | Rotates 5 sentence types (analytical / causal / comparative / hypothetical / observational) per paragraph |
| **N-gram Disruption** | Actively breaks 4+ word sequences matching common academic phrasing |
| **Concept-first Explanation** | Explains concepts before naming them — inverse of textbook order, harder to fingerprint |
| **Section-only Mode** | Write just intro / conclusion / body paragraph / methodology — chain multiple requests |
| **Rewrite Mode** | Paste any text (AI or human) → guard scores each section LOW/MEDIUM/HIGH → rewrites only flagged parts |
| **Multi-discipline** | STEM, humanities, social science, law, business — style calibrated per field |

---

## Anti-Plagiarism Engine

| Technique | What it counters |
|---|---|
| Analytical introductions | N-gram matches in definitions (biggest similarity spike) |
| Semantic expansion | Cosine similarity — expands conceptual distance from source |
| Style randomization | Stylometric fingerprinting / repetitive AI patterns |
| N-gram disruption | Winnowing / k-gram hashing detectors |
| Structural originality | JPlag / MOSS token comparison |
| Dual-mode guard | Works on both generated and pasted external text |

---

## Coding Features

| Feature | Description |
|---|---|
| **Algorithm Diversity Rule** | Never defaults to the most common textbook solution |
| **Modular Design** | Helper functions break token-sequence similarity |
| **Descriptive Naming** | No `x`, `arr`, `temp` — uses `search_index`, `node_depth`, etc. |
| **Approach Explanation** | Algorithm choice + reasoning always written before code |
| **Complexity Analysis** | Time + space complexity with explanation |
| **Possible Improvements** | Trade-offs and alternative approaches noted |
| **Comment Reasoning Rule** | Comments explain *why*, never just restate the code |

---

## Citation Support

| Style | In-text | Reference list |
|---|---|---|
| APA 7th | Author-date | Alphabetical, hanging indent, DOI |
| MLA 9th | Author-page | Works Cited, title case |
| Harvard | Author-date | Single quotes for articles, italics for books |
| IEEE | Numbered `[1]` | Ordered by appearance, abbreviated journal names |

→ Full formatting rules: `references/citation_guide.md`

---

## Rubric Awareness

| Feature | Description |
|---|---|
| **Rubric Parsing** | Extracts weighted dimensions from pasted marking criteria |
| **Mark-band Targeting** | Identifies highest-weight category and writes to earn top-band marks in it |
| **Required Section Detection** | Flags structural requirements (IMRAD, Literature Review, Case Study) |
| **Critical Analysis Injection** | Adds evaluation moves per paragraph to satisfy analysis criteria |

→ Full rubric strategy: `references/rubric_guide.md`

---

## Memory Bank

| File | Purpose |
|---|---|
| `assignment-memory/topic.md` | Assignment requirements, rubric, key concepts |
| `assignment-memory/style_profile.md` | Tone, citation style, sentence preferences |
| `assignment-memory/risk_log.md` | Plagiarism guard audit trail — every flagged phrase and rewrite |

---

## Output Modes

| Mode | Trigger |
|---|---|
| Full pipeline | `"Write my assignment on [topic]"` |
| Coding only | `"Do my [language] homework"` |
| Rewrite / de-risk | `"Check/fix/reduce plagiarism in: [paste]"` |
| Section only | `"Write just the [intro/conclusion/body] for..."` |
| Style pass | `"Make this sound less like AI"` |
| Citation pass | `"Add APA citations"` |
| Rubric-driven | `"Here's my rubric: [paste]"` |

---

## What the Examples Cover

| File | Demonstrates |
|---|---|
| `examples/essay_example.md` | STEM essay (Machine Learning) — semantic expansion, analytical intro |
| `examples/coding_example.md` | Algorithm (Two Sum) — hash approach, descriptive naming, complexity |
| `examples/humanities_example.md` | Social science (Political Polarisation) — contested framing, evaluative language, counterargument engagement |
