# Deliverable: Full Word Report

## When to produce

Produce a full Word report when the user requests:
- "Full report"
- "Word document"
- "Deliverable"
- "Save this analysis"
- "Something I can reference later"
- "Printable"

Do NOT produce a Word report by default. Default output is conversational. The report is on-request.

## Structure

The report has 7 sections in this order:

### 1. Title block

- **Title**: Election name, date, year (e.g., "June 2, 2026 Primary Election")
- **Subtitle**: "Full Ballot Analysis and Recommendations"
- **Metadata**: Voter name (if given), location, party registration, framework used
- Format: Centered, clean, professional

### 2. Executive summary

A single table with four columns:

| Race / Measure | Pick | Confidence | One-line rationale |

One row per ballot item. This is what a busy voter reads first.

### 3. Framework section

- Short intro explaining what frameworks are and why this one was chosen
- **Character gate subsection**: conditions, and list of candidates who failed with reasons
- **Weighted criteria subsection**: table of criteria, weights, and definitions
- **What the framework does NOT weight**: explicit list (party label, identity, electability, etc.)

This section proves the analysis is not hidden endorsement.

### 4. Statewide races

Section per race. For each:
- Heading with office name
- 1-paragraph context (what the office does, stakes, current holder/field dynamics)
- Scoring table (if race has 3+ candidates)
- Pick with bolded name and party
- Rationale in 2-4 sentences
- Runner-up note (why not this person)

### 5. Federal and state legislative races

Same per-race structure. Include:
- US House (district-specific)
- State Senate (only if district is up this cycle — flag if not)
- State Assembly

### 6. County races

Same per-race structure for each county office on the ballot:
- Board of Supervisors (if the voter's district is up)
- Assessor, Auditor-Controller, Clerk-Recorder, Treasurer-Tax Collector, Superintendent of Schools
- Superior Court Judge (if contested and researched)

### 7. Ballot measures

Heading per measure. For each:
- Heading with measure letter/number and short name
- Context paragraph (what it does, history if renewal)
- Pick with bolded YES/NO
- Rationale with 4-6 bullet points covering specific tests applied
- Reservation paragraph if Medium confidence

### 8. Framework caveats and confidence levels

Three subsections:
1. **Where the framework is a value judgment**: honest acknowledgment that the framework itself is a choice
2. **Where confidence is lowest**: 2-3 picks where you'd push back on yourself
3. **Where the framework is strongest**: 3-4 picks where evidence and framework align with highest confidence

### 9. Next steps

Short closing with:
- Election date and key dates (registration deadline, VBM, drop-off)
- Suggestion to cross-check against sample ballot when it arrives
- Note that picks reflect evidence as of analysis date

## Format requirements

**Page**: US Letter (8.5 x 11), 1-inch margins (can reduce to 0.75 inch if content demands)

**Fonts**:
- Body: Arial, 11pt
- H1: Arial Bold, 18pt, dark navy (#1F3A5F)
- H2: Arial Bold, 14pt, steel blue (#2E4F6B)
- H3: Arial Bold, 12pt, gray (#444444)

**Tables**:
- Header row: navy background, white text, bold
- Alternating row shading (#F5F5F5 on even rows)
- Borders: 1px light gray (#CCCCCC)
- Cell padding: 100 top/bottom, 140 left/right (DXA)

**Page breaks**: Before Framework section, Statewide section, Federal section, County section, Measures section, Caveats section.

**Length target**: 6-10 pages for a typical primary ballot. Shorter if the ballot has few races; longer only if measures require detailed analysis.

## Implementation

Use the `docx` skill to produce the file. Key constraints:

1. **Always explicitly set page size** — docx-js defaults to A4; use US Letter (12240 x 15840 DXA)
2. **Validate before presenting** — run `python scripts/office/validate.py doc.docx` after creation
3. **Use `ShadingType.CLEAR`** for table backgrounds, never SOLID
4. **Set both `columnWidths` on table AND `width` on each cell** — tables render incorrectly without both
5. **Paraphrase everything** — no copyright violations from ballot language or news sources

See the June 2026 primary report (`examples/2026-primary-ca10.md`) for a full worked example.

## Quality checklist before presenting

- [ ] Title block has voter name, location, framework used
- [ ] Exec summary table covers every ballot item with pick + confidence + one-liner
- [ ] Framework section explicit about character gate + weighted criteria
- [ ] Every race has: context, pick, rationale, runner-up note
- [ ] Every measure has: what-it-does, pick, bullet rationale
- [ ] Caveats section names 2-3 low-confidence picks honestly
- [ ] Next-steps section has correct dates
- [ ] Document validates cleanly
- [ ] No hallucinated candidates or vote records
- [ ] Every surprising claim has a citable source
- [ ] Paraphrasing discipline maintained (no 15+ word quotes)
