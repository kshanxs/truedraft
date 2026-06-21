# Rewrite Stage (Originality & Readability)

## Purpose

This stage reduces similarity risks, applies sentence variety, and enhances readability without fabricating safety scores. It combines originality-focused edits, style randomization (burstiness and perplexity simulation), and Humanise readability passes to ensure the text sounds natural, diverse, and human.

---

## Modes & Triggers

- `generated_draft`: automatically runs as part of the main pipeline.
- `draft_rewrite`: standalone run when a user pastes a draft and asks to improve it, reduce formulaic patterns, or make it sound less like AI.
- `humanise`: standalone run when a user pastes text and says "Humanise this" or "Make this easier to read."

---

## Required Work

1. **Read the Full Text:** Understand the context and argument before changing any phrasing.
2. **Determine Readability Intensity:**
   - **Level 1 (Light):** Cut filler phrases, activate key passive sentences, improve basic flow.
   - **Level 2 (Standard - Default):** Apply Level 1 + add 1-2 helpful analogies for abstract concepts, vary sentence rhythm, replace overused AI/academic transition words.
   - **Level 3 (Conversational):** Apply Level 2 + allow contractions, use a warmer, more engaging tone throughout, use short punchy sentences.
3. **Apply Style Randomization:**
   - Ensure every paragraph contains at least two distinct sentence types (Analytical, Causal, Comparative, Hypothetical, Observational) from `references/style_randomization.md`.
   - Ensure **Length Variation (Burstiness)**: Every paragraph must feature a mix of very short sentences (<10 words) and long, clause-rich sentences (>20 words).
   - Inject **Perplexity**: Replace 1-2 predictable academic words per paragraph with less expected but accurate synonyms.
4. **Remove Originality Targets:** Cut cliché academic intros (e.g. "In today's world..."), stock examples, robotic transitions, and repeating sentence openers.
5. **Preserve Integrity:** Keep all factual claims, technical terms, citations, and placeholders (`[CITE: ...]` or `[UNVERIFIED: ...]`) exactly intact.

---

## Output Contract

Return the revised text followed by a concrete change summary:

```text
Rewrite Level: Standard (2) | Light (1) | Conversational (3)

Changes Made:
| Paragraph | Original Sentence | Revised Sentence | Reason / Technique |
|---|---|---|---|
| 1 | "It is important to note that neural networks..." | "Neural networks..." | Cut filler opener (readability) |
| 2 | "A model learns training data too specifically." | "Overfitting is like memorizing exam answers..." | Analogy for abstract concept (Level 2) |
| 3 | "...very fast. It worked." | "...very fast. It worked." | Burstiness variation (sentence length) |

Revised Draft:
[Insert the fully revised draft here]
```
