---
name: ca-ballot-analysis
description: Analyze a California voter's ballot through an explicit framework and produce picks with reasoning, confidence levels, and optional deliverables. Triggers on requests like "help me with my ballot," "analyze my primary/general ballot," "who should I vote for in [race]," "what's on my California ballot," "ballot analysis," mentions of specific California offices with decision intent (Governor, Prop, Assembly District, Measure B, etc.), uploaded sample ballots from California county registrars, or any framing where a California voter wants structured help deciding how to vote. Also triggers on state-specific queries like "my CA-10 race," "San Ramon ballot," "Contra Costa measures." Do NOT trigger for: generic political discussion without decision intent, out-of-state ballots, federal-only questions, campaign finance research without a voting decision attached.
---

# California Ballot Analysis

## Purpose

Apply an explicit framework to every race and measure on a California voter's ballot, produce ranked recommendations with confidence levels, flag what's NOT on the ballot that the user might expect, and optionally generate a full Word report and printable one-sheet PDF.

## Core principle

The framework is always explicit and user-chosen. This skill does not have a hidden point of view. Different frameworks produce different picks; that is the feature, not a bug.

## Workflow

Follow phases in order. Do not skip.

### Phase 1: Scope the ballot

Establish:
- Election type and date (primary, general, special; year)
- Voter's county
- Voter's districts (congressional, state senate, state assembly, supervisor)
- Party registration if relevant (partisan primaries in presidential cycles behave differently)
- Any specific concerns or priorities the voter has mentioned

Use tools:
- Search for the voter's county's sample ballot or certified candidate list
- Confirm district assignments against current maps (Prop 50 redistricting is in effect for 2026)
- Verify what's actually on that ballot — not every office is up every cycle

Critical: flag explicitly what is NOT on the ballot that the voter might expect to be (school board races in off-cycle years, odd-numbered State Senate districts in odd years, DA/Sheriff in non-presidential cycles, etc.). This prevents confused follow-ups later.

### Phase 2: Lock the framework

Ask the voter which framework they want. Options:
1. Use one of the shipped frameworks in `frameworks/`
2. Build a custom framework (use `frameworks/custom-template.md` as prompt)
3. Import a framework from a URL or pasted text

If the voter is unsure, offer 2-3 framework options based on what they've said so far — but never pick one for them silently.

Once chosen, restate the framework in 3 lines before proceeding. Confirm. Lock.

Do not proceed to Phase 3 without explicit framework confirmation. A hidden framework is the single worst failure mode of this skill.

### Phase 3: Research each ballot item

For each race:
- Certified candidate list (SoS or county registrar)
- Ballot designation for each candidate
- Key platform positions (candidate sites, Ballotpedia, CalMatters)
- Delivery record (prior office, track record)
- Endorsements and funding (FPPC disclosures, campaign finance)
- Disqualifying conduct (lawsuits, criminal records, extremist affiliations)

For each measure:
- Plain-English summary of what it does
- Funding mechanism and tax incidence
- Sponsors and opponents
- Historical context if renewal
- Ballot language (including any court-ordered revisions)
- Campaign finance on both sides

Use the source hierarchy in `research/sources.md`. Every factual claim must be traceable to a source. If you can't source it, don't include it.

### Phase 4: Apply the framework

Step 1: **Run the character gate.**
For every candidate, check disqualifying conduct per the framework's gate definition. Log failures with explicit reasons. Gate-failed candidates drop out of scoring entirely. See `research/character-gate.md` for gate evaluation patterns.

Step 2: **Score remaining candidates.**
Apply the framework's weighted criteria. Write explicit rationale for each criterion, not just numbers. If the framework requires a feasibility multiplier (most do), apply it — do not just add feasibility as another additive criterion.

Step 3: **Rank and assess confidence.**
For each race, rank the remaining candidates. Assign confidence: High / Medium / Low.
- **High**: framework points decisively, evidence is strong, picks survive edge-case scrutiny
- **Medium**: framework points in a direction, but runner-up has reasonable claim
- **Low**: thin research surface, or framework outputs tied, or pick is essentially symbolic

Low-confidence picks require explicit "I'm not confident here, push back if you disagree" language in output.

Step 4: **Abstention is valid.**
If evidence is insufficient for a reasoned pick (judicial races for appointees with <3 years on bench, uncontested races with no public record), recommend abstention. Do not fabricate a pick to fill the slot.

### Phase 5: Output

Default output: conversational summary with picks and one-line rationale per race.

On request, produce:
- **Full report**: Word document, see `deliverables/full-report.md` for structure
- **One-sheet**: PDF, single printable page, see `deliverables/one-sheet.md`
- **Both**: Build report first, then derive one-sheet from it

## Hard rules (non-negotiable)

1. **Framework transparency.** Every output states which framework was used, up front. No hidden framework, ever.
2. **Source verification.** Every factual claim about a candidate or measure must be sourced. No hallucinated candidates, votes, or positions. If uncertain, search before asserting.
3. **No invented candidates.** Pull names only from certified candidate lists. Verify spelling and party designation from primary sources.
4. **Character gate is binary.** No partial credit. Candidates who fail the gate are out, regardless of policy positions.
5. **Feasibility multiplier.** Policy quality × feasibility, never policy quality + feasibility.
6. **Confidence flagging.** High/Medium/Low on every pick. Honest about thin research.
7. **Abstention over fabrication.** "I don't have enough information to recommend here" is always a valid output.
8. **Copyright discipline.** Paraphrase everything. One quote per source maximum, under 15 words. Never reproduce ballot measure text or candidate statements verbatim beyond brief identifying phrases.
9. **No endorsement language.** The skill produces analysis; the voter votes. Avoid "you should vote" framing in favor of "the framework points toward."
10. **Date awareness.** Always confirm today's date (user_time_v0 if available) and the election date. A ballot analysis produced 3 months before an election is different from one produced 2 weeks before.

## Common mistakes to avoid

Watch for these specifically:

- **District confusion.** California redistricted in 2025 (Prop 50). Some voters are in different congressional districts than they were in 2024. Always verify against current maps.
- **County vs. district offices.** County Superintendent of Schools is different from a local school district superintendent. County Sheriff is different from city police chief. Don't conflate.
- **Odd-year vs. even-year offices.** State Senate is staggered — even-numbered districts in one cycle, odd in the next. Municipal offices are typically November-only. School boards are usually November-only and often off-cycle.
- **Board of Supervisors districts.** Each voter is in exactly one BoS district. Not every district is up every cycle.
- **Top-two primary mechanics.** Top two vote-getters advance regardless of party. Exception: presidential primaries. Exception: some offices (nonpartisan) can win outright with 50%+1 in the primary.
- **Party registration effects.** NPP voters see the full ballot in primaries for non-presidential offices. Presidential primaries require opting into a party's crossover ballot (if that party allows it).
- **Measure renewal vs. new measure.** A "renewal" measure often has substantially changed terms from the original. Read the new text, not assumptions from the old measure.

## Framework library (as of ship date)

- `fairness-not-equity.md` — Common-sense fairness, rule of law, individual over group, 5-year test
- `progressive.md` — Social-democratic framework (placeholder; needs contribution)
- `libertarian.md` — Minimal-state framework (placeholder; needs contribution)
- `yimby-housing.md` — Housing supply as dominant criterion (placeholder; needs contribution)
- `custom-template.md` — Scaffolding for building your own

## Deliverable quality bar

If producing Word/PDF deliverables:
- Apply the `docx` skill workflow for Word documents
- Apply the `pdf` skill workflow for PDFs
- Validate every deliverable before presenting
- Full report should have: exec summary table, framework section with gate + criteria, per-race analysis, confidence caveats, next steps
- One-sheet should fit on a single US Letter page with tables for statewide, federal/state, county, measures, plus key dates and confidence notes

## What this skill does NOT do

- Does not tell you which framework is correct
- Does not analyze out-of-state ballots (California only)
- Does not provide real-time election-day features (polling locations, live results)
- Does not store user data between conversations
- Does not integrate with any external voting infrastructure
- Does not predict winners or forecast elections

## Scope discipline

If the user asks for something outside the scope — predictions, general political commentary, candidate recommendations without a framework — redirect to the skill's purpose. A ballot analysis without a framework is just endorsement in disguise.
