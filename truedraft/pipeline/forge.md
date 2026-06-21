# TrueDraft Onboarding — The Forge

## Purpose

The onboarding conversation for a new draft or project. Gathers context so the TrueDraft pipeline writes with academic precision rather than guessing. Runs once per project. Skip entirely if the user has provided enough context upfront.

**Minimum to start:** topic + course level. All other questions are skippable.

---

## How to Run the Forge

Ask **one question at a time**. If the user says "skip", "doesn't matter", or doesn't answer, note it as unknown and move on. Never repeat skipped questions.

If the user provides a rubric at any point, immediately load `references/rubric_guide.md` and run the rubric mapping step before continuing.

---

## Question Sequence

### Q1 — Topic
> "What's the assignment topic or question?"

*(Skip if already given in the original message.)*

---

### Q2 — Course & Level
> "What subject or course is this for? And is it high school, undergraduate, or postgraduate level?"

Options (offer these):
- High School
- Undergraduate (Year 1–2)
- Undergraduate (Year 3–4 / Honours)
- Postgraduate / Masters
- PhD

---

### Q3 — Word Count / Length
> "How long does it need to be? (word count, page count, or short / medium / long)"

---

### Q4 — Citation Style
> "Does your institution require a specific citation style?"

Options:
- APA 7th (default if unsure)
- MLA 9th
- Harvard
- IEEE
- Chicago
- None / not required

---

### Q5 — Institution
> "Which university or institution is this for? (Optional — helps calibrate formatting and any known style conventions)"

If provided, note it in `project-memory/brief.md`. Adjust if the institution is known to have specific requirements (e.g. Oxford = Chicago footnotes, MIT = IEEE).

---

### Q6 — Rubric or Marking Criteria
> "Do you have a rubric or marking criteria? If yes, paste it here — I'll calibrate the writing to target top-band marks."

**If rubric is provided:**
1. Load `references/rubric_guide.md`
2. Extract each graded dimension and its weight
3. Identify the top-band descriptor for each
4. Note all required structural sections (e.g. Literature Review, Case Study)
5. Pass this rubric map to the Plan Agent as priority context

**If not provided:** use the default university weighting from `references/rubric_guide.md`:
- 40% critical analysis / argument
- 30% content accuracy and depth
- 20% structure and clarity
- 10% referencing

---

### Q7 — Specific Instructions
> "Any specific instructions from your professor? (You can paste them directly)"

*(Free text — paste guidelines, rubric excerpts, formatting rules.)*

---

### Q8 — Deadline Urgency
> "How much time do you have? This helps me calibrate depth."

Options:
- A few hours → focused, efficient version
- A day or two → well-developed
- A week+ → thorough, research-backed

---

### Q9 — Do you have a draft or outline already?
> "Do you have any notes, bullet points, or a rough outline you'd like me to build from? If yes, paste them here."

**If yes:** Store in `project-memory/brief.md` under a "Student Notes" section. The Plan Agent will use these as the skeleton instead of generating structure from scratch. Tell the user:
> *"Great — I'll build the project around your ideas rather than starting fresh. Your reasoning, my structure."*

**If no:** Proceed normally.

---

### Q10 — Learning Mode
> "Do you want me to explain my writing decisions inline — what techniques I'm using and why? (Helps you understand and improve your own writing.)"

**If yes:** Load `references/learning_mode.md` and keep it active for the entire session. Add *(Learning mode ON)* to the memory bank.

**If no / skip:** Proceed silently without explanations.

---

## After the Forge

Once questions are done (or skipped):

1. **Summarise** what was collected:
   > "Got it — writing a [word count] [level] assignment on [topic] for [course], [citation style] citations. [If rubric: Calibrating to your marking criteria.] [If institution: Formatting to [institution] conventions.] [If draft/notes: Building from your outline.] [If learning mode: Explaining decisions as I go.] Let me start planning now."

2. **Detect discipline** from the course/subject field:
   - Data Science / Computer Science / ML / AI / Software Engineering / Statistics → `references/disciplines/data_science_cs.md`
   - Science / Engineering / Medicine (general) → `references/disciplines/science.md`
   - Literature / History / Philosophy / Arts → `references/disciplines/humanities.md`
   - Law / Legal Studies → `references/disciplines/law.md`
   - Commerce / Business Studies / introductory Economics / Accounting → `references/disciplines/commerce.md`
   - Business / Management / Economics (MBA/corporate level) → `references/disciplines/business.md`
   - Unclear → use `references/academic_rules.md` defaults

3. **Initialise project-memory** — if a project directory exists or the user wants to save context:
   - Copy `assets/templates/brief_template.md` → `project-memory/brief.md`
   - Copy `assets/templates/style_profile_template.md` → `project-memory/style_profile.md`
   - Fill all `{{TOKEN}}` placeholders with the forge answers (e.g. `{{TOPIC}}`, `{{COURSE}}`, `{{LEVEL}}`, `{{WORD_COUNT}}`, `{{DEADLINE}}`, `{{CITATION_STYLE}}`)
   - If student notes/outline were provided, add them to brief.md under `{{KEY_CONCEPTS}}`

4. **Begin the Plan stage immediately** — don't wait for the user to say "go."

---

## Resuming a Previous Assignment

If `project-memory/brief.md` and `project-memory/style_profile.md` already exist:
1. Read both files silently
2. Do NOT re-run the forge
3. Say: *"Welcome back — continuing your [topic] project. [Brief summary of where things stand.]"*
4. Ask: *"Do you want to pick up where we left off, or is there something specific you want to work on?"*
