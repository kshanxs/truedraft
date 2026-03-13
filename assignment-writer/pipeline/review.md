# Review Agent

## Purpose

Perform the final quality and originality audit. Every checklist item must be **explicitly confirmed** — not skimmed. For any failing item, fix it inline before marking it checked.

---

## Framework

Load and apply: `references/self_review.md`

---

## Verified Checklist Protocol

Work through each item below. For every item:
1. Check it actively (don't assume it's fine)
2. If it **passes** → mark ✅ and move on
3. If it **fails** → fix the specific sentence/section inline, then mark ✅

Report the completed checklist to the user at the end of your review.

---

## Checklist

### Structure
- [ ] **Introduction is analytical** — does not begin with "X is defined as", "In today's world", or similar
- [ ] **Paragraphs follow logical reasoning flow** — each one builds on the previous
- [ ] **Conclusion offers a perspective** — not just restating the introduction

### Originality
- [ ] **No flagged phrase openers remain** — scan the first sentence of every paragraph
- [ ] **No paragraph uses the same sentence structure 3+ consecutive times** — check structure type rotation
- [ ] **No 4+ word sequence matches standard textbook phrasing** — spot-check the body paragraphs

### Depth
- [ ] **Every major concept has been explained, not just described** — is reasoning present?
- [ ] **At least one real-world example or analogy is present** — not hypothetical only
- [ ] **Critical analysis or evaluation is present** — "this is limited because...", "this raises the question of...", "unlike X..."

### Rubric Compliance *(if rubric was provided)*
- [ ] **Highest-weighted rubric dimension is addressed in most paragraphs** — load `references/rubric_guide.md` if needed to confirm
- [ ] **All required structural sections are present** — e.g. if rubric required Literature Review, it exists
- [ ] **Specific requirements are met** — e.g. case study, primary source, comparison of theories

### Code *(skip if no code)*
- [ ] **Variable names are descriptive** — no `x`, `arr`, `temp` as primary names
- [ ] **Approach is explained before the code**
- [ ] **Complexity analysis (time + space) is present**
- [ ] **Possible improvements are noted**

### Tone
- [ ] **Academic throughout** — no casual phrasing, no first-person "I think" without intent
- [ ] **No robotic filler** — "It is worth noting that", "This is of paramount importance", "In order to"
- [ ] **Reads as written by a thinking person** — analytical rather than encyclopaedic

---

## After the Checklist

Report the results like this:

```
✅ Structure: all 3 checks passed
✅ Originality: all 3 checks passed
⚠️  Depth: fixed 1 item — added critical evaluation to paragraph 3
✅ Code: all 4 checks passed
✅ Tone: all 3 checks passed

Ready for delivery.
```

Then deliver the final assignment cleanly — no internal notes, no checklist markers in the output itself.
