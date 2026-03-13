# Style Randomization Framework

## Purpose

Prevent repetitive sentence patterns that both plagiarism detectors and AI detectors flag. This framework defines the five sentence types that should be rotated across every paragraph, and introduces perplexity/burstiness simulation to reduce AI detection scores.

---

## The Five Sentence Types

### 1. Analytical
Explains reasoning, causality, or mechanism.
> "The performance of a neural network scales with both the quantity and diversity of its training data."

### 2. Causal
Shows a cause-and-effect relationship.
> "As the number of model parameters increases, the risk of overfitting to the training set also grows proportionally."

### 3. Comparative
Contrasts two approaches, systems, or concepts.
> "Unlike traditional rule-based classifiers, which rely on hand-crafted conditions, neural approaches derive their own decision boundaries from data."

### 4. Hypothetical
Explores a conditional or possible scenario.
> "Were training data perfectly balanced across all classes, the resulting model would likely produce more equitable predictions."

### 5. Observational
Describes a pattern, trend, or finding.
> "Empirical studies consistently demonstrate that ensemble methods outperform single-model approaches in classification benchmarks."

---

## Rotation Rule

Every paragraph must include **at least two different sentence types**.

**Bad (monotone):**
> "X is a process that does Y. X also does Z. X is important because of W."
> *(All analytical — flagged by pattern detectors)*

**Good (varied):**
> "X operates by doing Y [analytical]. As Y scales, Z becomes more prominent [causal]. Unlike traditional approaches, X does not require W [comparative]."

---

## Perplexity & Burstiness Simulation

AI detectors (GPTZero, Turnitin AI) assess two statistical properties:

- **Perplexity** — how unpredictable the word choices are. AI text tends to be low-perplexity (predictable, common words in expected positions).
- **Burstiness** — how much sentence length varies. Human writing is highly bursty — a very long sentence followed by a short one. AI text is monotonously medium-length.

### Rule 1 — Length Variation (Burstiness)
Every paragraph must have at least one sentence under 10 words AND one over 20 words.

**Bad (flat rhythm):**
> "Machine learning systems process large amounts of data efficiently. They identify patterns across many training examples. These patterns are then generalised to new inputs."
> *(All ~10 words — low burstiness)*

**Good (bursty):**
> "Machine learning works by pattern recognition. Rather than encoding explicit rules, these systems derive their own decision logic from exposure to thousands of labelled examples — a process that makes them extraordinarily adaptable but equally dependent on the quality and diversity of the data they were trained on. This matters."
> *(Short. Very long. Short again.)*

### Rule 2 — Occasional Low-Frequency Vocabulary (Perplexity)
Occasionally replace a common academic word with a less predictable but accurate synonym:
- "important" → "consequential", "non-trivial", "pivotal"
- "use" → "leverage", "deploy", "employ"
- "shows" → "illustrates", "underscores", "surfaces"
- "problem" → "constraint", "pathology", "tension"
- "different" → "distinct", "divergent", "dissimilar"

Apply to 1–2 words per paragraph — not every sentence (that creates its own detectable pattern).

### Rule 3 — Mid-Sentence Pivots
Insert a pivot or qualification mid-sentence to break predictable clause structure:
> "The algorithm, though efficient in most cases, degrades significantly when input distributions shift — a limitation that standard benchmarks rarely capture."

---

## Practical Application

When reviewing a paragraph:
1. Label each sentence by type
2. If 3+ consecutive sentences share a type → rewrite one using a different type
3. Check sentence length variation — if lengths are similar, break the longest into two or combine the shortest with its neighbour
4. Replace 1–2 common words with less-predictable synonyms
5. Prefer embedded transitions — avoid "Furthermore", "Moreover", "In addition"
