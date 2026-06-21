# Learning Mode

## Purpose

When learning mode is active, the skill explains every decision it makes as it writes — what technique was applied, why, and what the original would have looked like. This turns the writing process into a teaching tool rather than just an output generator.

**Load this file only when the user activates learning mode.**

---

## How to Activate

Learning mode is triggered when the user says:
- "explain as you go"
- "learning mode"
- "show me why you're making these changes"
- "teach me, don't just write it"

---

## What to Explain at Each Stage

### After Plan/Outline Phase
> 💡 *Learning note: I broke the topic into [N] subtopics in the outline instead of treating it as one. This prevents shallow coverage and ensures each concept gets its own explanation, example, and implication.*

### After Each Introduction Paragraph
> 💡 *Learning note: I opened with [analytical context / problem framing / historical perspective] instead of a definition. Definitions are the most commonly flagged introduction type — they appear in thousands of academic texts and are easy for similarity engines to match. A contextual opener is almost always unique.*

### After Each Body Paragraph
> 💡 *Learning note: This paragraph used [sentence types used]. I avoided writing three analytical sentences in a row because repetitive structure is one of the patterns AI detectors use. The causal sentence ("As X grows, Y...") and the comparative sentence ("Unlike A, B...") break that pattern.*

### After Rewrite (Originality/Style/Humanise) Pass
> 💡 *Learning note: I applied a readability and style randomization pass. Here's what changed and why:*
> - **Cut filler:** "[It is important to note that X]" → "[X]" — filler phrases add length but not meaning; removing them tightens the sentence without losing information.
> - **Activated voice:** "[It was found that results varied]" → "[Results varied]" — active constructions are easier to read and sound more confident.
> - **Analogy added:** I added an analogy to explain [concept] — abstract ideas land better when grounded in something familiar.
> *The goal was readability for a human reader and sentence variation to break monotonous rhythms.*

### After Final Audit
> 💡 *Learning note: Everything passed the audit check. Here's what makes this version originality-first: [2–3 bullet points summarising the key choices made].*

---

## Learning Mode Writing Style

When learning mode is on:
- Wrap every technique-related note in a `💡 Learning note:` block
- Place notes *after* the relevant section, not inline
- Keep notes concise — 2–4 sentences maximum per note
- Never interrupt the flow of the actual content with learning notes
- At the end, offer: *"Want me to give you 3 practice exercises on [topic] so you can apply these techniques yourself?"*
