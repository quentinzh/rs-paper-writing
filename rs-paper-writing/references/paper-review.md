# Paper Review Guide

## Goal

Use an adversarial recommender-system reviewer checklist to detect rejection risks early and revise before submission.

## Critical Rule

Every major claim, especially in Abstract and Introduction, must be:

1. technically correct;
2. supported by experiments, analysis, or citations;
3. bounded to the paper's actual setting.

If a claim is unsupported, add evidence or weaken/remove the claim.

## What Usually Gets an RS Paper Accepted

1. A meaningful recommender-system problem.
2. A clear technical contribution.
3. Strong comparison against relevant baselines.
4. Task-appropriate metrics.
5. Complete ablations or analysis.
6. Clear writing and reproducible method details.

## Common Rejection Risks

| Dimension | Failure Signals |
| --- | --- |
| Insufficient contribution | The idea is a predictable combination of known components; the failure case is not meaningful; novelty is only an implementation choice. |
| Unclear writing | Task setting is ambiguous; Method variables are undefined; modules lack motivation; LLM outputs are not mapped to valid items. |
| Weak empirical effect | Gains are tiny, inconsistent, or not statistically credible; improvements appear only on weak baselines. |
| Incomplete evaluation | Missing strong competitors; missing task-specific metrics; missing ablations; missing efficiency analysis when the method increases cost; dataset, baseline, metric, or common hyperparameter choices are not justified by recent high-quality literature. |
| LLM-based recommendation risk | Invalid generation is not measured; grounding/matching is unclear; decoding cost is hidden; prompt/output format is under-specified. |
| Fairness/debiasing risk | Fairness metric is unclear; accuracy-fairness trade-off is missing; bias source is not connected to the proposed method. |
| Method design risk | The method adds complexity without clear benefit; assumptions are unrealistic; objective does not match the claimed problem. |

Do not require online/product value unless the paper itself claims deployment or online impact.

## Five-Dimension Self-Review

### 1. Contribution

1. What new knowledge does the paper give to RS readers?
2. Is the target problem meaningful for the claimed venue?
3. Is the idea non-obvious beyond standard practice?
4. Is the contribution type clear: task, model, objective, algorithm, analysis, metric, or evaluation protocol?
5. Are all contribution bullets supported?

### 2. Writing Clarity

1. Is the task understandable in the first page?
2. Are all Method variables defined?
3. Does each module have motivation, design, and advantage?
4. Are terms consistent across sections?
5. Does each paragraph carry one message?

### 3. Experimental Strength

1. Are improvements meaningful and stable?
2. Are strong baselines included?
3. Are metrics appropriate for the task?
4. Is statistical significance or variance reported when needed?
5. Are ablations tied to claimed modules?

### 4. Evaluation Completeness

1. Are baselines grouped clearly?
2. Are task-specific metrics complete?
3. Are datasets, compared models, metrics, and common hyperparameters supported by recent CCF-A or CAS-Q1 papers, preferably from the past one to three years?
4. Is efficiency, memory, or latency reported when relevant?
5. For LLM-based recommendation, are generation validity and grounding evaluated?
6. For fairness/debiasing, is the accuracy-fairness trade-off shown?

### 5. Method Design Soundness

1. Does the method solve the stated problem directly?
2. Is the objective aligned with the recommendation task?
3. Are assumptions explicit?
4. Does added complexity have measurable benefit?
5. Could reviewers argue that a simpler baseline explains the gains?

## Adversarial Workflow

1. Read the paper as a skeptical reviewer.
2. Answer every question above with evidence from the paper.
3. Mark each item as `pass`, `needs revision`, or `needs new evidence`.
4. Revise claims, writing, experiments, or method scope accordingly.
5. Repeat until no major rejection risk remains.
