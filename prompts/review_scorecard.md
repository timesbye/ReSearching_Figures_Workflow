# Review Scorecard Template

> **来源**：PaperOrchestra 的 AgentReview 结构化评审记分卡

Use this template to produce structured, quantitative review scores for each paper version. This enables the review-rollback mechanism to make objective accept/reject decisions.

## Scoring Dimensions

| Dimension | Weight | Score (1-10) | Notes |
|-----------|--------|--------------|-------|
| **Clarity** | 15% | | Is the writing clear and well-organized? |
| **Motivation** | 15% | | Is the problem well-motivated? |
| **Novelty** | 20% | | Is the contribution genuinely new? |
| **Method Soundness** | 20% | | Is the method technically correct? |
| **Experimental Rigor** | 15% | | Are experiments comprehensive and fair? |
| **Significance** | 10% | | Will this impact the field? |
| **Reproducibility** | 5% | | Can results be reproduced? |

## Weighted Score Calculation

```text
Total Score = Clarity × 0.15 + Motivation × 0.15 + Novelty × 0.20 + Method_Soundness × 0.20 + Experimental_Rigor × 0.15 + Significance × 0.10 + Reproducibility × 0.05
```

## Scorecard Template

```markdown
# Review Scorecard

## Paper Info
- Title:
- Version:
- Reviewer role:
- Date:

## Dimension Scores

| Dimension | Weight | Score (1-10) | Justification |
|-----------|--------|--------------|---------------|
| Clarity | 15% | | |
| Motivation | 15% | | |
| Novelty | 20% | | |
| Method Soundness | 20% | | |
| Experimental Rigor | 15% | | |
| Significance | 10% | | |
| Reproducibility | 5% | | |
| **Weighted Total** | **100%** | **/10** | |

## Issue Summary

### Major Issues
1. [Issue description + affected dimension]
2. [Issue description + affected dimension]

### Minor Issues
1. [Issue description]
2. [Issue description]

## Suggested Revisions
1. [Specific revision suggestion → expected dimension improvement]
2. [Specific revision suggestion → expected dimension improvement]

## Overall Assessment
- Recommendation: Accept / Minor Revision / Major Revision / Reject
- Confidence: High / Medium / Low
- Key strength:
- Key weakness:
```

## Multi-Reviewer Aggregation

When running multi-perspective review (5 reviewers), aggregate scores as follows:

```markdown
# Aggregated Review Scorecard

| Dimension | R1 (Method) | R2 (Domain) | R3 (Writing) | R4 (Rigor) | R5 (Novelty) | Mean | Std |
|-----------|-------------|-------------|---------------|-------------|-------------|------|-----|
| Clarity | | | | | | | |
| Motivation | | | | | | | |
| Novelty | | | | | | | |
| Method Soundness | | | | | | | |
| Experimental Rigor | | | | | | | |
| Significance | | | | | | | |
| Reproducibility | | | | | | | |
| **Weighted Total** | | | | | | | |

## AC Meta-Review Decision
- Consensus strengths:
- Consensus weaknesses:
- Key disagreements:
- Final recommendation:
- Decision rationale:
```

## Version Comparison (for rollback mechanism)

```markdown
# Version Comparison

| Dimension | Version [N] | Version [N+1] | Delta |
|-----------|-------------|----------------|-------|
| Clarity | | | |
| Motivation | | | |
| Novelty | | | |
| Method Soundness | | | |
| Experimental Rigor | | | |
| Significance | | | |
| Reproducibility | | | |
| **Weighted Total** | | | **+/-** |

**Decision**: Accept modification / Rollback to version [N]
**Reason**:
```
