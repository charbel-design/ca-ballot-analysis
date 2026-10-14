# Changelog

## October 14, 2026 — values-first weights

The fairness-not-equity defaults changed. The previous entry on this date left them at 20, 35, 15, 15, 10, and 5, with policy quality multiplied by feasibility. That product, plus a heavy delivery weight, ranked candidates by whether they could win and whether they had held office. The owner rejected it. The composites in the entry below are the historical record of that version. They are not the current scores.

### New defaults

Seven additive weights, summing to 100:

| Criterion | Weight |
| --- | --- |
| Policy alignment | 45 |
| Five-year effects | 15 |
| Concentrated benefit | 12 |
| Individualism | 10 |
| Delivery of framework-aligned results | 8 |
| Feasibility and electability | 7 |
| Baseline competence | 3 |

Policy alignment is the dominant criterion. Feasibility is a separate score. It is never a multiplier. Delivery counts a result this framework would call a success, not years in office. Competence dropped from 5 to 3 so literacy cannot override policy fit. Concentrated benefit moved from 15 to 12 to make the seven weights sum to 100. The character gate, the sourcing rule, the confidence labels in `scoring/confidence-levels.md`, and the ±10 sensitivity check are unchanged. Seven criteria produce 14 shifts. Delivery (8), feasibility (7), and competence (3) clip to 0 on a −10 shift.

The rationale is in `frameworks/fairness-not-equity.md`. The method is in `scoring/weighted-criteria.md`. `SKILL.md` and `PROMPT-VERSION.md` state the same weights.

### Rescored races

Same sources standard as the earlier pass: a claim without a link is not in the file. Campaign statements are scored as statements. They are not treated as audited results, which is why no candidate pick below is High.

November 3, 2026 general, `examples/2026-general-san-ramon.md`:

- Governor: Hilton 61.05, Becerra 48.50, gap 12.55, Medium. The leader is unchanged in all 14 shifts.
- Attorney general: Gates 58.35, Bonta 55.05, gap 3.30, Low. Feasibility at +10 flips the leader.
- U.S. House District 10: Frese 55.60, DeSaulnier 45.85, gap 9.75, Medium. The leader is unchanged in all 14 shifts.

June 2, 2026 primary governor field in `examples/2026-primary-ca10.md`. The inherited scores from the first draft were withdrawn rather than reweighted.

- Mahan 71.00, Hilton 61.05, Villaraigosa 60.50, Becerra 48.50. Gap 9.95, Medium. Mahan stays first in all 14 shifts. Hilton leads Villaraigosa by 0.55, and some shifts swap those two for second.

Proposition picks were not rescored. They use the measure tests, not these weights.

## October 14, 2026

Corrected the skill's scoring and screening rules, and added a worked example for the November 3, 2026 general election in San Ramon. The weights in this entry were 20, 35, 15, 15, 10, and 5, with a feasibility multiplier. The entry above replaces those weights and those composites.

### Rules

- Confidence labels and abstention now live only in `scoring/confidence-levels.md`. `SKILL.md`, `PROMPT-VERSION.md`, the fairness framework, the measure guide, and the scoring worksheet point there instead of keeping their own versions.
- High on a scored candidate race requires a recomputed gap of 15 or more and a sensitivity check that does not change the leader. A row with no score does not get a label. Abstain is not a confidence level.
- The character gate is generic. It no longer uses examples built around particular 2026 candidates. Screening is not an accusation: cite the record or do not disqualify.
- Voters can replace the six weights with any set that sums to 100. The method is in `scoring/weighted-criteria.md`, `SKILL.md`, and `PROMPT-VERSION.md`. After scoring, each criterion is shifted by 10 points in each direction, clipped at 0, and renormalized. The write-up says whether the leader changes.
- A Word report and a one-sheet PDF are optional. They are produced only when the voter asks. The verification checklist (weights sum to 100, composites recompute, High candidate picks clear a 15-point gap, every factual claim is sourced) is in `scoring/weighted-criteria.md` and repeated in the skill and the paste-in prompt.

### June 2, 2026 primary example

`examples/2026-primary-ca10.md` is corrected, not deleted.

- The governor composites now match the stated scores: Mahan 73.00, Villaraigosa 65.55, Hilton 49.55. The gap is 7.45, so the label is Medium. Mahan stays first in all 12 weight shifts.
- Picks that had a confidence label and no score are withdrawn.
- Disqualifications of Chad Bianco, Tom Steyer, Katherine Piccinini, and Angela Griffiths are withdrawn. Bianco's ballot seizure and the later Supreme Court ruling, and Steyer's published prosecution proposal, are cited as notes. They are not gate failures under the corrected rule. The other conduct claims were not re-verified and are not repeated.
- ZIP 94582 is in State Senate District 9, not District 7. Senate elections are in even-numbered years. Even-numbered districts are on the 2026 ballot; odd-numbered districts are next up in 2028.
- Contra Costa's district attorney and sheriff are next on the ballot at the 2028 presidential primary. That is Elections Code section 1300, and the county's own June 2026 candidate guide. The old shorthand was easy to misread, and the statute's charter-county exception is now stated. The underlying calendar claim for this county was right.

### November 3, 2026 general example

`examples/2026-general-san-ramon.md` is new. Last verified October 14, 2026. Same voter, same framework, default weights.

Scored races, all Medium, none flipped by the sensitivity check:

- Governor: Becerra 50.00, Hilton 41.65, gap 8.35.
- Attorney general: Bonta 51.25, Gates 40.45, gap 10.80.
- U.S. House District 10: DeSaulnier 46.375, Frese 40.60, gap 5.775. Cutting the delivery weight narrows that gap to under 2 points without changing the leader.

Propositions 41 and 42 are YES at High under the measure-test rule. The other propositions and Measure RTM are Medium or Low. Judicial retention is an abstention. Local and several statewide races are listed and not scored.

### Facts this pass could not verify

- The street address that would place a 94582 household in a San Ramon council district, a school trustee area, or a services-district division.
- Whether any June county fiscal race continued to November. Those offices are absent from the November contest list that was reviewed, and the June canvass was not re-read.
- A San Ramon city measure. None appeared in the county measure list as reviewed. The sample ballot is still the check.
- Donor-level finance for the scored candidates, other than one receipts total for DeSaulnier.
- Orange County canvass results for Michael Gates's city-attorney elections. His Ballotpedia biography states them. This file does not treat that biography as a canvass.
- The full statutory text of each proposition, beyond the official summary and analyst estimate.
- Opinions or discipline records for the justices on the retention ballot.
- The original primary example's biographical claims about Mahan, Villaraigosa, and Hilton, and its Measure B and urban-limit-line details. They were removed rather than repeated.
- A later correction, if any, of the Secretary of State's August 27, 2026 sentence that put odd-numbered Senate seats on the November ballot. The certified candidate list published that day enumerates the even-numbered districts. This repo follows the list.
