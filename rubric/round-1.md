# Rubric Design — Round 1: Initial Proposals

## Opus 4.6 Proposal (8 dimensions)
1. Factual Accuracy & Verifiability
2. Citation Quality & Source Diversity
3. Depth of Analysis
4. Breadth of Coverage
5. Logical Coherence & Structure
6. Recency & Relevance
7. Actionability & Specificity
8. Presentation Quality

## Gemini 3.1 Pro Proposal (5 dimensions)
**Key critique:** Opus's rubric evaluates essay quality, not agentic research quality. Wants to focus on AI-specific failure modes.

1. **Prompt Fidelity & Scope Mastery** — Did the agent answer the actual question with all constraints?
2. **Source Integrity & Citation Precision** — Are sources real, high-quality, no hallucinated links?
3. **Epistemic Rigor & Conflict Resolution** — Handles contradictory info, evaluates source bias, acknowledges unknowns
4. **Depth of Synthesis & Novel Insight** — Beyond summarization to net-new understanding
5. **Information Architecture & Density** — Structured for human consumption, high insight-per-word

**Removed:** Presentation Quality (all agents format well), Recency (topic-dependent), Actionability (assumes business context)

## GPT 5.4 Proposal (8 dimensions)
**Key critique:** Opus gives equal weight to unequal concerns. Biggest omission is epistemic honesty.

1. **Claim Accuracy & Factual Reliability** — Correct, non-misleading, consistent with evidence
2. **Evidence Traceability** — Claims anchored to specific, verifiable evidence
3. **Source Quality & Appropriateness** — Credible, relevant, fit-for-purpose sources
4. **Analytical Synthesis & Insight** — Cross-source integration, non-obvious insights
5. **Coverage & Research Judgment** — Important facets covered with proper prioritization
6. **Uncertainty Handling & Epistemic Honesty** — Distinguishes fact from inference, acknowledges ambiguity
7. **Task Fulfillment & Decision Utility** — Actually answers the prompt with useful takeaways
8. **Organization & Readability** — Clarity and navigability (downweighted)

## Convergence Points
- Factual Accuracy is #1 priority (all three)
- Depth/Synthesis is critical (all three)
- Presentation should be downweighted (all three)
- Recency shouldn't be standalone (Gemini + GPT)
- **Missing from Opus original:** Epistemic honesty (Gemini + GPT), Task/prompt adherence (Gemini + GPT), Evidence traceability (GPT)

## Disagreements
- Number of dimensions: 5 (Gemini) vs 8 (Opus, GPT)
- AI-specific failure modes like dead links (Gemini emphasizes, others don't)
- Whether to split citations into traceability + source quality (GPT) or keep unified (Opus, Gemini)
