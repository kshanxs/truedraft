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

### After Research Phase
> 💡 *Learning note: I broke the topic into [N] subtopics instead of treating it as one. This prevents shallow coverage and ensures each concept gets its own explanation, example, and implication.*

### After Each Introduction Paragraph
> 💡 *Learning note: I opened with [analytical context / problem framing / historical perspective] instead of a definition. Definitions are the most commonly flagged introduction type — they appear in thousands of academic texts and are easy for similarity engines to match. A contextual opener is almost always unique.*

### After Each Body Paragraph
> 💡 *Learning note: This paragraph used [sentence types used]. I avoided writing three analytical sentences in a row because repetitive structure is one of the patterns AI detectors use. The causal sentence ("As X grows, Y...") and the comparative sentence ("Unlike A, B...") break that pattern.*

### After Style Pass
> 💡 *Learning note: I changed [N] sentences. Here's one example:*
> - **Before:** "[original sentence]"
> - **After:** "[revised sentence]"
> - **Why:** [explanation of what was flagged and what technique fixed it]

### After Plagiarism Guard
> 💡 *Learning note: [N] sections were flagged. The highest-risk phrase was "[phrase]" — this matches a common pattern in academic databases. I rewrote it by [technique used]. The rewritten version says the same thing but breaks the n-gram sequence.*

### After Final Review
> 💡 *Learning note: Everything passed. Here's what makes this version lower-risk than a typical AI output: [2–3 bullet points summarising the key choices made].*

---

## Learning Mode Writing Style

When learning mode is on:
- Wrap every technique-related note in a `💡 Learning note:` block
- Place notes *after* the relevant section, not inline
- Keep notes concise — 2–4 sentences maximum per note
- Never interrupt the flow of the actual content with learning notes
- At the end, offer: *"Want me to give you 3 practice exercises on [topic] so you can apply these techniques yourself?"*


