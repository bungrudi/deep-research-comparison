# Deep Research Evaluation Rubric

**Designed by:** 3-model panel debate (Opus 4.6, Gemini 3.1 Pro, GPT 5.4)
**Date:** 2026-04-04
**Purpose:** Score deep research output from Gemini Deep Research, ChatGPT Deep Research, and Grok Heavy across 5 topics (15 total outputs).

## Scoring: 7 Dimensions, 1-10 Scale Each (Max 70)

### Scoring Note
When a claim is unsupported but possibly true, penalize primarily under **Evidence Traceability** (Dim 3), not **Claim Accuracy** (Dim 2) — unless the claim is also misleading or materially unreliable.

---

## Dimension 1: Task Fidelity & Coverage
**Phase:** The Prompt

Did the agent answer the specific question with all constraints? Did it cover all important facets while prioritizing what matters most? Penalize scope drift, missing sub-topics, and poor attention allocation.

| Score | Description |
|-------|-------------|
| 1-3 | Misses core constraints or major facets of the topic |
| 4-6 | Addresses the prompt but misses nuances or misproportions attention across sub-topics |
| 7-8 | Covers major dimensions, respects all constraints, prioritizes well |
| 9-10 | Flawless adherence to prompt, comprehensive yet focused, strong research judgment on what matters most |

---

## Dimension 2: Claim Accuracy & Factual Reliability
**Phase:** The Reasoning

Are substantive claims correct, non-misleading, and consistent with cited evidence? Penalize hallucinated facts, exaggerations, and misinterpretations of source material.

| Score | Description |
|-------|-------------|
| 1-3 | Multiple false, exaggerated, or unsupported claims |
| 4-6 | Mostly correct but notable errors, overreach, or shaky interpretations |
| 7-8 | Accurate on all important claims; minor issues do not change conclusions |
| 9-10 | Highly reliable, precise, and careful with zero material factual errors |

---

## Dimension 3: Evidence Traceability & Citation Integrity
**Phase:** The Search

Can claims be traced to specific, verifiable sources? Are links real and functional? Heavy penalty for hallucinated URLs, dead links, or citations that don't actually support the claim they're attached to.

| Score | Description |
|-------|-------------|
| 1-3 | Citations absent, vague, hallucinated, or detached from claims |
| 4-6 | Some claim-level support but important assertions remain unverifiable |
| 7-8 | Most consequential claims clearly supported by working, relevant citations |
| 9-10 | Precise, consistent evidence-to-claim linkage; zero dead or fabricated links |

---

## Dimension 4: Source Quality & Appropriateness
**Phase:** The Search

Are sources credible, relevant, and fit-for-purpose for the topic? Appropriate mix of primary and secondary sources? Penalize SEO spam, over-reliance on aggregators (Wikipedia, generic news), and irrelevant sources.

| Score | Description |
|-------|-------------|
| 1-3 | Heavy reliance on low-credibility, irrelevant, or weak secondary sources |
| 4-6 | Mixed quality; some strong sources alongside questionable or poorly chosen ones |
| 7-8 | Generally strong, relevant sources appropriate to the question |
| 9-10 | Excellent source selection with clear preference for authoritative or primary material |

---

## Dimension 5: Analytical Synthesis & Insight
**Phase:** The Reasoning

Does the output integrate evidence into higher-order conclusions rather than summarizing source-by-source? Does it cross-reference, identify trends, surface tradeoffs, and produce non-obvious insights?

| Score | Description |
|-------|-------------|
| 1-3 | Concatenated summaries with no interpretation — a "book report" |
| 4-6 | Some synthesis but limited cross-source analysis or insight generation |
| 7-8 | Clear cross-source synthesis with meaningful interpretation and nuance |
| 9-10 | Exceptional analytical lift — resolves tensions, surfaces tradeoffs, produces genuinely non-obvious insights |

---

## Dimension 6: Epistemic Honesty & Conflict Resolution
**Phase:** The Reasoning

Does the output distinguish established fact from inference, contested claims, and speculation? When sources conflict, does it investigate the discrepancy and evaluate source methodology/bias, rather than silently averaging or picking one?

| Score | Description |
|-------|-------------|
| 1-3 | Overstated certainty; contested issues presented as settled fact |
| 4-6 | Some caveats present but incomplete treatment of uncertainty or conflicting data |
| 7-8 | Appropriately calibrated confidence; acknowledges open questions and limitations |
| 9-10 | Exemplary — evaluates source methodology and bias, notes what cannot be known, investigates discrepancies |

---

## Dimension 7: Information Architecture & Signal Density
**Phase:** The Output

Is the output structured for efficient human consumption? High signal-to-noise ratio, logical flow, scannability. This is not about visual polish — it's about cognitive load and insight-per-word.

| Score | Description |
|-------|-------------|
| 1-3 | Wall of text, disorganized narrative, repetitive sections, buried conclusions |
| 4-6 | Standard essay format with decent headings; readable but requires parsing paragraphs for key data |
| 7-8 | Well-structured with clear hierarchy, logical flow, and easy navigation |
| 9-10 | Expertly organized — executive summaries, logical taxonomies, comparative tables, maximum insight density |

---

## Scoring Template

```
| Dimension | Gemini | ChatGPT | Grok |
|-----------|--------|---------|------|
| 1. Task Fidelity & Coverage | /10 | /10 | /10 |
| 2. Claim Accuracy | /10 | /10 | /10 |
| 3. Evidence Traceability | /10 | /10 | /10 |
| 4. Source Quality | /10 | /10 | /10 |
| 5. Analytical Synthesis | /10 | /10 | /10 |
| 6. Epistemic Honesty | /10 | /10 | /10 |
| 7. Information Architecture | /10 | /10 | /10 |
| **TOTAL** | **/70** | **/70** | **/70** |
```
