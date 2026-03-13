# Self Review Framework

## Purpose

An 8-stage structured self-review that the Review Agent uses to audit the assignment before final delivery. This functions as an internal quality and anti-similarity pass.

---

## Stage 1 — Structural Review

Check the overall flow:

- Does the introduction begin with analytical context (not a definition)?
- Do paragraphs build logically on each other?
- Does the conclusion offer a genuine perspective rather than just restating the introduction?

**If:** A paragraph resembles a textbook structure (definition → theory → summary), rewrite it with analytical reasoning.

---

## Stage 2 — Sentence Similarity Scan

For each paragraph:

1. Identify sentences longer than 20 words
2. Ask: Does this sound like something you'd read in a textbook or Wikipedia?
3. If yes:
   - Change the grammatical structure
   - Replace common phrases
   - Convert from passive to active voice (or vice versa)
4. Remove any sequence of 4+ consecutive words that commonly appears in academic writing

---

## Stage 3 — Style Diversity Check

Verify sentence type variety using `frameworks/style_randomization.md`.

At least **three** of these must appear across the assignment:
- [ ] Analytical
- [ ] Causal
- [ ] Comparative
- [ ] Observational
- [ ] Hypothetical

If any paragraph uses the same sentence pattern 3+ times, rewrite one of those sentences.

---

## Stage 4 — Concept Expansion Check

For each major concept discussed, confirm:

- [ ] The concept is **explained** (not just named)
- [ ] An **example** or scenario is provided
- [ ] The **implication** or significance is discussed

If only explanation exists without example → add one. If only example exists without analysis → add the "so what."

---

## Stage 5 — Coding Assignment Review

*(Skip if no code is present)*

Verify:
- [ ] Variable names are descriptive (no `x`, `temp`, `arr`)
- [ ] At least one helper function or structural variation is present
- [ ] Comments explain reasoning, not mechanics
- [ ] Algorithm approach is explicitly stated before the code
- [ ] Complexity analysis is included after the code

If code resembles a common textbook example:
- Introduce helper functions
- Alter the iteration style
- Rename variables descriptively

---

## Stage 6 — Algorithm Diversity Verification

*(Skip if no code is present)*

Confirm the chosen solution avoids the most common implementation of this problem.

If a more structurally distinct approach exists (recursion, hash map, DP), note it in the "Possible Improvements" section at minimum.

---

## Stage 7 — Tone and Clarity Check

Ensure:
- [ ] Academic tone is maintained throughout
- [ ] No overly complex or unnatural phrasing
- [ ] The text reads as if written by a thinking person, not a retrieval system
- [ ] No robotic filler phrases ("It is worth noting that...", "This is of great importance...")

---

## Stage 8 — Final Refinement Pass

Complete a final read-through:

- [ ] Sentence structures are varied
- [ ] No phrases repeat frequently
- [ ] Explanations are conceptual and sound natural
- [ ] Code structure (if present) appears original and readable

**If any item is unchecked**, fix it before marking the assignment complete.
