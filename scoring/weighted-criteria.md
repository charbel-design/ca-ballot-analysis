# Weighted Criteria Scoring

## Purpose

This file guides how to produce composite scores when a framework specifies weighted criteria. Goal: rigor without false precision.

## Core principle: prose over fake numbers

The temptation is to produce precise-looking numbers (Candidate X scores 73 on criterion 2). Resist. Prose reasoning with explicit scores at the end beats number-first scoring every time.

The risk of fake precision: users over-weight a close score gap (74 vs. 71) that is actually indistinguishable given the underlying evidence quality.

## Workflow

For each candidate who passed the character gate, for each criterion in the framework:

### Step 1: Write the reasoning first

Before assigning a number, write 2-4 sentences covering:
- Key evidence from research
- How the evidence maps to this specific criterion
- Where the evidence is strong vs. thin
- What the evidence points toward (high/mid/low on this criterion)

### Step 2: Assign a score in one of three bands

Don't pretend to distinguish 73 from 78. Use three bands:

- **High (70-100)**: Strong evidence this candidate scores well on this criterion
- **Medium (40-69)**: Mixed evidence, or evidence points in the right direction but is thin
- **Low (0-39)**: Evidence suggests the candidate scores poorly or the evidence gap is so large that a high score can't be justified

Within a band, 70/80/90 can be used to express gradation, but don't sweat the difference between 72 and 74.

### Step 3: Apply weights

Multiply each criterion score by its weight (as a decimal). Sum the results. That's the composite score. Keep the unrounded sum. A rounded headline that no longer matches the arithmetic is not the score.

The fairness-not-equity defaults, in order, are policy alignment 45, five-year effects 15, concentrated benefit 12, individualism 10, delivery of framework-aligned results 8, feasibility 7, and competence 3.

Example, using Steve Hilton's November 2026 governor scores from `examples/2026-general-san-ramon.md`:

- Policy alignment (45%): 70 → 31.50
- Five-year effects (15%): 65 → 9.75
- Concentrated benefit (12%): 60 → 7.20
- Individualism (10%): 70 → 7.00
- Delivery (8%): 30 → 2.40
- Feasibility (7%): 20 → 1.40
- Competence (3%): 60 → 1.80

**Composite: 31.50 + 9.75 + 7.20 + 7.00 + 2.40 + 1.40 + 1.80 = 61.05**

## Feasibility is not a multiplier

Policy alignment and feasibility are separate scores. Add them after weighting. Do not compute `(policy × feasibility) / 100`.

An earlier version of this file did that, at 35%. In a long Democratic trifecta the product put every Republican statewide agenda near the bottom regardless of policy fit. That rule is withdrawn. The rationale is in `frameworks/fairness-not-equity.md`.

A different framework may still define a multiplicative criterion. If it does, it has to say so in its own file, apply the product inside that one criterion, and then apply the weight. Fairness-not-equity does not.

The worked cases are `examples/2026-general-san-ramon.md` and `examples/2026-primary-ca10.md`.

## When candidate scores are close

Apply `scoring/confidence-levels.md`. Do not invent a second threshold here.

- A gap under 5 points is Low confidence, and the write-up names both candidates.
- A gap of 2 points or less is a reason to abstain rather than pretend the framework decided the race.

## Comparing candidates side-by-side

For races with 3+ serious candidates, produce a scoring table:

```markdown
| Candidate | Policy (45%) | 5-year (15%) | Concentrated (12%) | Indiv (10%) | Delivery (8%) | Feasibility (7%) | Competence (3%) | Composite |
|-----------|--------------|--------------|--------------------|-------------|---------------|------------------|-----------------|-----------|
| Hilton | 70 | 65 | 60 | 70 | 30 | 20 | 60 | 61.05 |
| Becerra | 50 | 45 | 45 | 40 | 30 | 70 | 85 | 48.50 |
```

The arithmetic for that table is in `examples/2026-general-san-ramon.md`. A table like this invites the user to push back on specific cells.

## Transparency requirements

Every composite score must be accompanied by:

1. **The criterion-level scores** (so the user can see where the candidate won and lost)
2. **The reasoning** (so the user can challenge specific judgments)
3. **Confidence level**, using only `scoring/confidence-levels.md`
4. **Key sources** (so the user can verify)

Do NOT produce a ranked list without the underlying scoring. That's just endorsement with extra steps.

## Common scoring mistakes

### Mistake 1: Scoring on likeability or vibes

If you catch yourself scoring a candidate high or low without being able to point to specific evidence tied to specific criteria, stop. Either find evidence or adjust the score.

### Mistake 2: Double-counting

If a candidate's union backing is relevant to both concentrated-benefit alignment and feasibility, it can appear in both, but don't penalize twice for the same fact. Apply it once, to the criterion where it most clearly belongs. Do not also treat years in office as delivery.

### Mistake 3: Anchoring to the first candidate

If you score the first candidate at 80 and the second at 75, you may be anchoring rather than scoring on absolute criteria. Score each candidate independently against the rubric, not relative to the others.

### Mistake 4: Letting the pick drive the scoring

If you have an intuition about who the right pick is, don't back-fill scores to get there. Do the scoring honestly; if the numbers disagree with your intuition, examine why (the framework may be telling you something you missed).

### Mistake 5: False precision

Don't score 73 when your confidence is ±15. Use band-level scoring (High/Medium/Low or 25/50/75 anchors) unless you have evidence to support finer distinctions.

## Edge cases

### Incumbent facing no serious challenger

Don't force a comparison. Say "incumbent scores X on the framework; no challenger presents a credible alternative on the framework's criteria." Recommend retain if X is adequate, or recommend protest vote if X is poor.

### Single candidate on ballot (unopposed)

No scoring needed. Note for the voter.

### All candidates fail the character gate

Very rare but possible. Recommend abstention with explicit reasoning.

### Information too thin to score

If research produces almost no useful information about a candidate (common in minor local races), don't fabricate a score. Output: "Insufficient information to score this candidate against the framework. Recommend reviewing candidate statement and endorsements, or abstaining."

## Output format for scored races

```markdown
### [Office]

**Candidates**: [List with party/designation]

**Character gate**: [Who passed, who failed, with one-line reasons]

**Scoring**:
[Scoring table if 3+ candidates, or side-by-side prose if 2 candidates]

**Pick**: [Candidate name] — [Confidence level from scoring/confidence-levels.md, or Abstain / Not scored with no label]

**Why**:
[3-5 sentences summarizing the decisive criteria]

**If the framework is wrong**:
[1-2 sentences on what could change the pick — useful for voter pushback]
```

The "if the framework is wrong" section is critical: it invites the voter to identify where they disagree with the framework, rather than where they disagree with a specific pick.

## Adjustable weights

The fairness-not-equity defaults are 45, 15, 12, 10, 8, 7, and 3, in the order listed in the framework. They stay the defaults. A voter may replace them.

To use different weights:

1. Write one percentage per criterion, in the same order as the framework.
2. Check that they sum to 100. If they do not, stop and fix them before scoring.
3. Recompute every composite with the new weights. Do not reuse a ranking from the default weights.
4. Assign confidence again under `scoring/confidence-levels.md`.
5. Say, in the output, that the weights are the voter's and not the framework default.

Do not multiply policy by feasibility. Changing the weights does not create a multiplier, and it does not remove the rule against one.

## Sensitivity check

Run this once for every scored candidate race, after the default (or voter-chosen) composites are done.

Starting weights: `W = [45, 15, 12, 10, 8, 7, 3]` unless the voter substituted a set that sums to 100. Use that set as `W` instead. The order is policy, five-year, concentrated benefit, individualism, delivery, feasibility, competence.

For each criterion, and for a shift of +10 and of −10:

1. Copy `W`.
2. Add the shift to that one criterion. If the result would be negative, set it to 0 and note that the shift was clipped. On the defaults, delivery (8), feasibility (7), and competence (3) all clip on −10.
3. Renormalize so the weights sum to 100: `new_i = trial_i / sum(trial) × 100`.
4. Recompute every candidate's composite with `new`.
5. Record whether the leader changed.

Seven criteria produce 14 shifts. A framework with a different count produces two shifts per criterion.

Report, for that race, either "the leader is the same in all 14 shifts" or which shifts change the leader, with the new composites. A shift that changes the leader blocks a High label. See `scoring/confidence-levels.md`.

Worked check, June 2026 primary, from `examples/2026-primary-ca10.md`. Scores are policy, five-year, concentrated, individualism, delivery, feasibility, competence.

| Candidate | Scores | Composite |
| --- | --- | --- |
| Mahan | 80, 75, 60, 65, 45, 60, 75 | 71.00 |
| Hilton | 70, 65, 60, 70, 30, 20, 60 | 61.05 |
| Villaraigosa | 65, 70, 45, 60, 30, 65, 80 | 60.50 |
| Becerra | 50, 45, 45, 40, 30, 70, 85 | 48.50 |

Mahan remains first in all 14 shifts. The gap to Hilton is 9.95, so the label is Medium, not High. Hilton leads Villaraigosa by 0.55 on the defaults. Some shifts swap those two. That does not change the leader.

## Verification checklist

Run this before treating an analysis as finished. The same list is what `SKILL.md` and `PROMPT-VERSION.md` require.

- [ ] The weights sum to 100.
- [ ] Each composite equals the weighted sum of the stated criterion scores. Show the arithmetic.
- [ ] Policy alignment and feasibility were scored separately and added. Feasibility was not multiplied into policy.
- [ ] Delivery was scored on framework-aligned results, not on years in office.
- [ ] Every High candidate pick has a gap of 15 or more, strong evidence, and does not flip in the sensitivity check.
- [ ] Every High measure pick has three aligned tests and no serious test the other way, per `scoring/confidence-levels.md`.
- [ ] Unscored rows and abstentions have no High/Medium/Low label.
- [ ] Every factual claim about a candidate or measure has an inline source link.
- [ ] The worked example, if any, shows a last-verified date.
- [ ] The sensitivity check is reported for each scored race.
