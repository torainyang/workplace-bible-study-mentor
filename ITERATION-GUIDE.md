# Iteration Guide — Workplace Bible Study Mentor

> This document is for **human use only** — it is NOT injected into the LLM prompt.
> It contains the methodology, audit frameworks, and version history for iterating on SKILL.md.

---

## 1. Architecture Overview

```
workplace-bible-study-mentor/
├── SKILL.md              ← Runtime prompt (injected into LLM context)
├── RUBRIC.md             ← Quality evaluation rubric (for human/LLM-judge use)
├── ITERATION-GUIDE.md    ← This file (methodology + version history)
├── README.md             ← Human documentation (GitHub / developers)
├── LICENSE               ← MIT License
│
├── references/           ← AI runtime reference materials (reserved for future few-shot examples)
├── outputs/              ← Generated study plans (actual deliverables)
├── platforms/            ← Cross-platform prompt adaptations (e.g., Gemini)
├── tests/                ← Test cases and historical test outputs for QA
└── archive/              ← Historical prompt versions and development docs
```

**Separation principle:** Runtime instructions (SKILL.md) must be kept minimal. Meta-level methodology (this file) and evaluation criteria (RUBRIC.md) live outside the prompt to avoid consuming token budget.

---

## 2. Prompt Engineering Principles

These principles were established through iterative testing and apply to ALL skill development, not just this one.

### 2.1 Attention Economics
- **Primacy-Recency Effect:** LLMs pay most attention to the beginning (~20%) and end (~20%) of a system prompt. The middle receives the least attention.
- **Action:** Place the most critical constraints (Quality Red Lines) at the very top of SKILL.md, immediately after Identity.
- **Action:** Keep the ending clean — Guardrails and Language settings, not verbose templates.

### 2.2 Positive Examples > Negative Prohibitions
- Showing the LLM "what good looks like" is 3-5x more effective than listing "what not to do."
- **Negative priming paradox:** Providing specific bad examples (e.g., "Don't write: 'Have you experienced God's grace?'") actually increases the probability of generating similar content, because the LLM's attention is drawn to the example.
- **Action:** Maintain a ratio of at least 3:1 (good examples : bad examples) in SKILL.md. Prefer benchmark examples over anti-pattern lists.

### 2.3 Executable Instructions Only
- Do not give the LLM instructions it cannot actually execute (e.g., "silently perform pre-computation before generating output"). Auto-regressive models generate token-by-token; they cannot "think first, then write."
- **Action:** If you want pre-computation to influence output, make it visible (require the LLM to output the analysis) so it enters the context and genuinely shapes subsequent generation.

### 2.4 Rule Count Discipline
- When rules exceed 5-7 items, compliance with each individual rule drops significantly.
- **Action:** Compress self-check lists to ≤5 core red lines. Embed secondary checks inline within the relevant section rather than in a separate checklist.

### 2.5 Length Anchoring
- Without explicit length guidance, LLMs tend to over-generate, causing quality degradation in the latter half of long outputs.
- **Action:** Provide soft length targets (word/character counts) for each output component. These are not hard limits but "anchors" that prevent runaway generation.

### 2.6 Output Segmentation
- For outputs exceeding ~4,000 tokens, quality degrades in the second half (reduced sharpness, increased repetition, looser structure).
- **Sweet spot:** 2,000-4,000 tokens per response.
- **Action:** Include explicit segmentation instructions in SKILL.md for long passages. Use a "bridge summary" between segments to maintain coherence.

### 2.7 Semantic Deduplication
- Saying the same thing in multiple places (e.g., "no fairy-tale endings" in both the Application section and the Self-Check) wastes tokens and dilutes attention.
- **Action:** State each rule once, in the most relevant location. Reference it elsewhere if needed, but do not repeat the full description.

### 2.8 Bilingual Term Anchoring
- When the prompt is in English but output is in Chinese (or vice versa), subtle semantic distinctions can be "flattened" during language switching.
- **Action:** For key structural terms, provide both English and Chinese labels in SKILL.md so the LLM maintains clear boundaries between output components.

### 2.9 Runtime vs. Meta Separation
- **Runtime instructions** (SKILL.md): What the LLM reads every time it generates output. Must be minimal and precise.
- **Meta instructions** (this file): How humans iterate on the skill. Can be as detailed as needed.
- **Evaluation criteria** (RUBRIC.md): How output quality is measured. Kept separate so it can be injected into a different LLM for automated evaluation.
- **Never mix these layers.** Putting audit methodology into SKILL.md confuses the LLM about whether it should generate content or evaluate content.

---

## 3. Audit Expert Panels

When iterating on SKILL.md, convene two expert panels for deep analysis. These panels are **mental models for the human editor**, not roles for the LLM.

### 3.1 AI Hardness Engineering Panel

| Expert | Focus Area |
|--------|-----------|
| **Tokenizer Expert** | Token efficiency, multilingual token overhead, term boundary effects |
| **Attention Expert** | How LLM attention distributes across long prompts; primacy/recency effects |
| **Instruction Following Expert** | Instruction executability, ambiguity detection, conflict detection between rules |
| **Evaluation Expert** | How to verify output actually follows instructions; rubric design |

**Key questions this panel asks:**
1. Is every instruction in SKILL.md actually executable by an auto-regressive model?
2. Are there any instruction pairs that contradict each other?
3. Is the most important content positioned where attention is highest?
4. Can compliance with each rule be objectively measured?

### 3.2 Bible Study Design Panel

| Expert | Focus Area |
|--------|-----------|
| **Inductive Bible Study Expert** | DUCA model pedagogical soundness; question progression logic |
| **Hermeneutics Expert** | Exegetical methodology; guarding against eisegesis |
| **Group Dynamics Expert** | Real-world usability in small group settings; facilitation challenges |
| **Workplace Theology Expert** | Faith-work integration; avoiding common theological pitfalls (prosperity gospel, dualism, moralism) |

**Key questions this panel asks:**
1. Does the DUCA progression actually build understanding, or do stages feel disconnected?
2. Are the hermeneutical guardrails strong enough to prevent well-meaning but textually unfounded applications?
3. Would a real small group of 3-4 people be able to complete this study in 50 minutes?
4. Do the Application scenarios reflect diverse workplace contexts (not just corporate/tech)?

---

## 4. Version History

### v9.3.0 (2026-04-07)
**Patch release: Prompt diet — remove low-ROI instructions to reduce token overhead.**

Root cause analysis: Three items added in v9.1.0 consumed ~200 tokens in SKILL.md without proportional quality improvement. Benchmark scoring with RUBRIC.md showed no regression after removal.

Changes from v9.2.0:
1. **Removed 3 inline benchmark Application examples (Manager/Peer/IC):** These occupied ~150 tokens in SKILL.md. The same examples now live in RUBRIC.md (Benchmark Samples section), where they serve evaluators without consuming runtime prompt budget. The generic instruction "Scenarios should vary across management levels (manager, peer, IC)" is retained.
2. **Removed minimal series learning handling ("第一次学习" / "session N" signals):** The v9.1.0 implementation was too thin to be useful. Full series mode with cross-session theme accumulation remains planned for v10 (see Roadmap).
3. **Removed greeting format anchoring (3-5 sentences + end with open question):** Unnecessary micro-management of LLM greeting behavior. The Identity & Tone section provides sufficient guidance.

**Token impact on SKILL.md:** ~2,800-3,100 tokens (v9.2.0) → ~2,600-2,900 tokens (v9.3.0). ~200 token reduction.

### v9.2.0 (2026-04-05)
**Minor release: Two-Stage Sequential Generation — eliminates output truncation.**

Root cause analysis: Single-shot generation of both files (~5,000-6,000 tokens) exceeded the LLM sweet spot (~2,000-4,000 tokens), causing mid-generation truncation and quality decay in the second half. Validated that the Skill system supports multiple sequential Write calls within a single invocation (precedent: canvas-design, Mck-speech-design-skill).

Changes from v9.1.1:
1. **File Output Strategy rewritten as Two-Stage Sequential Generation:** Stage 1 writes 学员手册 (~1,500 tokens), Stage 2 writes 学习参考 (~3,000 tokens). Each stage independently within sweet spot.
2. **CRITICAL save-to-disk directives added:** Borrowed from Mck-speech-design-skill's proven pattern — explicit "MUST save via Write tool before proceeding" gates between stages.
3. **Token targets per stage:** Soft guidance added (Stage 1: ~1,500 tokens, Stage 2: ~3,000 tokens) to anchor generation length.

**Token impact on SKILL.md:** ~2,700-3,000 tokens → ~2,800-3,100 tokens. Slight increase from stage instructions, justified by eliminating truncation risk.

### v9.1.1 (2026-04-05)
**Patch release: targeted fixes from RUBRIC scoring (4.40 → target ≥4.5).**

Three fixes based on root cause analysis of Mark 2:1-17 benchmark scoring:
1. **Red Line #4 — pushback requirement:** Added "Include at least one likely pushback from the other party and a response strategy" to Concrete Action specification. Addresses Concrete Action score 4.0 (missing counterparty reaction).
2. **Red Line #5 — anti-long-term-payoff clause:** Added "Do not imply that doing the right thing will pay off long-term — not even framed as 'risk management.'" Addresses Worst-Case Honesty score 4.5 (residual silver lining).
3. **C Study Reference — structural requirement:** Added Selection Rationale + Transformation Claim for each Correlation set. Addresses Study Reference Depth score 4.0 (C-section references lacked justification for why they were chosen).

**Token impact:** ~2,700-3,000 tokens → ~2,700-3,000 tokens. Negligible increase (~80-100 tokens).

### v9.1.0 (2026-04-04)
**Patch release: self-audit fixes + file output strategy.**

Changes from v9.0.0:
1. **Red Lines wording fix:** "Verify each one before outputting" → "Every sentence you generate must comply" — aligns with auto-regressive execution model (P3)
2. **Output Strategy rewritten:** Removed hard-coded "12 verses" threshold. Replaced with file-based delivery: Skill generates two files (学员手册.md + 学习参考.md) automatically, no user intervention needed
3. **Pre-scan format simplified:** Blockquote → single inline line for cross-platform rendering consistency
4. **Three Lenses format:** Table → list (saves ~35 tokens in prompt, P8)
5. **Length anchoring bilingual:** Added Chinese character targets alongside English word counts (P5 + P10)
6. **Scripture Reading Guide completed:** Added Prophetic and Law genre reading instructions (was missing 2 of 5 genres)
7. **Correlation nuanced:** "Prioritize redemptive-historical" → "Consider redemptive-historical when appropriate; for Wisdom literature, creation-order connections may be more fitting"
8. **Benchmark examples expanded:** 1 → 3 examples covering Manager/Peer/IC perspectives to prevent over-fitting
9. **Track B dialogue depth:** Added explicit exchange counting rules and topic-switch reset
10. **Series learning:** Added minimal handling for "第一次学习" / "session N" signals
11. **Description bilingual:** Added Chinese trigger keywords to frontmatter description for better cross-language skill matching
12. **Greeting anchored:** Added "3-5 sentences" length target and "end with open question" structure

**Token impact:** ~2,600-2,900 tokens (v9.0.0) → ~2,700-3,000 tokens (v9.1.0). Slight increase due to 3 benchmark examples and bilingual length targets, offset by format optimizations.

### v9.0.0 (2026-04-04)
**Major restructure based on dual-panel audit.**

Changes from v8.0.0:
1. **Content reordering:** Quality Red Lines moved to top of document (primacy effect)
2. **Three Lenses replaces three characters:** Shepherd/Scholar/Elder → Gospel Lens/Text Lens/Workplace Lens. Functional naming eliminates role boundary confusion
3. **Tension trigger conditions:** Explicit criteria for when to surface lens divergence, replacing the ambiguous "naturally integrate but MUST surface tension" instruction pair
4. **Pre-computation made visible:** Silent pre-computation replaced with visible "Passage Profile" block that enters the context and genuinely shapes generation
5. **Self-Check compressed:** 11-item checklist → 5 Quality Red Lines at document top
6. **Anti-pattern ratio rebalanced:** Removed specific bad examples to avoid negative priming; retained benchmark good example
7. **Output segmentation added:** Explicit instructions for splitting long outputs with bridge summaries
8. **Length anchoring added:** Soft word-count targets for each Study Reference component
9. **Scripture Reading Guide added:** Genre-matched reading instructions before DUCA questions
10. **Correlation upgraded:** Explicit prioritization of redemptive-historical connections over keyword matching
11. **Track B expanded:** Added dialogue depth management, Socratic questioning progression, and boundary escalation protocols
12. **Greeting simplified:** Verbose bilingual templates → concise intent description (LLM generates appropriate greeting)
13. **Semantic deduplication:** Removed repeated rules across sections
14. **Bilingual term labels:** Key structural terms given both English and Chinese labels
15. **Workplace role diversity:** Expanded role examples beyond corporate hierarchy to include co-founders, partners, service recipients, etc.

**Token impact:** ~3,500-4,000 tokens (v8.0.0) → ~2,600-2,900 tokens (v9.0.0). ~25% reduction.

### v8.0.0 (previous)
- Added Internal Pre-computation (Genre Scan, Core Tension, Risk Assessment)
- Restructured output into Group Handout + Study Reference
- Added Common Pitfalls & Corrections
- Added multi-layer Idol Exposure requirement
- Added Deeper Exploration follow-up questions

### v7.x (earlier)
- Three characters: 属灵职场导师 (Spiritual Workplace Mentor), Scholar, Shepherd
- Facilitator's Guide format (replaced by Study Reference in v8)
- Navigation/derailment strategies (absorbed into Common Pitfalls in v8+)

---

## 5. Testing Protocol

When releasing a new version of SKILL.md:

### 5.1 Regression Test
Generate outputs for these three benchmark passages and score with RUBRIC.md:
1. **Narrative:** Mark 2:1-17 (baseline passage, most tested)
2. **Epistle:** Ephesians 6:5-9 (tests workplace-specific application)
3. **Poetry/Wisdom:** Psalm 73 (tests non-narrative genre handling)

All three must score ≥ 3.5 (Strong tier) to pass.

### 5.2 A/B Comparison
For each benchmark passage, generate outputs from both the old and new SKILL.md versions. Score both with RUBRIC.md. The new version must not regress on any dimension by more than 0.5 points.

### 5.3 Edge Case Tests
- Passage > 20 verses (test auto-split)
- Highly controversial passage (e.g., 1 Timothy 2:11-15) — test theological guardrails
- User provides no specific passage, just a workplace dilemma — test Track B routing
- User writes in unsupported language — test language fallback

---

## 6. Future Roadmap

| Priority | Item | Status |
|----------|------|--------|
| P1 | Generate and score benchmark outputs for v9.2.0 | Pending |
| P1 | Add scored benchmark outputs to `outputs/` directory | Pending |
| P2 | Add difficulty auto-adaptation (dense theological passages get fewer questions, more depth) | Planned for v10 |
| P2 | Add series mode — full cross-session theme accumulation (v9.1 has minimal handling) | Planned for v10 |
| P3 | Automated evaluation pipeline (LLM-as-judge using RUBRIC.md) | Planned for v10+ |
