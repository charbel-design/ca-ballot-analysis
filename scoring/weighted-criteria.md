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

Multiply each criterion score by its weight (as a decimal). Sum the results. That's the composite score.

Example:
- Delivery track record (20%): 80 → 80 × 0.20 = 16
- Policy quality × feasibility (35%): 90 × 60 / 100 = 54 → 54 × 0.35 = 18.9
- Second-order effects (15%): 70 → 70 × 0.15 = 10.5
- Concentrated-benefit alignment (15%): 85 → 85 × 0.15 = 12.75
- Individualism/rule-equality (10%): 75 → 75 × 0.10 = 7.5
- Baseline competence (5%): 95 → 95 × 0.05 = 4.75

**Composite: 16 + 18.9 + 10.5 + 12.75 + 7.5 + 4.75 = 70.4**

Round to whole number: 70.

## Special handling: multiplicative criteria

Some frameworks use multiplicative criteria (e.g., "policy quality × feasibility"). Apply the multiplication within that criterion BEFORE applying the weight.

Formula: `(sub_score_1 × sub_score_2) / 100 = criterion_score`

Example: Policy quality 90, Feasibility 30 → (90 × 30) / 100 = 27. That 27 is the criterion score, which then gets weighted.

The June 2026 primary example is the worked case. Hilton's policy-times-feasibility score is 18 and Mahan's is 60. After the weights below are applied, the corrected composites are Mahan 73.00, Villaraigosa 65.55, and Hilton 49.55. See `examples/2026-primary-ca10.md`.

## When candidate scores are close

Apply `scoring/confidence-levels.md`. Do not invent a second threshold here.

- A gap under 5 points is Low confidence, and the write-up names both candidates.
- A gap of 2 points or less is a reason to abstain rather than pretend the framework decided the race.

## Comparing candidates side-by-side

For races with 3+ serious candidates, produce a scoring table:

```markdown
| Candidate | Delivery (20%) | Pol×Feas (35%) | 5-year (15%) | Concentrated (15%) | Indiv (10%) | Competence (5%) | Composite |
|-----------|---------------|----------------|--------------|-------------------|-------------|-----------------|-----------|
| Candidate A | 85 | 75 | 70 | 80 | 70 | 90 | 77 |
| Candidate B | 70 | 60 | 75 | 85 | 80 | 85 | 72 |
| Candidate C | 60 | 45 | 60 | 70 | 65 | 80 | 59 |
```

Makes comparisons transparent and invites the user to push back on specific cells.

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

If a candidate's union backing is relevant to both "concentrated-benefit alignment" and "feasibility" (because unions help them pass things), it can appear in both — but don't penalize twice for the same fact. Apply it once to the criterion where it most clearly belongs.

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

The fairness-not-equity defaults are 20, 35, 15, 15, 10, and 5. They stay the defaults. A voter may replace them.

To use different weights:

1. Write six percentages, one per criterion, in the same order as the framework.
2. Check that they sum to 100. If they do not, stop and fix them before scoring.
3. Recompute every composite with the new weights. Do not reuse a ranking from the default weights.
4. Assign confidence again under `scoring/confidence-levels.md`.
5. Say, in the output, that the weights are the voter's and not the framework default.

Policy quality times feasibility is still computed inside that criterion before the weight is applied. Changing the weights does not turn the multiplier into an addition.

## Sensitivity check

Run this once for every scored candidate race, after the default (or voter-chosen) composites are done.

Starting weights: `W = [20, 35, 15, 15, 10, 5]` unless the voter substituted a set that sums to 100. Use that set as `W` instead.

For each criterion, and for a shift of +10 and of −10:

1. Copy `W`.
2. Add the shift to that one criterion. If the result would be negative, set it to 0 and note that the shift was clipped. The 5-point competence weight clips on −10.
3. Renormalize so the six weights sum to 100: `new_i = trial_i / sum(trial) × 100`.
4. Recompute every candidate's composite with `new`.
5. Record whether the leader changed.

Report, for that race, either "the leader is the same in all 12 shifts" or which shifts change the leader, with the new composites. A shift that changes the leader blocks a High label. See `scoring/confidence-levels.md`.

Worked check, June 2026 primary governor scores from `examples/2026-primary-ca10.md` (delivery, policy×feasibility, five-year, concentrated, individualism, competence):

| Candidate | Scores | Composite |
| --- | --- | --- |
| Mahan | 85, 60, 80, 75, 75, 85 | 73.00 |
| Villaraigosa | 85, 53, 65, 60, 70, 85 | 65.55 |
| Hilton | 40, 18, 75, 80, 85, 70 | 49.55 |

Mahan remains first in all 12 shifts. The gap to Villaraigosa is 7.45, so the label is Medium, not High.

## Verification checklist

Run this before treating an analysis as finished. The same list is what `SKILL.md` and `PROMPT-VERSION.md` require.

- [ ] The six weights sum to 100.
- [ ] Each composite equals the weighted sum of the stated criterion scores. Show the arithmetic.
- [ ] Policy×feasibility was multiplied, then weighted. It was not added as a seventh score.
- [ ] Every High candidate pick has a gap of 15 or more and does not flip in the sensitivity check.
- [ ] Every High measure pick has three aligned tests and no serious test the other way, per `scoring/confidence-levels.md`.
- [ ] Unscored rows and abstentions have no High/Medium/Low label.
- [ ] Every factual claim about a candidate or measure has an inline source link.
- [ ] The worked example, if any, shows a last-verified date.
- [ ] The sensitivity check is reported for each scored race.
