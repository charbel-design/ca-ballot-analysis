# Changelog

## October 16, 2026 — card stack swipe

A committed swipe keeps the top card moving off the screen, with a slight tilt, until it is gone. The card behind rises into that spot. Back brings the previous card in from the left. A short swipe springs back. Next and Back use the same motion.

## October 16, 2026 — flip cards fill the phone

Flip through now uses the space under the top bar. Each card has the reason on it. Measures lead with the proposition number and a large Yes or No. Local no-picks list the candidate names and say to check the sample ballot. Back sits beside Next, and a thin bar shows how far you are in the stack.

## October 16, 2026 — drawn controls

Once a device has opened the private link, the hero keeps a My ballot | Public switch on screen. The public page does not show it. Theme, Adjust, and Close are drawn controls. The sliders use a custom track, thumb, and value. Offices, Measures, and Local slide an indicator, and the list fades and slides with transform and opacity. Sheets still spring open. Card edges are a hairline so the list does not repaint a large shadow while scrolling.

## October 15, 2026 — public-share pass

The phone guide now sends no referrer, keeps a tight content-security policy, and only opens outside links with `noopener` and `noreferrer`. The private link is still a hash, not a login. Countdown days use Pacific time. Muted text is darker so it meets contrast AA, and the sheets trap keyboard focus. The city district lookup points at the city’s current map. A preview image is included for messages.

## October 15, 2026 — a ballot you can flip through

The phone guide now opens on a full-screen date, then matchup cards instead of a settings list. Measures show the proposition number and a Yes or No. A tally fills as the page scrolls. Flip through is an optional card stack. The weights, both views, and the private link are unchanged.

## October 15, 2026 — sheets scroll on the phone

The Adjust values sheet and the race sheets now fill the screen and scroll on their own, with a sticky title bar, a total along the bottom, and a fade when more content sits below. The page behind the sheet stays put. Rows sit in grouped cards with a monogram.

## October 15, 2026 — phone guide

`guide/2026-general-san-ramon.html` is now a single self-contained page for a phone. The public URL starts every weight equal and recomputes candidate picks from those sliders. Slider changes stay in that browser. A private hash on the same file opens the saved weights (policy 45, five-year effects 15, concentrated benefit 12, individualism 10, delivery 8, feasibility 7, competence 3), shows those picks, and remembers the view on the device. Measures still use the measure tests. The two-page sheet is unchanged.

## October 14, 2026 — two-page ballot sheet

`examples/2026-general-san-ramon-sheet.md` and `guide/ballot-sheet-nov-2026-san-ramon.pdf` are now a two-page sheet of the current picks. The sentences are plain language. Scores appear only as the small pair of composites under each scored race. Picks are unchanged from the deep pass below. The longer guide, with weight sliders, remains `guide/2026-general-san-ramon.html`.

## October 14, 2026 — deep pass and voter guide

The November 3, 2026 San Ramon example was rescored from sourced platforms, not by nudging neutral cells. Policy alignment stays at 45. Feasibility stays additive at 7. A gap of 15 or more is Medium, not High, when the evidence is a campaign summary or a news report rather than a statute or a case file. That rule is now explicit in `scoring/confidence-levels.md`.

Current candidate picks, with composites and the gap:

- Governor: Hilton 62.45, Becerra 42.15, gap 20.30, Medium. Was Hilton 61.05 to 48.50, Medium. The leader is unchanged. The wider gap is the CalMatters tax and rate-freeze contrast. It is still not High.
- Lieutenant governor: Romero 58.00, Ma 43.35, gap 14.65, Medium. Newly scored.
- Secretary of state: Wagner 57.35, Weber 49.00, gap 8.35, Medium. Newly scored.
- Controller: Morgan 60.25, Cohen 51.65, gap 8.60, Medium. Newly scored.
- Treasurer: Hawks 51.25, Kounalakis 47.40, gap 3.85, Low. Newly scored. Feasibility at +10 flips it.
- Attorney general: Bonta 62.65, Gates 43.15, gap 19.50, Medium. This reverses the prior pick, Gates 58.35 to Bonta 55.05, Low. CalMatters reports that Bonta enforced housing laws that make cities allow housing and that Gates fought those laws as Huntington Beach city attorney. The label stays Medium because the case files were not read.
- Insurance commissioner: Allen 48.00, Kim 37.55, gap 10.45, Medium. Newly scored.
- Board of Equalization, District 2: Pimentel 62.30, Lieber 45.85, gap 16.45, Medium. Newly scored. Not High. Both platforms are campaign material.
- U.S. House, District 10: Frese 55.60, DeSaulnier 43.00, gap 12.60, Medium. Was Frese 55.60 to 45.85. DeSaulnier's policy cell moved from 45 to 40.
- Assembly District 16: Bauer-Kahan 50.70, Rubay 42.50, gap 8.20, Medium. Newly scored. The source is San Ramon Patch, thinner than CalMatters.
- Superintendent of public instruction: Shaw 56.90, Barrera 42.35, gap 14.55, Medium. Newly scored.

Proposition direction is unchanged. Patch's note that Proposition 40 is labor-sponsored, and that Proposition 44 is union-backed, is cited and does not raise either label. Judicial retention and the local candidate contests stay unscored. ZIP 94582 is still not one council district, trustee area, or services-district division.

The June primary file was not recomputed. It still uses the earlier Hilton and Becerra cells.

The voter guide is `guide/2026-general-san-ramon.html` and `guide/ballot-sheet-nov-2026-san-ramon.pdf`. The same text is `examples/2026-general-san-ramon-sheet.md`. The HTML copy has weight sliders that recompute candidate races in the browser. Measures stay on the measure tests.

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
