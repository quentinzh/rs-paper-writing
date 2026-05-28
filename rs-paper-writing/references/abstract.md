# Abstract Writing Guide

## Goal

Write a recommender-system abstract that lets reviewers identify the task, problem, method, and evidence in one pass.

## Default Logic

Use this logic unless the target venue or user request requires otherwise:

1. State the recommendation task and why it matters.
2. State the current paradigm or representative solution.
3. State the key unsolved problem.
4. State the proposed model, method, framework, objective, or evaluation protocol.
5. State the main technical idea in plain language.
6. State the experimental evidence within the actual scope of results.

## RS-Specific Requirements

1. Name the task precisely: sequential recommendation, next-item prediction, CTR/CVR prediction, retrieval, ranking, LLM-based recommendation, fairness-aware recommendation, debiasing, causal recommendation, or another task.
2. For LLM-based recommendation, mention the recommendation output form when it matters: item title, semantic ID, ranked list, candidate reranking, or generated explanation/reasoning.
3. For fairness/debiasing/causal work, state the target bias or causal problem, not only the general goal of trustworthy recommendation.
4. For sequential recommendation, state the user-behavior issue, such as evolving interest, sparse histories, long-range dependency, or short-term intent.
5. Use evidence-backed verbs and avoid broad deployment claims unless the experiments support them.

## Pre-Writing Questions

Answer these before writing:

1. What exact recommendation problem does this paper solve?
2. Which existing paradigm is the paper contrasting against?
3. What failure of the existing paradigm matters to reviewers?
4. What is the proposed technical object and its stable noun?
5. Why should the proposed object solve the problem?
6. What experiment sentence can be safely supported?
7. Which claim must be weakened because evidence is missing?

## Version 1: Challenge to Method

Use when the paper has one central technical challenge.

Structure:

1. Task and importance.
2. Existing paradigm and limitation.
3. Proposed method.
4. Main design.
5. Experimental evidence.

Skeleton:

```text
[Task] is a core problem in recommender systems because [reason].
Existing [method type] methods typically [mechanism], but they struggle with [problem] because [technical reason].
To address this problem, we propose [Name], a [object noun] for [task].
[Name] [main technical idea] to [benefit].
Experiments on [datasets/settings] show that [Name] improves [metrics/properties] over [baseline group].
```

## Version 2: Diagnosis to Method

Use for LLM-based recommendation, fairness/debiasing, causal recommendation, or any paper that first identifies a failure mechanism.

Structure:

1. Task.
2. Existing objective or framework.
3. Diagnosed failure.
4. Proposed fix.
5. Evidence.

Skeleton:

```text
[Task] has recently been addressed by [framework/objective].
However, we find that [framework/objective] can [failure] under [condition], leading to [negative consequence].
To mitigate this issue, we propose [Name], which [core mechanism].
[Name] [module/design 1] and [module/design 2], enabling [benefit].
Experiments demonstrate that [Name] improves [main metrics] while [secondary property, e.g., fairness/diversity/efficiency].
```

## Version 3: Multiple Contributions

Use when the paper has several technical contributions.

Structure:

1. Task and problem.
2. Contribution 1 and its advantage.
3. Contribution 2 and its advantage.
4. Contribution 3 if needed.
5. Evidence.

Rules:

1. Pair each contribution with a concrete advantage.
2. Avoid listing many modules without explaining why they matter.
3. Keep the abstract short enough for non-specialists at the target venue.

## Final Experiment Sentence

The final sentence should be factual and bounded:

```text
Experiments on [datasets] show that [Name] outperforms [baseline group] on [metrics].
```

For fairness/debiasing:

```text
Experiments show that [Name] improves [fairness/bias metric] while preserving competitive [accuracy/ranking metric].
```

For LLM-based recommendation:

```text
Experiments show that [Name] improves recommendation quality and reduces [invalid generation / grounding error / decoding cost / bias], compared with [baseline group].
```

## Quality Checklist

1. The task appears early.
2. The problem is specific to recommender systems.
3. The proposed object is named clearly and consistently.
4. Technical details are sufficient but not excessive.
5. Every superiority claim is supported by experiments.
6. The abstract avoids inflated adjectives.
7. The final evidence sentence does not overclaim.
