# Quality Rubric — Workplace Bible Study Mentor

> Version: 1.0.0 | Aligned with SKILL.md v9.0.0
> Purpose: Evaluate output quality for human review, A/B testing between versions, or automated LLM-as-judge evaluation.

## How to Use This Rubric

**For human evaluation:** Read the generated output, score each dimension below (0-5), compute the weighted total.

**For LLM-as-judge:** Inject this file as system prompt, provide the generated output as user input, and ask the LLM to score each dimension with justification.

**For A/B testing:** Generate outputs from two SKILL.md versions using the same Scripture passage, score both with this rubric, compare totals.

---

## Scoring Dimensions

### 1. Application Scenario Quality (Weight: 25%)

| Score | Criteria |
|-------|----------|
| 0 | No workplace scenario; pure faith-life reflection |
| 1 | Has a workplace setting but no conflict of interest |
| 2 | Has a conflict but only one "obviously right" option |
| 3 | Genuine two-sided dilemma, but scenario is vague (no specific roles) or too long (>4 sentences) |
| 4 | Genuine dilemma + specific roles + concise (2-4 sentences), but weak connection to the passage |
| 5 | Genuine dilemma + specific roles + concise + question explicitly requires grounding response in the passage being studied |

**Red flag check:** Can the question be answered with "pray more / surrender to God"? If yes, cap at 1.

---

### 2. Study Reference Depth (Weight: 20%)

| Score | Criteria |
|-------|----------|
| 0 | No Study Reference provided |
| 1 | Generic spiritual teaching unconnected to the specific question |
| 2 | Addresses the question but from a single perspective only |
| 3 | Multiple perspectives present but no genuine tension or differentiation |
| 4 | Integrated multi-lens analysis with at least one labeled tension point |
| 5 | Rich multi-lens analysis + tension labeled + Common Pitfalls are passage-specific (not generic) + Deeper Exploration opens genuinely new angles |

---

### 3. Idol Exposure Quality (Weight: 15%)

| Score | Criteria |
|-------|----------|
| 0 | No idol exposure |
| 1 | Generic label only (e.g., "pride" or "fear") |
| 2 | One specific idol named but no layering |
| 3 | Two layers identified (surface + deeper) |
| 4 | Three layers (surface → deeper → root) but root idol feels formulaic |
| 5 | Three layers with the root idol being genuinely surprising and specific to this scenario — the reader feels "exposed" |

---

### 4. Concrete Action Quality (Weight: 15%)

| Score | Criteria |
|-------|----------|
| 0 | No concrete action; only "adjust your mindset" |
| 1 | Vague action direction without specifics |
| 2 | Specific action but no talk track (no exact words) |
| 3 | Includes a talk track but uses religious language that would sound odd in a secular workplace |
| 4 | Talk track in secular workplace language + actionable tomorrow |
| 5 | Talk track in secular workplace language + actionable tomorrow + accounts for likely pushback or follow-up from the other party |

---

### 5. Worst-Case Scenario Honesty (Weight: 10%)

| Score | Criteria |
|-------|----------|
| 0 | Not addressed |
| 1 | Mentioned but immediately softened with "God will make it up to you" |
| 2 | Acknowledges loss but pivots quickly to "silver lining" |
| 3 | Honestly names the worldly cost without fairy-tale resolution |
| 4 | Names the cost + grounds the response in theology of the cross (faithfulness has intrinsic worth) |
| 5 | Names the cost + theology of the cross + avoids both despair and false hope — the reader feels sobered but not crushed |

---

### 6. Discovery & Understanding Question Quality (Weight: 10%)

| Score | Criteria |
|-------|----------|
| 0 | Questions are trivial or off-topic |
| 1 | Questions exist but are really interpretation disguised as observation (D) or have obvious Sunday-school answers (U) |
| 2 | Adequate questions but generic — could apply to many passages |
| 3 | Questions are passage-specific and require genuine engagement with the text |
| 4 | Questions embed relevant historical/linguistic context that changes the reader's understanding |
| 5 | Questions create at least one genuine "I never noticed/thought about that" moment — the reader's default interpretation is challenged |

---

### 7. Correlation Quality (Weight: 5%)

| Score | Criteria |
|-------|----------|
| 0 | No cross-references |
| 1 | Verse-piling — multiple references listed without explanation |
| 2 | References explained but only share a keyword, not a deeper connection |
| 3 | References genuinely illuminate the passage with a new dimension |
| 4 | References reveal a redemptive-historical pattern (creation → fall → redemption → consummation) |
| 5 | Redemptive-historical connection + effectively guards against the specific misreading risk flagged in the Pre-scan |

---

## Composite Score Calculation

| Dimension | Weight | Score (0-5) | Weighted |
|-----------|--------|-------------|----------|
| 1. Application Scenario | 25% | | |
| 2. Study Reference Depth | 20% | | |
| 3. Idol Exposure | 15% | | |
| 4. Concrete Action | 15% | | |
| 5. Worst-Case Honesty | 10% | | |
| 6. D & U Questions | 10% | | |
| 7. Correlation | 5% | | |
| **Total** | **100%** | | **/5.0** |

### Quality Tiers

| Tier | Score Range | Interpretation |
|------|-----------|----------------|
| ⭐⭐⭐⭐⭐ Exceptional | 4.5 - 5.0 | Ready to use as-is; could serve as a benchmark example |
| ⭐⭐⭐⭐ Strong | 3.5 - 4.4 | Minor improvements possible but usable for group study |
| ⭐⭐⭐ Adequate | 2.5 - 3.4 | Needs revision in specific dimensions before use |
| ⭐⭐ Weak | 1.5 - 2.4 | Significant gaps; likely generated from an under-specified prompt |
| ⭐ Failing | 0.0 - 1.4 | Does not meet minimum quality standards |

---

## Quick-Check Flags

In addition to scoring, flag any of these critical failures (any single flag = automatic cap at Tier ⭐⭐ regardless of score):

- [ ] An Application question can be answered with "just pray more"
- [ ] Idol Exposure is single-layer only
- [ ] No specific talk track provided (no exact words)
- [ ] Worst-Case Scenario includes a fairy-tale ending
- [ ] Scripture is fabricated or misattributed
- [ ] Cross-references are pure verse-piling with no explanation
- [ ] Output language does not match user's selected language

---

## Benchmark Samples

### Benchmark: 5-Star Application Question (Mark 2:1-17)

**Question:**
"Your subordinate has underperformed for two quarters due to a family crisis. Company policy requires a PIP. Your boss hints it's time to act. Based on how Jesus prioritizes the paralytic's deeper need (forgiveness) over his surface need (healing), what do you do — and where is the boundary between grace and organizational responsibility?"

**Why it scores 5:**
- Specific conflict: grace vs. policy compliance
- Named roles: subordinate, boss, you
- Concise: 3 sentences
- Explicitly requires grounding in the passage

### Benchmark: 1-Star Application Question (anti-example, for evaluator calibration only)

"Have you experienced God's grace at work? Please share a time when you felt God's presence in a difficult situation."

**Why it scores 1:**
- No conflict of interest
- No specific roles
- Answerable with a generic testimony
- No connection to any specific passage
