# Ballot Measure Analysis

## Purpose

Ballot measures require different analysis from candidates. A candidate is a person with a record and platform; a measure is a policy change with stated purposes, actual legal text, funding mechanisms, and political coalitions. This file captures patterns for analyzing common measure types.

## Universal measure checklist

For every measure, establish:

1. **What it legally does** (not what it says it does)
2. **Who wrote it** (government body, initiative campaign, legislature)
3. **Who pays and who benefits** (tax incidence, spending allocation)
4. **Sunset provisions** (permanent or expiring?)
5. **Enforcement mechanism** (who implements, oversees, audits)
6. **Amendment threshold** (can future voters fix it easily, or is it locked in?)
7. **Historical analog** (if renewal, what's changed from original? if new, what happened with similar measures elsewhere?)
8. **Money** (FPPC filings: who's funding Yes and No campaigns?)
9. **Ballot language integrity** (has the ballot question been challenged in court? Is it neutral or argumentative?)

## Common measure types and red flags

### New sales taxes

**Red flags to surface**:
- "General" tax (goes to general fund) advertised as specific-purpose — revenue cannot legally be restricted to stated purposes
- Framing of "backfilling" cuts rather than identifying spending to reform
- Public employee union as primary funding source
- Regressive incidence (hits working families hardest)
- Short term that sets up future renewal (teaching voters to accept incremental increases)
- Partial solution framing (covers only a fraction of stated problem, implying future asks)
- Sunset provisions that can be extended without new vote

**Context to provide**:
- Current combined sales tax rate in that county/city
- Historical sales tax measure pattern (have similar measures passed and then been renewed/expanded?)
- Alternative revenue sources not being considered (progressive options, fee restructuring, etc.)

### Parcel taxes and school bonds

**Red flags to surface**:
- Flat per-parcel amount (regressive — same tax on a mansion and a condo)
- Bundled purposes (hard to evaluate each component)
- Exemptions for seniors that shift burden to younger homeowners/renters
- Claims of "no new taxes" when the measure extends or increases existing taxes
- Bond measures where interest costs aren't clearly disclosed

**Context to provide**:
- What the district currently spends per student
- Track record of prior bond measures (completed on budget? on time?)
- Alternative funding sources available

### Growth boundaries and development restrictions

**Red flags to surface on restrictive measures**:
- Long lock-in periods that prevent future adjustment
- Claims of environmental protection without addressing housing supply consequences
- Definitions drawn to protect specific interests (preserving views for incumbent homeowners)
- Carve-outs for politically connected projects

**Red flags to surface on loosening measures**:
- Enabling sprawl without providing infrastructure
- Weakening environmental review without substitute protections
- Project-specific carve-outs that set bad precedent

**Framework note**: Under the fairness-not-equity framework, growth boundaries that force infill development into already-served areas pass the 5-year test (more housing, less sprawl). Growth boundaries drawn to protect incumbent property values fail it. Read the actual map changes, not just the general concept.

### Rent control, tenant protections

**Red flags to surface**:
- Universal application (not targeted at genuinely vulnerable populations)
- No exemption for small landlords
- No supply-side complement (building more housing)
- Vacancy decontrol limitations (locks in below-market rents indefinitely)
- Historical evidence: where has this policy been tried and what happened?

**Framework note**: Under most frameworks focused on long-run outcomes, broad rent control fails the 5-year test. This is one of the most studied policy areas in economics; the evidence is not subtle.

### Police and public safety

**Red flags to surface**:
- Across-the-board funding changes without operational analysis
- Oversight structures without enforcement power
- Measures written by people with no criminal justice experience
- Historical data misused (e.g., citing one statistic out of context)

**Context to provide**:
- Actual local crime trends (not national narratives)
- What the department currently does and what's proposed to change
- Other jurisdictions that have tried similar approaches

### Initiative constitutional amendments

**Red flags to surface**:
- Locking policy into constitution instead of statute (future voters can't fix)
- Single-subject rule compliance (is it really one subject?)
- Complexity beyond what most voters can evaluate (may indicate hidden provisions)
- Campaign funding concentrated in narrow interest groups

**Framework note**: Constitutional amendments should meet a higher bar than statutes. The default posture under most frameworks should be skeptical of using the initiative process for policy that belongs in legislation.

### Bonds (state or local)

**Red flags to surface**:
- Unclear repayment source
- Interest cost over bond life (often 2x principal)
- Bundled purposes that obscure accountability
- Track record of prior bonds — delivered? on budget?
- Competitive alternatives (pay-as-you-go, federal funds, reprioritization)

## Things to ALWAYS verify directly

1. **The actual ballot language.** What will appear in front of the voter. Not the campaign website version.
2. **The full legal text.** Often linked from the voter pamphlet. Critical for understanding what the measure actually does.
3. **The impartial analysis.** Legislative Analyst's Office for state measures, county counsel or city attorney for local measures.
4. **Campaign finance.** FPPC filings tell you who has a stake. This is usually more illuminating than the policy arguments.

## Output format for measure analysis

For each measure, produce:

```markdown
### Measure [Letter/Number]: [Short name]

**What it does** (plain English, 2-3 sentences):
[Description]

**Funding/fiscal impact**:
[Revenue, cost, who pays]

**Sponsors**: [Organizations/individuals, with funding amounts if known]
**Opponents**: [Organizations/individuals, with funding amounts if known]

**Framework analysis**:
[Apply the framework's measure criteria. Address each relevant test.]

**Pick**: [YES / NO / ABSTAIN] — [Confidence level]

**Why**:
[3-5 bullet points, each with specific reasoning]

**Caveats or edge cases**:
[Anything that could change the analysis]
```

## Measure vs. candidate: different confidence calibration

Measures often produce higher-confidence picks than candidate races because:
- Measures have explicit legal text (not just campaign promises)
- Historical analogs are usually available
- The money behind each side is directly disclosable
- There are only two options (yes/no) rather than multi-candidate scoring

A measure pick should usually be Medium or High confidence. Low confidence on a measure usually indicates that the measure is genuinely novel or that information is incomplete — in which case, recommend the voter seek additional sources rather than defaulting to either position.

## Campaign finance as signal

Follow the money consistently. Under most frameworks:

- **Measure backed primarily by public employee unions**: likely revenue-expansion or job-protection measure. Scrutinize.
- **Measure backed primarily by developers**: likely zoning/permitting loosening. Scrutinize for whose interests specifically.
- **Measure backed primarily by incumbent homeowners**: likely anti-density, anti-tax, or pro-property-value. Scrutinize for diffuse-cost effects.
- **Measure backed primarily by an industry group**: likely regulatory relief for that industry. Scrutinize for externalities.
- **Measure backed primarily by a single wealthy individual**: this is not normal and deserves investigation regardless of the measure's substance.

None of these alone disqualifies a measure — sometimes the organized groups are right — but they tell you where to look for hidden costs.
