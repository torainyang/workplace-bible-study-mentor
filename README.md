# Workplace Bible Study Mentor

> An AI-powered Bible study plan generator designed for workplace Christian small groups and personal study. Produces deep, structured, and practically applicable study materials using the DUCA model.

## What It Does

Give it a Bible passage → Get a complete, ready-to-use 50-minute small group study plan.

The output includes:
- **Group Handout** — Structured questions for group discussion or personal study
- **Study Reference** — Answer directions, common pitfalls & corrections, deeper exploration questions, and application analysis (idol exposure, concrete actions, worst-case scenarios)

It also works as an **instant spiritual counsel** mode for personal faith and workplace struggles.

## Why It's Different

Most Bible study generators produce generic, surface-level questions. This one is specifically engineered for **workplace professionals** who face real ethical dilemmas — KPIs, office politics, layoffs, compliance conflicts.

Key design principles:
- **Internal pre-computation**: Genre scan, core tension extraction, and risk assessment before generating any questions — ensuring genre-appropriate, theologically grounded output
- **Three-expert cross-validation**: Every output is shaped by a Shepherd (pastoral care), Scholar (hermeneutical rigor), and Elder (workplace realism)
- **DUCA with Goal + Principles + Anti-patterns**: Each stage has a defined goal, guiding principles, and explicit anti-patterns to prevent low-quality output
- **Anti-platitude guardrails**: The system actively rejects hollow spiritual clichés and fairy-tale endings
- **Concrete action focus**: Application questions demand specific talk tracks and decisions, not just "attitude adjustments"
- **Dual-audience Study Reference**: Works equally well for facilitator preparation and individual self-study at home

## Installation

### Claude (Recommended)

**Option A: Claude Code**
1. Clone this repository (or download ZIP)
2. Copy the entire `workplace-bible-study-mentor/` folder into `.claude/skills/` in your project
3. The skill will be automatically available

**Option B: Claude.ai Skill Upload**
1. Download or clone this repository
2. ZIP the entire `workplace-bible-study-mentor/` folder
3. Go to Claude.ai > Settings > Capabilities > Skills
4. Click "Upload skill" and select the ZIP file
5. Start chatting with a Bible passage (e.g., "Mark 2")

**Option C: Claude Projects**
1. Go to [Claude Projects](https://claude.ai)
2. Create a new Project
3. Copy the contents of `SKILL.md` (everything after the YAML frontmatter `---`) into the System Prompt field

### Gemini

1. Go to [Gemini Gems](https://gemini.google.com)
2. Create a new Gem
3. Copy the contents from `references/gemini-version.md` into the Instructions field
4. Start chatting with a Bible passage

> **Note:** The Gemini version (`references/gemini-version.md`) is based on v5 and has not yet been updated to reflect v8 changes. A Gemini-optimized v8 version is planned.

## Repository Structure

```
workplace-bible-study-mentor/
├── SKILL.md                            # Main skill file (v8 — current)
├── README.md                           # This file
├── LICENSE                             # MIT License
└── references/                         # Bundled resources & historical versions
    ├── gemini-version.md               # Gemini Gems optimized prompt (v5-based)
    ├── skill7-test-cases.md            # 27 systematic test cases for QA
    ├── skill7-output1.md               # Example output: Mark 2 (v7)
    ├── skill5-output1.md               # Example output: Mark 2 (v5)
    ├── skill6-output1.md               # Example output: Mark 2 (v6)
    ├── V5-V6-comparison.md             # Version comparison analysis
    ├── SKILL-v5.md                     # Historical: v5 skill
    ├── SKILL-v6-experimental.md        # Historical: v6 experimental skill
    └── SKILL-v7.md                     # Historical: v7 skill
```

### What Goes Where

| File | Purpose | Used by |
|------|---------|---------|
| `SKILL.md` | Core skill instructions (v8) | Claude (auto-loaded) |
| `README.md` | Human documentation | GitHub / developers |
| `LICENSE` | Legal | GitHub / developers |
| `references/gemini-version.md` | Cross-platform prompt | Gemini Gems users |
| `references/skill7-test-cases.md` | Quality assurance | Developers / testers |
| `references/skill*-output*.md` | Example outputs | Reference / comparison |
| `references/SKILL-v*.md` | Version history | Archive |

## The DUCA Model

| Phase | Goal | Principles | Question Count |
|---|---|---|---|
| **D**iscovery | "I never noticed that before" — see details others skip | Genre-specific question styles (narrative → scene reconstruction; epistle → logical flow mapping; poetry → imagery unpacking) | 2-3 |
| **U**nderstanding | Break habitual thinking — challenge default interpretations | Must touch theological anchors: human condition (idols/fears) and/or God's character (grace/sovereignty) | 2 |
| **C**orrelation | Not an island — connect to the larger biblical narrative | Theological guardrail against moralism, prosperity distortion, decontextualization | 1-2 sets |
| **A**pplication | Business-school-grade ethical dilemmas grounded in Scripture | Concise scenarios (2-4 sentences), specific roles, genuine decisional tension | 2 |

## Example Usage

Input:
```
Mark chapter 2
```

Output includes:
- Core theme and workplace entry point
- 3 Discovery questions with genre-appropriate observation prompts
- 2 Understanding questions with embedded historical/linguistic context
- 2 Cross-reference sets revealing biblical narrative patterns
- 2 Workplace Application scenarios (concise, sharp)
- Study Reference for each question:
  - Answer Direction (integrated three-expert analysis)
  - Common Pitfalls & Corrections (2-3 specific misreadings with redirections)
  - Deeper Exploration (progressive follow-up questions)
  - For Application: Idol Exposure (multi-layer) + Concrete Action (exact talk tracks) + Worst-Case Scenario (no fairy-tale endings)

See `references/skill7-output1.md` for a complete example output (v7 format — v8 example coming soon).

## Version History

| Version | Key Changes |
|---|---|
| v1 | Basic DUCA framework + three-expert setup |
| v2 | XML structure + routing mechanism + Application constraints + self-check |
| v3 | Gemini adaptation + anti-false-consensus + language anchoring |
| v4 | Claude Skill format + Expert "teeth" upgrade + 3-dimension analysis (Idol/Action/Worst-case) + anti-fairy-tale self-check |
| v5 | Claude Skill standard format, kebab-case naming, BOM-free UTF-8, single-line YAML description |
| v6 | Experimental: goal-oriented DUCA definitions, "business school case" quality benchmark, natural expert integration |
| v7 | Merged v5 stability + v6 creativity: explicit tension labeling, multi-layer idol exposure, genre-adaptive D questions, "original audience vs modern reader" U guidance |
| **v8** | **Current. Three key upgrades: (1) DUCA with Goal + Principles + Anti-patterns for higher-quality questions; (2) Study Reference replaces Facilitator's Guide — works for self-study and group leading; (3) Concise Application scenarios (2-4 sentences, no long stories). Also adds Internal Pre-computation (genre scan + core tension + risk assessment + council deliberation) as a chain-of-thought layer before output generation.** |

See `references/V5-V6-comparison.md` for detailed version comparison analysis.

## Testing

The `references/skill7-test-cases.md` file contains 27 systematic test cases covering:
- Routing & basic behavior (TC-01 to TC-04)
- Track A structural completeness (TC-05 to TC-09)
- Study Reference quality (TC-10 to TC-15)
- Guardrails & constraints (TC-16 to TC-19)
- Three-expert system (TC-20)
- Silent self-check (TC-21)
- Cross-version comparison (TC-22 to TC-23)
- Edge cases & stability (TC-24 to TC-27)

> **Note:** Test cases were written for v7 and may need updates to reflect v8's Study Reference structure (replacing Facilitator's Guide references).

## License

MIT License. See [LICENSE](LICENSE) for details.

## Contributing

Issues and PRs are welcome. If you have used this skill to generate study plans for other Bible passages and want to contribute examples, please submit them.

---

> *"Mark chapter 2 tells us: Jesus did not come to patch your old system — He came to establish an entirely new order."*
