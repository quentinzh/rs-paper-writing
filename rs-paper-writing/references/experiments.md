# Experiments Writing Guide

## Goal

Write the Experiments section so reviewers can see that the method is effective, fairly compared, statistically credible, and practical enough for the claimed setting.

Focus on six RS-specific dimensions:

1. metrics by task;
2. baseline grouping;
3. statistical significance;
4. efficiency, memory, and latency;
5. LLM-based recommendation validity and grounding;
6. fairness/debiasing metrics and accuracy-fairness trade-off.

In addition, the experimental setup must be literature-backed: use recent high-quality papers to show that the selected datasets, compared models, metrics, and common hyperparameters follow accepted practice.

## Experiment Questions

Organize experiments around research questions.

Examples:

```text
RQ1: Does the proposed method improve the main recommendation metric?
RQ2: Which module contributes to the improvement?
RQ3: What is the efficiency or resource cost?
RQ4: For LLM-based recommendation, how often are generated outputs valid and correctly grounded?
RQ5: For fairness/debiasing, how does the method trade off accuracy and fairness?
```

## Literature-Backed Setup Justification

The goal is to convince reviewers that the experimental setup follows accepted practice rather than being specially chosen to favor the proposed method.

For each important setup choice, cite recent high-quality recommender-system papers showing that related work uses similar choices.

Cover four setup types:

1. Datasets:
   - cite papers that use the same datasets or datasets with the same role in the task.
2. Compared models:
   - cite papers showing that the selected baselines are standard, strong, recent, or directly related.
3. Metrics:
   - cite papers showing that the metrics are commonly used for the task.
4. Common hyperparameters:
   - cite papers or official baselines that use similar values for learning rate, embedding size, batch size, number of epochs, optimizer, or other common training settings.

Citation priority:

1. Prefer papers from the most recent year.
2. If not enough evidence is available, use papers from the past two years.
3. If still not enough evidence is available, use papers from the past three years.
4. Prefer CCF-A conferences or journals and Chinese Academy of Sciences Q1 journals.

Do not invent citation support. If no suitable citation is available, write `[NEEDS CITATION]` and make the setup justification more conservative.

Sentence patterns:

```text
We use [dataset] because it is widely adopted for [task], following recent studies such as [citations].
```

```text
We compare with [baseline group] because these methods represent [standard/recent/strong] solutions for [task], as used in [citations].
```

```text
We report [metric] because it is commonly used to evaluate [target capability] in recent [task] studies [citations].
```

```text
Following recent work [citations], we set [hyperparameter] to [value].
```

## Metrics by Task

Choose metrics that match the task.

1. Top-K ranking or retrieval:
   - Recall@K, NDCG@K, Hit Rate@K, MRR@K, Precision@K.
2. CTR/CVR or binary preference prediction:
   - AUC, GAUC, LogLoss, calibration metrics when relevant.
3. Sequential recommendation:
   - HR@K, NDCG@K, MRR@K, Recall@K, plus sequence-specific analysis when needed.
4. LLM-based recommendation:
   - ranking metrics plus valid generation rate, grounding success rate, exact item match, invalid output rate, and decoding cost when relevant.
5. Fairness/debiasing:
   - task accuracy metrics plus fairness, bias, diversity, exposure, coverage, or popularity-bias metrics.

Always label metric direction in tables, such as `NDCG@10 (higher is better)` or `MGU@10 (lower is better)`.

## Baseline Grouping

Group baselines by method family so reviewers understand comparison coverage.

Possible groups:

1. traditional recommenders;
2. sequential recommendation models;
3. graph-based models;
4. contrastive/self-supervised models;
5. LLM-based recommenders;
6. generative recommendation models;
7. fairness/debiasing methods;
8. causal recommendation methods;
9. task-specific SOTA methods.

When writing baselines, explain why each group is relevant:

```text
We compare with three groups of baselines: [group 1], [group 2], and [group 3]. These groups cover [reason].
```

Do not hide the strongest direct competitor.

For each baseline group, cite recent papers showing that the methods are standard or competitive for the task.

## Statistical Significance

Report statistical credibility when the paper claims improvement.

Recommended practices:

1. run repeated experiments when feasible;
2. report mean and standard deviation when applicable;
3. mark statistically significant improvements in tables;
4. describe the test used, such as paired t-test, bootstrap test, or randomization test;
5. avoid claiming meaningful gains from tiny, unstable differences.

Sentence pattern:

```text
We repeat each experiment [N] times and report the average result. Improvements marked with [symbol] are statistically significant under [test] with p < [threshold].
```

## Efficiency, Memory, and Latency

Use this subsection when the method changes model size, training, inference, decoding, reranking, or serving cost.

Report relevant costs:

1. parameter count;
2. training time;
3. GPU memory;
4. inference latency;
5. throughput;
6. decoding cost, beam size, sample size, or prompt length for LLM-based recommendation.

Connect cost to the claim:

```text
Because [Name] introduces [component], we report [cost metric] to quantify its overhead.
```

## LLM-Based Recommendation Validity and Grounding

For LLM-based recommendation, reviewers need to know whether generated outputs become valid recommendations.

Report or describe:

1. generated output format;
2. constrained decoding or unrestricted generation;
3. grounding or matching protocol;
4. invalid generation rate;
5. grounding success rate;
6. exact item match rate when appropriate;
7. how invalid or unmatched outputs are handled.

Do not report only ranking metrics if generated outputs may be invalid.

## Fairness / Debiasing Trade-Off

For fairness/debiasing papers, report both utility and fairness.

Include:

1. recommendation utility metrics such as HR, NDCG, Recall, AUC, or LogLoss;
2. fairness or bias metrics;
3. direction of each fairness metric;
4. trade-off table or curve when the method has a trade-off hyperparameter;
5. discussion of whether fairness gains come with unacceptable utility loss.

Sentence pattern:

```text
[Name] reduces [bias/fairness metric] while maintaining competitive [utility metric], indicating a better accuracy-fairness trade-off.
```

## Table and Figure Rules

1. One table should communicate one message.
2. Group baselines by family.
3. Label metric directions.
4. Keep numeric precision consistent.
5. Highlight best and second-best results with restraint.
6. Use captions to state setting and notation, not long interpretation.
7. For trade-offs, use a figure or table that shows both utility and fairness.

## Quality Checklist

1. Metrics match the task.
2. Baselines are grouped and include strong competitors.
3. Datasets, baselines, metrics, and common hyperparameters are justified with recent high-quality citations.
4. Significance or variance is reported when improvements are claimed.
5. Efficiency, memory, or latency is reported when the method changes cost.
6. LLM-based recommendation includes validity and grounding analysis when needed.
7. Fairness/debiasing includes both fairness metrics and utility metrics.
8. Abstract and Introduction claims are supported by reported numbers.
