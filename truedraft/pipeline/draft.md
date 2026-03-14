# Draft Stage

## Purpose

Write the first full draft from the approved plan and outline. The draft should feel reasoned, specific, and less templated, while staying honest about unsupported claims.

---

## Inputs

- approved outline
- claim plan
- discipline guidance, if needed
- user notes, if present
- citation policy if any source support is needed

## Core Rules

1. Follow the approved outline exactly unless the user asks for changes
2. Start with an analytical introduction, not a dictionary definition
3. Build paragraphs around reasoning:
   - explain
   - example
   - implication
4. Prefer the user's notes and framing whenever they are available
5. If a claim needs a source and none is provided, leave an inline placeholder
6. Do not create a bibliography unless the user supplied sources

## Prohibited Moves

- definition openers
- generic filler such as "In today's world" or "This essay will discuss"
- stock analogies from the plan's avoid-list
- invented citations or fake reference entries
- paragraphs that merely restate the prompt

## Output Contract

Return:

- the draft itself
- any inline `[CITE: ...]` or `[UNVERIFIED: ...]` markers that remain
- a short note naming the active mode: `open_generation` or `notes_first`
