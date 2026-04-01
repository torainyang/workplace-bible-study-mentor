# Workplace Bible Study Mentor

> An AI-powered Bible study plan generator designed for workplace Christian small groups. Produces deep, structured, and practically applicable study materials using the DUCA model.

## What It Does

Give it a Bible passage -> Get a complete, ready-to-use 50-minute small group study plan.

The output includes:
- **Group Handout** - Structured questions for every participant
- **Facilitator's Guide** - Reference answers, discussion hooks, probing questions, and crowd-control strategies

It also works as an **instant spiritual counsel** mode for personal faith and workplace struggles.

## Why It's Different

Most Bible study generators produce generic, surface-level questions. This one is specifically engineered for **workplace professionals** who face real ethical dilemmas - KPIs, office politics, layoffs, compliance conflicts.

Key design principles:
- **Three-expert cross-validation**: Every output is checked by a Shepherd (pastoral care), Scholar (hermeneutical rigor), and Elder (workplace realism)
- **Anti-platitude guardrails**: The system actively rejects hollow spiritual cliches and fairy-tale endings
- **Concrete action focus**: Application questions demand specific talk tracks and decisions, not just "attitude adjustments"
- **Worst-case scenario analysis**: Every application answer must address what happens when doing the right thing leads to worldly failure

## Installation

### Claude (Recommended)

**Option A: Claude.ai Skill Upload**
1. Download or clone this repository
2. ZIP the `workplace-bible-study-mentor/` folder (the inner one containing `SKILL.md`)
3. Go to Claude.ai > Settings > Capabilities > Skills
4. Click "Upload skill" and select the ZIP file
5. Start chatting with a Bible passage (e.g., "Mark 2")

**Option B: Claude Code**
1. Place the `workplace-bible-study-mentor/` folder (the inner one) under `.claude/skills/` in your project
2. The skill will be automatically available

**Option C: Claude Projects**
1. Go to [Claude Projects](https://claude.ai)
2. Create a new Project
3. Copy the contents of `workplace-bible-study-mentor/SKILL.md` (everything after the YAML frontmatter `---`) into the System Prompt field

### Gemini

1. Go to [Gemini Gems](https://gemini.google.com)
2. Create a new Gem
3. Copy the contents from `workplace-bible-study-mentor/references/gemini-version.md` into the Instructions field
4. Start chatting with a Bible passage

## Repository Structure

```
workplace-bible-study-mentor/
|-- README.md                                    # This file (for humans)
|-- LICENSE                                      # MIT License
|-- workplace-bible-study-mentor/                # The Skill folder (for Claude)
    |-- SKILL.md                                 # Main skill file (required)
    |-- references/
        |-- gemini-version.md                    # Gemini-optimized prompt
```

## The DUCA Model

| Phase | Purpose | Question Count |
|---|---|---|
| **D**iscovery | Observe facts, reconstruct the scene | 2-3 |
| **U**nderstanding | Dig into theological logic, challenge assumptions | 2 |
| **C**orrelation | Cross-reference with other Scripture | 1-2 sets |
| **A**pplication | Workplace scenario dilemmas with real stakes | 2 |

## Example Usage

Input:
```
Mark chapter 2
```

Output includes:
- Logic restructuring with core theme and workplace entry point
- 3 Discovery questions with facilitator notes
- 2 Understanding questions with theological depth
- 2 Cross-reference sets
- 2 Workplace Application scenarios with:
  - Idol Exposure (what are you really afraid of losing?)
  - Concrete Action (specific talk tracks for tomorrow)
  - Worst-Case Scenario (when doing right leads to worldly failure)

## Version History

| Version | Changes |
|---|---|
| v1 | Basic DUCA framework + three-expert setup |
| v2 | XML structure + routing mechanism + Application constraints + self-check |
| v3 | Gemini adaptation + anti-false-consensus + language anchoring |
| **v4** | **Claude Skill format + Expert "teeth" upgrade + 3-dimension analysis (Idol/Action/Worst-case) + anti-fairy-tale self-check** |

## License

MIT License. See [LICENSE](LICENSE) for details.

## Contributing

Issues and PRs are welcome. If you have used this skill to generate study plans for other Bible passages and want to contribute examples, please submit them.

---

> *"Mark chapter 2 tells us: Jesus did not come to patch your old system - He came to establish an entirely new order."*
