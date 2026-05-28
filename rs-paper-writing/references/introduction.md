# Introduction Writing Guide

## Goal

Write an Introduction that quickly tells reviewers what recommendation problem the paper solves, why the problem matters, why existing methods are insufficient, and why the proposed method is credible.

## Core Logic

Use this order by default:

1. Task and importance.
2. Representative methods or current paradigm.
3. Remaining problem and technical reason.
4. Proposed model, method, framework, objective, algorithm, or evaluation protocol.
5. Main technical characteristics.
6. Experimental evidence.
7. Contributions.

Do not spend multiple paragraphs on distant background before entering the central recommendation problem.

## RS-Specific Entry Points

Choose one entry point.

### 1. Task-First

Use for less familiar tasks.

```text
[Task] aims to [predict/retrieve/rank/generate/debias] [output] from [input].
This task is important for [application or research goal].
```

### 2. Application-First

Use for familiar tasks.

```text
Personalized recommendation is central to [application].
Practical systems require [accuracy/efficiency/diversity/fairness/robustness].
```

### 3. Paradigm-First

Use when the paper is about a new paradigm such as LLM-based recommendation or generative recommendation.

```text
Recent work has reformulated recommendation as [paradigm].
This paradigm enables [benefit], but also introduces [problem].
```

### 4. Failure-First

Use when the paper identifies a strong failure mechanism.

```text
Although [method type] has achieved strong results in [task], it still suffers from [failure].
This failure matters because [negative consequence].
```

## Existing Methods and Challenge

The Introduction should not list prior work broadly. It should use prior work to expose the exact challenge solved by the paper.

Rules:

1. Discuss existing methods around the target challenge.
2. Explain both the limitation and the technical reason.
3. Ensure the final limitation is exactly what the proposed method solves.
4. Do not set up a weak or naive baseline just to make the method look better.
5. Do not raise problems that the paper cannot solve.

Templates:

```text
Existing [task] methods typically [mechanism]. However, they struggle with [problem] because [technical reason].
```

```text
For LLM-based recommendation, recent methods often [SFT/DPO/prompting/reranking/generation paradigm]. However, [objective/output/protocol] creates [failure], which leads to [recommendation-specific consequence].
```

```text
For fairness/debiasing, existing methods usually [mechanism]. However, they do not fully address [bias source] because [reason].
```

## Introducing the Proposed Method

Use a stable object noun based on the paper:

- `model` for a predictive architecture;
- `method` for a general technical solution;
- `framework` for a multi-stage system;
- `objective` for a training loss;
- `algorithm` for an optimization or inference procedure;
- `evaluation protocol` for a measurement contribution.

Template:

```text
To address this problem, we propose [Name], a [object noun] for [task].
The key idea of [Name] is [core idea].
Specifically, [Name] [mechanism 1] and [mechanism 2].
These designs enable [benefit] because [reason].
```

## Contribution List

The contribution list should be concrete and verifiable.

Template:

```text
The main contributions are summarized as follows:
1. We identify [problem/failure] in [task/paradigm] and explain why it matters.
2. We propose [Name], which [main technical contribution].
3. We design [module/objective/algorithm], which [technical benefit].
4. We conduct experiments on [datasets/settings] and show that [main evidence].
```

Rules:

1. Do not claim a contribution without evidence.
2. Do not call an implementation detail a contribution.
3. If the paper introduces a problem diagnosis, include the diagnosis as a contribution only when it is supported by analysis or experiments.
4. Keep experimental contribution bounded to reported metrics.

## Default Skeleton

```latex
\section{Introduction}

% Paragraph 1: task and importance
% Paragraph 2: existing paradigm and limitation
% Paragraph 3: technical reason behind the limitation
% Paragraph 4: proposed method and main idea
% Paragraph 5: experimental evidence
% Paragraph 6: contributions
```

For LLM-based recommendation or fairness/debiasing papers, insert a diagnosis paragraph if the failure mechanism is central to the method.

## Reviewer-Oriented Checklist

1. Can the reviewer identify the task in the first paragraph?
2. Is the paper's problem specific and important?
3. Are representative methods or paradigms described fairly?
4. Is the technical reason for the limitation clear?
5. Does the proposed method directly address the stated problem?
6. Is the proposed object named consistently?
7. Are claims supported by citations, analysis, or experiments?
8. Does the experiment sentence match the actual evidence?
9. Does the Introduction avoid excessive mechanism details?
10. Would a skeptical RS reviewer see an obvious objection?
