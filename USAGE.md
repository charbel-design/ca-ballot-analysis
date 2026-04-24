# How to Use This Skill

This guide walks you through using the ca-ballot-analysis skill to analyze your California ballot. Three options, in order of effort.

## Option 1: Read and apply manually (no account needed)

The simplest way. Read through the files in this repo, pick a framework that matches your values (or build your own from `frameworks/custom-template.md`), and apply the framework to your ballot yourself.

You don't need Claude, an account, or any technical setup. The methodology is the product. The framework, the character gate, the weighted criteria, the confidence calibration, these all work as thinking tools regardless of whether you run them through an AI.

Start with:
1. `frameworks/fairness-not-equity.md` to see what a worked framework looks like
2. `research/character-gate.md` to see how to evaluate disqualifying conduct
3. `research/measure-analysis.md` to see how to think through ballot measures
4. `examples/2026-primary-ca10.md` to see a full worked example

Useful if you want the thinking, not the automation.

## Option 2: Paste-in prompt (any Claude user)

If you have access to Claude (paid or free tier at claude.ai), you can use this skill without installing anything by pasting a prompt into a fresh conversation.

### Steps

1. Go to claude.ai and start a new chat
2. Open `PROMPT-VERSION.md` in this repo (coming soon)
3. Copy the entire prompt
4. Paste it into Claude as your first message
5. Follow up with your ballot: "I'm in [county], registered [party]. My framework is [fairness-not-equity / progressive / libertarian / custom]. Help me analyze my June ballot."

Claude will then walk you through the skill's workflow: scoping your ballot, locking the framework, researching each item, and producing picks with confidence levels.

This is the easiest path for most people. No installation, no technical setup, works in any Claude conversation.

## Option 3: Install as a Claude skill (for developers)

If you're on Claude Pro, Max, or Team and want the full skill experience with automatic triggering, you can install this as a custom skill in your Claude environment.

### Prerequisites

- Claude Pro, Max, or Team subscription
- Access to Claude's skill configuration (check your Claude settings for a "Skills" or "Custom Skills" section)
- Familiarity with file management and GitHub

### Steps

1. Clone or download this repo:
   ```
   git clone https://github.com/charbel-design/ca-ballot-analysis.git
   ```
   Or click the green "Code" button on the repo page and select "Download ZIP."

2. Unzip if needed. You should have a folder called `ca-ballot-analysis` containing `SKILL.md`, `README.md`, and five subfolders.

3. Add the folder to your Claude skills directory. The exact location depends on your Claude environment. Check Claude's documentation for skill installation instructions specific to your platform.

4. Restart Claude or refresh your conversation.

5. In a new conversation, invoke the skill with something like:
   - "Help me analyze my California ballot"
   - "I need ballot analysis for Contra Costa County"
   - "Who should I vote for in AD-16?"

The skill should trigger automatically based on ballot-related language.

### If installation doesn't work

Skill installation interfaces vary across Claude versions and platforms. If the skill doesn't trigger, check:
- Are the file paths preserved? (SKILL.md should be at the top of the folder, subfolders intact)
- Does your Claude plan support custom skills?
- Did you restart the conversation after installation?

If you can't get the skill to install, fall back to Option 2 (paste-in prompt) or Option 1 (manual application). Both produce valid output.

## What to expect from a full analysis

Whichever option you use, a complete ballot analysis will give you:

- **A pick for every race** on your ballot (or an abstain recommendation when evidence is too thin)
- **Confidence levels** (High / Medium / Low) for each pick, with Low-confidence picks explicitly inviting pushback
- **A one-line rationale** for each pick tied to specific framework criteria
- **A list of what's NOT on your ballot** that you might expect (prevents surprises)
- **Character gate disqualifications** with stated reasoning
- **Deliverable options**: if you ask, Claude can produce a full Word report and printable one-sheet PDF

Budget about 15-30 minutes of back-and-forth with Claude for a full primary ballot analysis. General elections with more propositions can take longer.

## Common problems and fixes

**Claude refuses to make political recommendations.**
Claude defaults to neutrality on political questions. This skill overrides that by making the framework explicit and user-chosen. If Claude pushes back, restate your framework and ask Claude to apply it (not to endorse it).

**Claude recommends candidates who aren't on my ballot.**
Verify against your county registrar's sample ballot. Claude can make mistakes on local races, especially for minor offices. Always check the official candidate list against Claude's output.

**The framework produces picks I strongly disagree with.**
Good. That's the test. Either your framework doesn't actually match your values (rebuild it using `frameworks/custom-template.md`), or the analysis got specific evidence wrong (push back with the evidence), or the framework is right and your intuition was off (uncomfortable but valuable).

**I want to use a different framework.**
Copy `frameworks/custom-template.md`, fill it in honestly, and tell Claude to use your framework instead of the shipped ones. You can also combine elements from multiple shipped frameworks.

## Contributing

If you build a framework worth sharing (progressive, libertarian, YIMBY, single-issue, or anything else), PR it to the repo. See `README.md` for contribution guidelines. Every framework stays attributed to its author.

If you find factual errors or framework improvements, file an issue. The Akram AbouKhalil pork-authoring sub-test in criterion 4 of the fairness-not-equity framework came from exactly this kind of community feedback.

## Disclaimer

This skill produces analysis based on the framework you choose and the evidence available at the time of your conversation. It is not legal advice, voter guide certification, or official election information. Before voting, verify critical information against your official sample ballot and your county registrar's website.

The skill can make mistakes. Candidates can change platforms late in a cycle. Campaign finance data has reporting lag. District assignments under California's 2025 Prop 50 redistricting can be misread. Always verify.
