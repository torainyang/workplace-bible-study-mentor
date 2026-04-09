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
- **Three Lenses integration**: Every output is shaped by Gospel Lens (pastoral care), Text Lens (hermeneutical rigor), and Workplace Lens (organizational realism) — with explicit tension surfacing when lenses diverge
- **Five Quality Red Lines**: Hard constraints that override everything — specific conflict scenarios, anti-platitude questions, multi-layer idol exposure, exact talk tracks with pushback handling, and no fairy-tale endings (not even long-term payoff framing)
- **Two-Stage Sequential Generation**: Outputs are generated in two stages to stay within the LLM quality sweet spot, eliminating truncation and quality decay
- **DUCA with Goal + Principles + Anti-patterns**: Each stage has a defined goal, guiding principles, and explicit anti-patterns to prevent low-quality output
- **Concrete action focus**: Application questions demand specific talk tracks, counterparty pushback responses, and decisions — not just "attitude adjustments"
- **Dual-audience Study Reference**: Works equally well for facilitator preparation and individual self-study at home
- **Dual-file output**: Automatically generates both a clean Group Handout (学员手册) and a comprehensive Study Reference (学习参考)

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
3. Copy the contents from `platforms/gemini-version.md` into the Instructions field
4. Start chatting with a Bible passage

> **Note:** The Gemini version (`platforms/gemini-version.md`) is based on v5 and has not yet been updated to reflect v9 changes. A Gemini-optimized v9 version is planned.

## Repository Structure

```
workplace-bible-study-mentor/
├── SKILL.md                            # Main skill file (v9.3 — current)
├── README.md                           # This file
├── RUBRIC.md                           # Quality scoring rubric for output evaluation
├── ITERATION-GUIDE.md                  # Iteration guide for skill development
├── LICENSE                             # MIT License
│
├── references/                         # AI runtime reference materials (reserved)
│
├── outputs/                            # Generated study plans (actual deliverables)
│   ├── Mark2-1-17-学员手册.md           # Group Handout: Mark 2:1-17
│   ├── Mark2-1-17-学习参考.md           # Study Reference: Mark 2:1-17
│   ├── Mark2-Part1-学员手册.md          # Group Handout: Mark 2 Part 1 (alt version)
│   └── Mark2-Part1-学习参考.md          # Study Reference: Mark 2 Part 1 (alt version)
│
├── platforms/                          # Cross-platform adaptations
│   └── gemini-version.md               # Gemini Gems optimized prompt (v5-based)
│
├── tests/                              # Testing & quality assurance
│   ├── skill7-test-cases.md            # 27 systematic test cases for QA
│   ├── skill5-output1.md               # Test output: Mark 2 (v5)
│   ├── skill6-output1.md               # Test output: Mark 2 (v6)
│   └── skill7-output1.md               # Test output: Mark 2 (v7)
│
└── archive/                            # Historical versions & development docs
    ├── SKILL-v5.md                     # Historical: v5 skill
    ├── SKILL-v6-experimental.md        # Historical: v6 experimental skill
    ├── SKILL-v7.md                     # Historical: v7 skill
    ├── V5-V6-comparison.md             # Version comparison analysis
    └── prompt优化1.md                   # Prompt optimization audit report
```

### What Goes Where

| Directory / File | Purpose | Used by |
|------|---------|---------|
| `SKILL.md` | Core skill instructions (v9.3) | Claude / CodeFuse (auto-loaded) |
| `README.md` | Human documentation | GitHub / developers |
| `RUBRIC.md` | Quality scoring rubric for evaluating outputs | Developers / testers |
| `ITERATION-GUIDE.md` | Guide for iterating on skill development | Developers |
| `references/` | AI runtime reference materials (currently empty, reserved for future high-quality few-shot examples) | AI at runtime |
| `outputs/` | Generated study plans — the actual deliverables | End users / small groups |
| `platforms/` | Cross-platform prompt adaptations | Gemini Gems users |
| `tests/` | Test cases and historical test outputs for QA | Developers / testers |
| `archive/` | Historical prompt versions and development analysis docs | Archive / reference |

## The DUCA Model

| Phase | Goal | Principles | Question Count |
|---|---|---|---|
| **D**iscovery | "I never noticed that before" — see details others skip | Genre-specific question styles (narrative → scene reconstruction; epistle → logical flow mapping; poetry → imagery unpacking) | 2-3 |
| **U**nderstanding | Break habitual thinking — challenge default interpretations | Must touch theological anchors: human condition (idols/fears) and/or God's character (grace/sovereignty) | 2 |
| **C**orrelation | Not an island — connect to the larger biblical narrative | Theological guardrail against moralism, prosperity distortion, decontextualization. Study Reference includes Selection Rationale + Transformation Claim for each cross-reference. | 1-2 sets |
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
- 2 Cross-reference sets revealing biblical narrative patterns (with selection rationale and transformation claims)
- 2 Workplace Application scenarios (concise, sharp)
- Study Reference for each question:
  - Answer Direction (integrated three-lens analysis)
  - Common Pitfalls & Corrections (2-3 specific misreadings with redirections)
  - Deeper Exploration (progressive follow-up questions)
  - For Application: Idol Exposure (multi-layer) + Concrete Action (exact talk tracks + pushback handling) + Worst-Case Scenario (no fairy-tale endings, no long-term payoff framing)

See `outputs/` for complete example outputs, or `tests/skill7-output1.md` for a historical test output.

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
| v8 | Three key upgrades: (1) DUCA with Goal + Principles + Anti-patterns; (2) Study Reference replaces Facilitator's Guide — works for self-study and group leading; (3) Concise Application scenarios (2-4 sentences). Added Internal Pre-computation (genre scan + core tension + risk assessment) as chain-of-thought before output. |
| v9.0 | Major restructure: Three Lenses (Gospel / Text / Workplace) replace three-expert council. Five Quality Red Lines as hard constraints. Passage Pre-scan display. Scripture Reading Guide matched to genre. Target word counts for Study Reference. Dialogue Depth Management for Track B. Boundary Escalation protocol. ~25% token reduction. |
| v9.1 | Self-audit fixes: dual-file output strategy (学员手册 + 学习参考), bilingual length anchoring, 3 benchmark Application examples, Prophetic/Law reading guides, Correlation nuancing, series learning support. |
| v9.1.1 | RUBRIC-driven fixes: Red Line #4 adds pushback requirement; Red Line #5 adds anti-long-term-payoff clause; C Study Reference adds Selection Rationale + Transformation Claim. |
| v9.2 | Two-Stage Sequential Generation — Stage 1 writes 学员手册 (~1,500 tokens), Stage 2 writes 学习参考 (~3,000 tokens). CRITICAL save-to-disk gates between stages. Eliminates output truncation and quality decay from single-shot generation. |
| **v9.3** | **Current. Prompt diet — removed 3 items from v9.1 that consumed tokens without proportional quality gain: (1) 3 inline benchmark Application examples (moved to RUBRIC.md); (2) minimal series learning handling (deferred to v10 full implementation); (3) greeting format anchoring (unnecessary micro-management). Net effect: ~200 token reduction in SKILL.md with no quality regression.** |

See `archive/V5-V6-comparison.md` for detailed version comparison analysis.

## Testing

The `tests/skill7-test-cases.md` file contains 27 systematic test cases covering:
- Routing & basic behavior (TC-01 to TC-04)
- Track A structural completeness (TC-05 to TC-09)
- Study Reference quality (TC-10 to TC-15)
- Guardrails & constraints (TC-16 to TC-19)
- Three-expert system (TC-20)
- Silent self-check (TC-21)
- Cross-version comparison (TC-22 to TC-23)
- Edge cases & stability (TC-24 to TC-27)

> **Note:** Test cases were written for v7 and may need updates to reflect v9's structural changes (Three Lenses replacing three-expert council, dual-file output, two-stage generation, etc.).

## License

MIT License. See [LICENSE](LICENSE) for details.

## Contributing

Issues and PRs are welcome. If you have used this skill to generate study plans for other Bible passages and want to contribute examples, please submit them to the `outputs/` directory.

---

> *"Mark chapter 2 tells us: Jesus did not come to patch your old system — He came to establish an entirely new order."*
