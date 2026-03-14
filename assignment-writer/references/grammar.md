# Grammar & Punctuation Reference

## Purpose

A grammar and punctuation audit checklist applied during the final Review stage. Every rule below must be actively checked — not assumed. Fix inline before confirming.

---

## 1. Subject-Verb Agreement

The verb must agree in number with its subject — not with a nearby noun.

> ❌ "The performance of the algorithms were tested."
> ✅ "The performance of the algorithms was tested."

Watch especially for:
- Collective nouns: "The data **is**..." not "The data are..." (in most academic contexts)
- Inverted sentences: "There **are** several reasons..." not "There is several reasons..."
- Compound subjects joined by "or/nor": agree with the nearer subject

---

## 2. Comma Rules

### After introductory elements (mandatory)
> ✅ "In the context of machine learning, overfitting is a central concern."
> ❌ "In the context of machine learning overfitting is a central concern."

### Before coordinating conjunctions in compound sentences
When two independent clauses are joined by and/but/or/so, place a comma before the conjunction:
> ✅ "The model trained quickly, but it failed to generalise."
> ❌ "The model trained quickly but it failed to generalise."

### Oxford comma (use consistently)
In a list of three or more items, include a comma before the final "and" or "or":
> ✅ "...searching, insertion, and deletion..."
> ❌ "...searching, insertion and deletion..."

### No comma before "that" (restrictive clauses)
> ✅ "The algorithm that performs best on sparse data uses hashing."
> ❌ "The algorithm, that performs best on sparse data, uses hashing."

### Comma before "which" (non-restrictive clauses — adds extra info)
> ✅ "The algorithm, which was proposed in 2017, uses hashing."

---

## 3. Hyphenation

### Compound modifiers before a noun — hyphenate
> ✅ "a well-suited approach", "left-to-right ordering", "real-world applications"
> ❌ "a well suited approach", "real world applications"

### After an adverb ending in -ly — no hyphen
> ✅ "a widely accepted method"
> ❌ "a widely-accepted method"

### Compound nouns — check convention:
- "inorder" (CS term, no hyphen — standard in academic literature)
- "in-order" is also acceptable but pick one and use it consistently

---

## 4. Em Dash, En Dash, and Hyphen

| Symbol | Use | Example |
|---|---|---|
| Hyphen `-` | Joins compound words | `well-suited`, `left-to-right` |
| En dash `–` | Ranges (numbers, dates) | `2019–2023`, `pages 12–15` |
| Em dash `—` | Interruption, parenthetical emphasis | `The model — after ten epochs — converged.` |

Do not use a hyphen where an em dash is intended.
Do not use an em dash where an en dash (range) is intended.

Em dashes do not need spaces around them in standard academic style:
> ✅ "The root — and only the root — has no parent."
> ❌ "The root - and only the root - has no parent."

---

## 5. Apostrophes

- Possessive singular: `node's value`, `the tree's depth`
- Possessive plural (noun ends in s): `the nodes' references` (apostrophe after the s)
- Contractions: `it's` = "it is"; `its` = possessive (no apostrophe)
- No apostrophe in possessive pronouns: `its`, `theirs`, `ours`

> ❌ "It's structure is recursive." → ✅ "Its structure is recursive."

---

## 6. Parallelism in Lists

All items in a list must share the same grammatical form.

> ❌ "The pipeline includes researching the topic, to write a draft, and style variation is applied."
> ✅ "The pipeline includes researching the topic, writing a draft, and applying style variation."

This applies to bulleted lists, numbered lists, and inline series.

---

## 7. Sentence Fragments and Run-ons

### Fragments (intentional ones are fine — rogue ones are not)
A fragment is acceptable for stylistic effect when it follows a long sentence:
> ✅ "The algorithm is efficient in time and space, robust to noise, and generalises well across domains. Mostly."

Rogue fragments — sentences that lose the subject or verb accidentally — must be fixed:
> ❌ "Which is why the traversal order matters." (no subject)
> ✅ "This is why traversal order matters."

### Run-on sentences
Two independent clauses joined with only a comma = comma splice. Fix with a semicolon, coordinating conjunction, or period:
> ❌ "The model overfits, it memorised the training data."
> ✅ "The model overfits; it has memorised the training data."
> ✅ "The model overfits because it has memorised the training data."

---

## 8. Academic-Specific Rules

- **Avoid contractions** in formal academic writing unless Humanise Level 3 is active
- **Spell out numbers** below 10 in prose, unless they are measurements: "three components" not "3 components" — but "45°C", "O(log n)"
- **Consistent tense** — present tense for established facts and descriptions of algorithms; past tense for experimental results
- **"However" punctuation** — when used as a sentence adverb, bracket with commas or place at the start:
  > ✅ "The result, however, was inconclusive."
  > ✅ "However, the result was inconclusive."
  > ❌ "The result was however inconclusive."
- **"Which" vs "that"** — use "that" for restrictive clauses (defines the noun), "which" with a comma for non-restrictive clauses (adds information)

---

## Quick-Check Protocol

When reviewing a passage, scan in this order:
1. Subject-verb agreement on every sentence
2. Comma after every introductory clause
3. Compound modifiers — hyphenated?
4. Em/en dash used correctly?
5. Every list item in the same grammatical form?
6. Apostrophes on possessives and contractions correct?
7. No comma splices or rogue fragments?
