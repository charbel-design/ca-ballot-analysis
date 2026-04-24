# Deliverable: One-Sheet PDF

## When to produce

Produce a one-sheet PDF when the user requests:
- "One-sheet" / "cheat sheet" / "one-pager"
- "Printable PDF"
- "Something I can take to the polls"
- "Wallet card" / "pocket reference"
- "Ballot summary"

Often produced alongside the full report, but can stand alone for users who only want a quick reference.

## Hard constraint

**Must fit on one US Letter page.** If content exceeds one page, reduce content — do not spill to a second page. A one-sheet that's two sheets defeats the purpose.

## Structure

Top-to-bottom:

### 1. Header (2 lines, compact)

- Title: "[ELECTION DATE] PRIMARY/GENERAL BALLOT" — all caps, dark navy, centered, 16pt bold
- Subtitle: "[Voter location] · [Party registration] · Framework: [name]" — 10pt, gray, centered

### 2. Statewide offices table

Columns: Race (1.8"), Pick (1.9"), Why (3.6")
Rows: one per statewide office on ballot
Header row: navy background, white text, bold
Data rows: alternating light gray shading (#F5F5F5 on even rows), candidate names bold

### 3. Federal and state legislative table

Same format as statewide.
Include races that are NOT on the ballot with italic "— Not on ballot —" to prevent confusion.

### 4. County races table

Same format. Only include offices actually on the ballot for this county.
"Abstain" recommendations shown in gray.

### 5. Ballot measures table

Columns: Measure (2.8"), Vote (0.9"), Why (3.6")
"YES" in green (#2D7A3E), "NO" in red (#B33030), both bold
Shorter column for vote allows the why to be full-detail

### 6. Bottom info block (two columns)

**Left column (2.5"): KEY DATES**
- Ballot mail date
- Registration deadline
- Vote center opening (if vote center county)
- Election Day
- VBM ballot cutoffs

**Right column (4.8"): CONFIDENCE NOTES**
- HIGH-CONFIDENCE PICKS: list 3-5 picks where framework speaks clearly
- LOWER-CONFIDENCE PICKS: list 2-3 where user might want to push back

Light gray background (#F5F5F5), thin border, internal column divider.

### 7. Footer (1 line, 8pt gray)

Short note:
"Full reasoning in companion Word document. Character gate disqualified: [list names with offices]."

## Format requirements

**Page**: US Letter, 0.5" left/right margins, 0.4" top/bottom margins (tight to fit content)

**Colors**:
- NAVY header fill: #1F3A5F
- STEEL section headings: #2E4F6B
- MUTED text: #666666
- LIGHT row alternate: #F5F5F5
- BORDER: #CCCCCC
- NO red: #B33030
- YES green: #2D7A3E
- ABSTAIN gray: #888888

**Fonts**:
- Helvetica throughout (widely supported)
- Title: 16pt bold
- Section headings: 11pt bold
- Table headers: 9pt bold white
- Table body: 9pt, candidate picks bold
- Footer: 8pt

**Table styling**:
- Top/bottom cell padding: 4pt
- Left/right cell padding: 6pt
- Header alignment: left (except Vote column in measures, centered)
- Grid: 0.5pt BORDER color

## Implementation

Use the `pdf` skill with ReportLab. Key constraints:

1. **Never use Unicode subscripts/superscripts/bullets in direct canvas draws** — fonts don't include these glyphs
2. **Use &middot; and &mdash; HTML entities** instead of Unicode characters in Paragraph strings for better rendering
3. **Test rendering before presenting** — convert PDF to PNG with pdf2image and visually verify the one-page constraint
4. **Flush build**: call `doc.build(story)` and handle exceptions gracefully

See June 2026 primary example in `examples/2026-primary-ca10.md` for full code.

## Content density calibration

Sample ballot sizes (rough):
- Presidential primary with many offices and 5 propositions: tight fit, aggressive trimming of "Why" column
- Regular primary with typical ballot: comfortable fit
- General election with full proposition list (8+): may require squeezing; prioritize top/bottom key info

If content genuinely won't fit, pre-negotiate with user:
- Would they prefer: denser tables (smaller font), fewer races (skip uncontested/unopposed), or split into front/back of a single sheet (still "one sheet" physically)?

## Quality checklist before presenting

- [ ] Fits on exactly one US Letter page (verify by rendering to image)
- [ ] Every ballot item from the full report appears in the one-sheet
- [ ] YES/NO measure colors render correctly
- [ ] Abstain recommendations visually distinct (gray)
- [ ] Key dates section accurate for this election
- [ ] Confidence notes reflect the actual picks
- [ ] Footer names all character-gate disqualifications
- [ ] No text truncation or overflow
- [ ] Printer-friendly (no heavy color backgrounds, readable at 100% zoom)
- [ ] Works in both color and black-and-white printing
