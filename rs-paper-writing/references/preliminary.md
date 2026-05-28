# Preliminary / Problem Formulation Guide

## Core Idea

Write Preliminary by looking forward to Method.

Only define the task, notation, background objective, measurement concept, or failure diagnosis that the Method section directly depends on. Preliminary is not a small Related Work section and should not reveal the proposed method too early.

## Main Question

Before writing Preliminary, ask:

```text
What must a reviewer understand before reading the Method section?
```

If a symbol, metric, objective, or concept is not used later in Method, remove it.

## Default Workflow

1. Identify the paper type.
2. List the Method variables and modules.
3. Define the minimum notation needed by those variables.
4. Introduce only the background objective or metric that the method modifies.
5. Add problem diagnosis only when the failure mechanism is non-obvious.
6. End with a bridge to Method.

## Common RS Preliminary Types

### 1. Standard Recommendation Task

Use this for collaborative filtering, retrieval, matching, ranking, CTR/CVR prediction, or ordinary sequential recommendation.

Recommended structure:

```latex
\section{Preliminary}
\subsection{Problem Formulation}
\subsection{Recommendation Objective}
```

Define:

1. users, items, and interactions;
2. user history or feature context;
3. prediction target;
4. scoring function, ranking list, or top-K output;
5. objective only if Method directly uses it.

Do not introduce unrelated recommendation background.

### 2. LLM-Based Recommendation

Use this for prompt-based recommendation, instruction tuning, generative recommendation, LLM reranking, LLM reasoning for recommendation, or LLM alignment.

Recommended structure:

```latex
\section{Preliminary}
\subsection{Task Formulation}
\subsection{LLM-based Recommendation}
\subsection{Training Objective}
\subsection{Output Validity}
```

Define:

1. how user history and item information are converted into a prompt;
2. whether the model generates item titles, item IDs, semantic IDs, reasoning tokens, or ranked lists;
3. the autoregressive probability of the generated output;
4. the loss function used by the LLM recommender, such as SFT loss, DPO loss, GRPO objective, ranking loss, or another loss that Method modifies;
5. how generated outputs map to valid items, including constrained decoding, grounding, matching, or candidate filtering when applicable.

Keep the loss definition functional: define the variables, the objective, and the role it plays in the proposed method. Do not explain the full history of the objective.

### 3. Fairness / Debiasing / Causal Recommendation

Use this for item-side fairness, user-side fairness, popularity bias, exposure bias, debiasing, causal recommendation, counterfactual learning, or distribution alignment.

Recommended structure:

```latex
\section{Preliminary}
\subsection{Problem Formulation}
\subsection{Bias, Fairness, or Causal Definition}
\subsection{Measurement}
```

Define:

1. affected groups, item groups, user groups, or exposure groups;
2. the target distribution and model-induced distribution;
3. fairness, bias, or causal metrics and their direction;
4. causal variables when needed, such as treatment, exposure, confounder, propensity, and counterfactual outcome;
5. whether the later Method addresses training-stage bias, inference-stage bias, exposure bias, confounding, or distribution mismatch.

### 4. New Optimization Framework

Use this when Method builds on DPO, GRPO, GFlowNets, Best-of-N alignment, reinforcement learning, uncertainty modeling, calibration, or another framework.

Recommended structure:

```latex
\section{Preliminary}
\subsection{Task Formulation}
\subsection{Background Objective}
\subsection{Connection to Recommendation}
```

Define:

1. the recommendation objects used by the framework;
2. the minimum equations needed by Method;
3. how each variable maps to a user, item, prompt, list, candidate, reward, or feedback signal;
4. the limitation that motivates the proposed method if the limitation is not obvious.

## Problem Diagnosis

Add a short diagnosis subsection only when reviewers may not immediately believe the problem.

Use it for:

1. LLM-based recommendation;
2. fairness, debiasing, or causal recommendation;
3. a new failure mode of an existing objective;
4. a method motivated by counter-intuitive empirical behavior.

Do not force diagnosis into ordinary sequential recommendation or ranking papers unless the method truly depends on it.

Diagnosis can be empirical, theoretical, or conceptual:

```text
Empirical: show that an existing LLM recommender amplifies popularity bias.
Theoretical: show that an objective favors popular items under common sampling assumptions.
Conceptual: explain why an output validity issue makes generated recommendations unreliable.
```

## Writing Rules

1. Start from the recommendation task, not from a generic ML concept.
2. Define notation before Method uses it.
3. Keep object names stable: user, item, history, prompt, response, candidate, list, group, reward, exposure, or confidence.
4. For LLM-based recommendation, define the loss function when Method uses or modifies it.
5. For generated recommendations, define valid-item mapping if generated text can be invalid.
6. For fairness/debiasing/causal papers, define the measurement target before proposing the solution.
7. Avoid literature survey; use Related Work for comparison.
8. Avoid method leakage; define what is needed, not the proposed solution.
9. End with a bridge sentence that prepares the Method section.

## Bridge Patterns

```text
Based on this formulation, the key challenge is to [challenge], which motivates the method described next.
```

```text
The definitions above allow us to describe how the proposed method modifies [objective/framework] to address [problem].
```

```text
With the task and measurement clarified, we next present [Method Name].
```

## Quality Checklist

1. Every symbol used in Method is defined.
2. No unused symbol is introduced.
3. The task input and output are unambiguous.
4. The training objective is defined when Method depends on it.
5. LLM outputs are connected to valid recommendation items when needed.
6. Bias, fairness, or causal metrics are interpretable.
7. The section does not become Related Work.
8. The section does not prematurely describe the proposed method.
