# ca-ballot-analysis

A Claude skill for analyzing California ballots through an explicit framework.

## What this does

Most ballot guides are either comprehensive reference (Ballotpedia), nonpartisan journalism (CalMatters), or disguised endorsement (newspaper editorial boards). None of them applies an explicit, user-chosen framework to every item on the ballot.

This skill does. You choose (or build) a framework. The skill researches every race and measure on your California ballot, applies your framework with a documented character gate and weighted criteria, and produces picks with confidence levels — plus optional Word report and printable one-sheet PDF deliverables.

The framework is always explicit. A progressive framework and a libertarian framework will produce different picks; that's the feature.

## Design principles

1. **Framework transparency.** Every output states which framework was used. No hidden framework.
2. **Source verification.** Every factual claim is sourced. No hallucinated candidates or votes.
3. **Character gate first.** Disqualifying conduct is checked before scoring. Rule of law, extremism, unseriousness, and judgment lapses are evaluated explicitly.
4. **Feasibility multiplier.** Policy quality times feasibility, not plus. A great platform that can't pass is worth less than a good platform that can.
5. **Confidence calibration.** Every pick is High / Medium / Low confidence. Low-confidence picks explicitly invite pushback.
6. **Abstention is valid.** If evidence is insufficient (judicial races with thin records), recommend abstention over fabrication.

## Usage

Install the skill in your Claude environment, then invoke with a request like:

- "Help me analyze my California ballot"
- "I'm in [county], registered [party], ballot arrived. Walk me through it."
- "What should I make of Measure [X] in [county]?"

The skill will ask which framework to use. Pick from the shipped frameworks, import your own, or build one from the custom template.

## Framework library

Shipped frameworks (all in `frameworks/`):

- **fairness-not-equity.md** — Common-sense fairness, rule of law, individual over group, 5-year test. Written. Production-ready.
- **progressive.md** — Social-democratic framework. PLACEHOLDER — needs contribution.
- **libertarian.md** — Minimal-state framework. PLACEHOLDER — needs contribution.
- **yimby-housing.md** — Housing supply as dominant criterion. PLACEHOLDER — needs contribution.
- **custom-template.md** — Build your own framework from scratch.

## Contributing a framework

Frameworks should be written by people who actually hold the underlying values. A progressive framework written by a libertarian (or vice versa) will inevitably strawman.

If you want to contribute a framework:

1. Copy `frameworks/custom-template.md` to a new file
2. Fill in every section honestly (especially "known framework limitations")
3. Test it against 2-3 past California ballots to verify it produces picks that match your values
4. PR against the repo with a brief author note

## What this skill does NOT do

- Does not tell you which framework is correct
- Does not analyze out-of-state ballots (California only)
- Does not provide real-time election-day features (polling locations, live results)
- Does not predict winners or forecast elections
- Does not store user data between conversations

## What this skill might get wrong

- **Recent candidates** may have information gaps (new entrants, minor local races)
- **District assignments** can be wrong if the skill uses outdated maps (always verify against your sample ballot)
- **Campaign finance** data has reporting lag
- **Court rulings** affecting ballot language can be missed if they happen after the analysis

Always verify critical decisions against your official sample ballot from your county registrar.

## License

MIT. Fork it, improve it, use it for other states, adapt the frameworks.

## Why this exists

The alternative to an explicit-framework ballot analyzer isn't "voters thinking for themselves, unaided." It's voters outsourcing thinking to party endorsements, union recommendations, editorial boards, or AI tools that hide their frameworks. This skill puts the framework in the open so the user can interrogate it, modify it, or reject it.

Framework-based analysis is not a substitute for civic engagement. It's a tool for voters who care enough to want their reasoning explicit.

## Disclaimer

This is not legal advice, campaign consulting, or official voter guidance. Ballot analyses produced by this skill reflect the framework used and the evidence available at the time of analysis. Before voting, verify critical information against your official sample ballot and county registrar's website.

## Maintainer

[Your name and contact, once you're ready to publish]

## Acknowledgments

Built with Claude (Anthropic). Methodology informed by the limitations of existing California voter guides.
