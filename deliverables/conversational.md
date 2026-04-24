# Deliverable: Conversational Output

## When to use

This is the DEFAULT output mode. Use this unless the user explicitly asks for a Word report or one-sheet PDF.

Most ballot analysis conversations happen over several turns with the user asking follow-up questions. The conversational format handles this better than generating documents after every exchange.

## Core principles

1. **Scale response length to question specificity.** "Should I vote yes on Measure B?" needs a focused answer, not a 9-page analysis.
2. **Lead with the pick.** Don't bury it in preamble. "Pick: [Name]. Here's why:" is the right shape.
3. **Make confidence explicit.** Always say High/Medium/Low, not just the pick.
4. **Invite pushback.** The voter knows things the skill doesn't. Structure output to support their challenges.

## Output formats by question type

### Full ballot analysis (user wants everything)

Follow the phase workflow. Produce conversational output that covers every ballot item. Use markdown tables for dense information (picks summary) and prose for rationales.

Length target: 1500-3000 words depending on ballot size. Organize into logical sections (statewide, federal/state, county, measures) with clear headers.

End with: "Want me to turn this into a full Word report and one-sheet PDF?"

### Single race analysis (user asks about one race)

Structure:
1. **The pick** (bolded, with confidence)
2. **Why** (2-4 sentences of reasoning tied to framework criteria)
3. **Runner-up note** (who's the next closest candidate and why not them)
4. **If framework is wrong** (1-2 sentences on what would change the pick)

Length target: 150-300 words.

### Single measure analysis (user asks about one measure)

Structure:
1. **What it does** (2-3 sentences in plain English)
2. **The pick** (YES/NO/ABSTAIN with confidence)
3. **Why** (3-5 bullet points tied to framework measure tests)
4. **Strongest opposing argument** (steelman the other side briefly)

Length target: 200-400 words.

### Clarification / follow-up questions

Match the user's scope. A clarifying question deserves a clarifying answer, not a re-dump of the full analysis. If the user pushes back on a pick, engage with the specific reason they pushed back — don't defensively restate the original reasoning.

## What to include by default

Every conversational output should include:

1. **The picks** with confidence levels
2. **The framework name** somewhere visible (can be in an opening sentence for long outputs, or a footer note for short outputs)
3. **At least one "where I could be wrong" moment** for any output covering multiple races or medium/low confidence picks

## What to avoid

1. **False neutrality.** If the framework points toward a pick, state it. Don't hedge with "it's up to you" on every race.
2. **Endorsement language.** "You should vote for X" is wrong framing. "The framework points toward X" is right.
3. **Over-hedging.** Low-confidence picks should say they're low-confidence; medium-high picks should not be undermined with excessive caveats.
4. **Dumping research.** The user doesn't need to see every source. Synthesize, attribute when material, paraphrase.
5. **Pretending all races deserve equal attention.** Governor matters more than Board of Equalization. Length should reflect leverage.

## Formatting conventions

- **Bold** for candidate names and YES/NO votes
- Tables for summary views (full ballot overview)
- Bullet points only for genuinely list-like content (reasons, tests applied, candidates in a field)
- Prose paragraphs for reasoning
- Subheadings (##) only for multi-race outputs
- Em dashes AVOIDED per user preference (use colons, parentheses, or two sentences)

## Sample single-race output

> **Pick: Stacy Korsgaden (R)** — High confidence.
>
> Korsgaden has 30+ years running an insurance agency, which makes her the only candidate in the field who actually understands the market dynamics driving carriers out of California. The framework weights industry-relevant experience heavily for regulatory offices, and her platform (faster rate approval, market competition to attract carriers back) addresses the actual mechanism behind the non-renewal crisis rather than the political framing of it.
>
> Runner-up: Ben Allen (D). Thoughtful state senator with neighborhood-scale fire mitigation framing. If you prefer a Democratic candidate and want a pragmatic one, Allen over Bradford and far over Kim — Kim's "insurers are profiting" framing doubles down on the adversarial approach that caused the exodus in the first place.
>
> If the framework is wrong: if you believe the insurance crisis is primarily about insurer greed rather than regulatory structure, you'd prefer Kim or Bradford.

Notice: pick, confidence, reasoning tied to framework, runner-up, and explicit space for disagreement. 175 words.

## Sample ballot-overview output structure

When producing a full ballot overview conversationally:

```markdown
Here's your ballot analyzed through [framework name].

## Executive summary

[Markdown table with all picks and confidence]

## Statewide offices

### Governor
[Pick, confidence, 2-3 sentence rationale]

### Lt. Governor
[Shorter format for lower-leverage offices]

[Continue for each statewide race]

## Federal and state legislative

[Races with district context]

## County races

[Races that are on the voter's specific ballot]

## Ballot measures

[Measures with YES/NO and bullet rationale]

## Framework caveats

[Honest note on where confidence is lowest + where framework is strongest]

Want me to turn this into a full Word report and printable one-sheet PDF?
```

## Handling follow-ups

Common follow-up patterns:

- **"Why not X?"**: Engage with why X didn't score higher on specific criteria. Don't dismiss the alternative.
- **"What about [issue]?"**: If the user raises an issue not addressed, address it and adjust the pick if warranted. Don't defend the original pick just because you made it.
- **"I disagree with your framework on [X]"**: Acknowledge, ask what they'd weight differently, and re-run affected races with the adjusted framework.
- **"Are you sure?"**: If confidence is Low or Medium, say so explicitly and name what would shift it. If High, restate the evidence succinctly.

The user is the decision-maker. The skill's job is to produce the best reasoning given their framework, not to defend its picks.
