# Worked example: June 2, 2026 primary — San Ramon 94582

**Last verified: October 14, 2026.**

**Framework:** fairness-not-equity, default weights 20 / 35 / 15 / 15 / 10 / 5.

This file is the June primary example after a correction pass. The original composites did not recompute from the stated weights, several rows carried a confidence label with no score, and four candidates were disqualified with no source. Those mistakes are fixed below. Narrative claims from the original file that this pass could not re-verify are not repeated.

Word and PDF renderings are optional. None were produced for this correction.

## What changed in this file

- Composites are the weighted sums of the original criterion scores. Mahan is 73.00, not 81. Villaraigosa is 65.55, not 69. Hilton is 49.55, not 61.
- The governor gap is 7.45 points, so the label is Medium. The old High label did not meet the 15-point rule in `scoring/confidence-levels.md`.
- Rows that were never scored no longer have a confidence label. Those picks are withdrawn.
- The voter is in State Senate District 9, not District 7. Both are odd-numbered, so neither is on the 2026 ballot. The old "odd years" shorthand was wrong. See the scope section.
- District attorney and sheriff are not on this ballot. That part of the old file was right for Contra Costa. The citation is below.
- No candidate is disqualified in this corrected file. Screening is not an accusation. The earlier disqualifications are withdrawn. What could be sourced is recorded as a note.

## Phase 1: Scope

**Election:** June 2, 2026 statewide direct primary. ([Contra Costa positions list, updated October 2025](https://www.contracostavote.gov/wp-content/uploads/26Jun02_PositionsUpForElection_OfficeOnly.pdf))

**Voter:** San Ramon, ZIP 94582, Contra Costa County, no party preference. The ZIP is used because the original example used it. An address-level sample ballot is still the check for council district and school trustee area.

**Districts checked for 94582:**

- Congressional District 10 under the Proposition 50 map used for the 2026 ballot. The Senate Office of Demographics lists 94582 as 100 percent of its population in that district. ([120th Congress zip directory, February 5, 2026](https://sdmg.senate.ca.gov/system/files/2026-02/ca_120thcongress_housedistricts_zipcodes_in_district-order_20260205_0.pdf); [Secretary of State on Proposition 50](https://www.sos.ca.gov/elections/california-redistricting))
- Assembly District 16. The same office's assembly zip directory lists 94582 as 100 percent in District 16. Proposition 50 did not change Assembly lines. ([2021 certified Assembly zip directory](https://sdmg.senate.ca.gov/sites/sdmg.senate.ca.gov/files/ZipCodes/2023_2024_state_assembly_zip_codes-district_order.pdf); [Secretary of State](https://www.sos.ca.gov/elections/california-redistricting))
- State Senate District 9, not District 7. The Senate zip directory lists 94582 as 100 percent in District 9. ([2021 certified Senate zip directory, dated November 21, 2024 in the file](https://sdmg.senate.ca.gov/system/files/2024-12/2025-state-senate-zip-codes-district-order.pdf))
- Board of Equalization District 2. Contra Costa County is listed in District 2. ([Secretary of State voter guide map](https://voterguide.sos.ca.gov/voter-info/boe-map.htm))
- Supervisorial District 2. The county lists San Ramon in District 2. ([District 2 supervisor page](https://www.contracosta.ca.gov/4668/District-2-Supervisor-Candace-Andersen))

**Not on this voter's June ballot:**

- State Senate. Contra Costa's own positions list says no Senate district in the county is up in 2026. The November 3, 2026 certified candidate list contains the even-numbered Senate districts only. District 9 is odd-numbered and is not on that list. The next regular election for odd-numbered districts is 2028. An August 27, 2026 Secretary of State news release said "odd-numbered" Senate seats would appear in November 2026. The certified list published the same day enumerates districts 2, 4, 6, and so on through 40. This file follows the certified list. ([Positions list](https://www.contracostavote.gov/wp-content/uploads/26Jun02_PositionsUpForElection_OfficeOnly.pdf); [certified list](https://elections.cdn.sos.ca.gov/statewide-elections/2026-general/cert-list-candidates.pdf); [news release](https://www.sos.ca.gov/administration/news-releases-and-advisories/2026-news-releases-and-advisories/california-secretary-state-shirley-n-weber-phd-certifies-candidate-list-november-3-2026-general-election))
- Board of Supervisors District 2. The June 2026 positions list puts Districts 1 and 4 on the ballot, not District 2. ([Positions list](https://www.contracostavote.gov/wp-content/uploads/26Jun02_PositionsUpForElection_OfficeOnly.pdf))
- District attorney and sheriff. Elections Code section 1300 requires those elections at the presidential primary, with a one-time six-year term for officers elected in 2022 and the next election at the 2028 presidential primary. Charter counties that fixed a different date in the charter on or before January 1, 2021 are the exception. Contra Costa's candidate guide states the 2028 date. ([Elections Code section 1300](https://law.justia.com/codes/california/code-elec/division-1/chapter-4/section-1300/); [Contra Costa June 2026 candidate guide](https://www.contracostavote.gov/wp-content/uploads/26Jun02_CandidateGuide.pdf))
- City offices and San Ramon Valley Unified trustee areas are November elections when they are up. They were not June primary contests for this voter. The November file covers them.

County fiscal offices (assessor, auditor-controller, clerk-recorder, treasurer-tax collector, superintendent of schools) and superior-court seats were on the June positions list. This corrected file does not score them. The original picks for those offices had no composites and no sources, so they are withdrawn.

## Phase 2: Framework

Fairness-not-equity, default weights. Confirmed for this example. The weights sum to 100.

| Criterion | Weight |
| --- | --- |
| Delivery | 20 |
| Policy quality × feasibility | 35 |
| Five-year effects | 15 |
| Concentrated benefit | 15 |
| Individualism and rule-equality | 10 |
| Baseline competence | 5 |

A reader who wants different weights follows `scoring/weighted-criteria.md`: substitute six numbers that sum to 100, recompute, and say the weights are not the defaults.

## Character gate

Screening is not an accusation. This corrected example disqualifies nobody.

The original file disqualified Chad Bianco, Tom Steyer, Katherine Piccinini, and Angela Griffiths without citations, and it did so in language that matched the old gate examples. That fails the sourcing rule. The disqualifications are removed.

What this pass could verify, and no more:

- Bianco ran for governor and finished fourth in the June 2, 2026 primary, with 10.2 percent (941,708 votes). He is not on the November ballot. ([Ballotpedia](https://ballotpedia.org/California_gubernatorial_election,_2026)) CalMatters reported in April 2026 that his office had obtained warrants and seized ballots from the November 2025 Proposition 50 election. ([CalMatters, April 2026](https://calmatters.org/politics/2026/04/chad-bianco-election-warrants/)) The Los Angeles Times reported on September 24, 2026 that the California Supreme Court held the seizure unlawful and ordered the remaining materials returned. ([Los Angeles Times](https://www.latimes.com/california/story/2026-09-24/california-supreme-court-ruling-ballot-seizure)) That is one sourced episode, and the court ruling is later than the primary. The corrected gate treats a single episode as a note, not an automatic disqualification. Claims in the original file about organizational membership and a crime-clearance ranking were not re-verified and are not restated.
- Steyer finished third in the same primary, with 22.8 percent (2,110,707 votes), and is not on the November ballot. ([Ballotpedia](https://ballotpedia.org/California_gubernatorial_election,_2026)) During the campaign he published a plan that included giving the attorney general authority to prosecute ICE agents and their leadership. ([Steyer's post](https://tomsteyer.substack.com/p/how-california-can-put-ice-in-jail); [KGET](https://www.kget.com/inside-california-politics/steyer-announces-plan-to-jail-ice-agents-calls-agency-a-violent-extremist-group/)) That is a campaign proposal. It is not, on its own, a pattern of completed violations, so this file does not disqualify him.
- Piccinini and Griffiths ran in the Congressional District 10 primary and did not advance. DeSaulnier received 59.7 percent and Frese 12.9 percent; Piccinini received 11.5 percent and Griffiths 6.7 percent. ([Ballotpedia](https://ballotpedia.org/California%27s_10th_Congressional_District_election,_2026)) The original descriptions of their campaigns were not re-verified to the gate standard and are not restated.

## Phase 4: Governor, the one scored race

The original file scored three candidates and stated criterion scores. This correction keeps those scores, because they are the example's judgments, and replaces the composites. It does not restate the original biographical claims (clearance rates, fee cuts, tax plans, and similar), because this pass did not re-source them. The primary result is a separate fact: Becerra (28.0 percent, 2,591,857 votes) and Hilton (24.6 percent, 2,277,318) advanced. Mahan received 3.5 percent (327,537). Villaraigosa received 1.1 percent (104,107). ([Ballotpedia](https://ballotpedia.org/California_gubernatorial_election,_2026)) The framework ranking below is not a prediction, and it did not match the order of finish.

Policy×feasibility scores below are the already-multiplied criterion scores from the original file: Mahan (85×70)/100 = 60, Villaraigosa (70×75)/100 = 53, Hilton (90×20)/100 = 18.

| Candidate | Delivery 20 | Policy×feas. 35 | Five-year 15 | Concentrated 15 | Individualism 10 | Competence 5 | Composite |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Mahan | 85 | 60 | 80 | 75 | 75 | 85 | 73.00 |
| Villaraigosa | 85 | 53 | 65 | 60 | 70 | 85 | 65.55 |
| Hilton | 40 | 18 | 75 | 80 | 85 | 70 | 49.55 |

Arithmetic:

- Mahan: (85×0.20) + (60×0.35) + (80×0.15) + (75×0.15) + (75×0.10) + (85×0.05) = 17 + 21 + 12 + 11.25 + 7.5 + 4.25 = 73.00
- Villaraigosa: (85×0.20) + (53×0.35) + (65×0.15) + (60×0.15) + (70×0.10) + (85×0.05) = 17 + 18.55 + 9.75 + 9 + 7 + 4.25 = 65.55
- Hilton: (40×0.20) + (18×0.35) + (75×0.15) + (80×0.15) + (85×0.10) + (70×0.05) = 8 + 6.3 + 11.25 + 12 + 8.5 + 3.5 = 49.55

Gap, Mahan minus Villaraigosa: 7.45. That is Medium. It is not High.

**Pick:** Mahan, among these three scored names, at Medium confidence. Hilton's raw policy score in the original file was the highest of the three, and the feasibility multiplier is why his criterion score is 18. That illustration still holds. It is not a claim about who won the primary.

**If the framework is wrong:** a reader who refuses the feasibility multiplier, and who adds policy quality instead of multiplying, is using a different framework. The original file's lesson was that this multiplier moves Hilton from a high policy score to a low criterion score.

### Sensitivity

Method: `scoring/weighted-criteria.md`. Each default weight is shifted by +10 and by −10, clipped at 0, then renormalized to 100. Twelve shifts.

Mahan stays first in all 12. The competence −10 shift clips the 5-point weight to 0. The closest call among the shifts is not close enough to change the leader. The label stays Medium because the default gap is 7.45, not because a shift flipped the race.

## Withdrawn picks

The original summary table gave High, Medium, or Low to lieutenant governor, attorney general, secretary of state, controller, treasurer, insurance commissioner, superintendent of public instruction, Board of Equalization District 2, Congressional District 10, Assembly District 16, assessor, auditor-controller, clerk-recorder, superintendent of schools, a superior-court seat, Measure B, and an urban-limit-line measure. Those rows had no composites. They do not get a confidence label. The names are not repeated here as picks.

Measure B and the urban-limit-line details in the original file (a court-ordered rewrite, a dollar figure for a PAC, a deficit projection) were not re-verified on October 14, 2026. They are omitted rather than carried forward.

## Verification checklist

- [x] Weights 20+35+15+15+10+5 = 100.
- [x] Composites recompute: 73.00, 65.55, 49.55.
- [x] No candidate pick is labeled High. The only scored gap is 7.45.
- [x] Unscored rows have no confidence label.
- [x] Factual claims that remain have an inline link. Unverified claims were removed.
- [x] Sensitivity check: leader unchanged in 12 shifts.
- [x] Last verified: October 14, 2026.

## Not verified in this pass

- The original criterion scores themselves are judgments inherited from the first draft. They are not new findings about Mahan, Villaraigosa, or Hilton.
- June results for county fiscal offices, and whether any of them went to a November runoff.
- The text of Measure B and of any June urban-limit-line measure.
- Bianco claims other than the ballot seizure reported by CalMatters and the later Supreme Court ruling reported by the Los Angeles Times.
- Piccinini's and Griffiths's campaign materials, beyond the fact that they ran and lost the primary.
