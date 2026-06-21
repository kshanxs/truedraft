# Citation Policy

## Purpose

Define how `TrueDraft` handles citations and source gaps.

---

## Mandatory Rules

1. **Never Invent Citations:** Never fabricate bibliography entries, authors, paper titles, or publication years.
2. **Search-First Attempt:** If the user requires citations but has not provided the raw sources:
   - Check if the host agent has web search or Google Scholar tools (e.g. `search_web` or similar).
   - If available, execute search queries to find real, peer-reviewed papers or authoritative sources for the claims in the draft.
   - Extract actual bibliographic data (authors, year, title, journal/publisher, URL/DOI).
3. **Verified-Fallback:** If search tools are unavailable, rate-limited, fail to find high-quality authoritative matches, or return ambiguous results:
   - Use explicit inline placeholders (see format below).
   - **Do not** write a plausible-looking but fabricated reference entry.
4. **User Verification & Logging:** Log all successfully web-retrieved citations in `project-memory/audit_log.md` with the search query used, retrieved source metadata, and direct URLs for the user's validation.

---

## Placeholder Format

When a source cannot be found or verified, insert one of:

- `[CITE: source needed for claim about: "<brief context of claim>"]`
- `[UNVERIFIED: details need source confirmation: "<claim details>"]`

---

## Formatting Rule

When formatting real sources (either supplied by the user or found via web search), follow the requested style using [citation_guide.md](./citation_guide.md):

- APA 7th Edition
- MLA 9th Edition
- Harvard
- IEEE

---

## Delivery Rule

If any placeholders remain in the draft, the final audit stage must clearly warn the user:
- The draft contains unresolved placeholders and is **not submission-ready**.
- The user must verify the web-searched sources listed in `audit_log.md` and replace any remaining placeholders with their own real sources before submission.
