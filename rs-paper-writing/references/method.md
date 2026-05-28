# Method Writing Guide

## Goal

Write the Method section so reviewers can understand what the method does, why each component is needed, why it works, and how it is trained or used.

This guide is distilled from recommender-system method sections in LLM-based recommendation, fairness/debiasing, sequential recommendation, and optimization-oriented recommendation papers.

## Core Method Logic

A strong RS Method section usually follows this arc:

```text
Problem Formulation / Preliminary -> Problem Diagnosis -> Method Overview -> Module Design -> Objective / Algorithm -> Training or Inference Workflow
```

Problem Diagnosis is a strong rule for LLM-based recommendation, fairness/debiasing, and causal/debiasing papers. It is optional for ordinary sequential recommendation, retrieval, ranking, or CTR/CVR papers.

## Pre-Writing Questions

Before writing Method, answer:

1. What exact task formulation does the method assume?
2. Which problem or failure mechanism does the method address?
3. What modules or stages exist?
4. For each module, what is its input, workflow, output, and technical advantage?
5. What objective, loss, reward, or algorithm trains the method?
6. How does the method produce recommendations at inference time?
7. What extra cost does the method introduce?

## Recommended Section Skeleton

```latex
\section{Method}
\subsection{Overview}
\subsection{[Module or Stage 1]}
\subsection{[Module or Stage 2]}
\subsection{Objective and Training}
\subsection{Inference}
```

Use a separate `Problem Formulation` subsection only if the paper does not already have Preliminary.

## Overview Subsection

The Overview should do three things:

1. Name the proposed method and object noun.
2. State the core idea.
3. Map the pipeline figure to the following subsections.

Template:

```text
We propose [Name], a [model/method/framework/objective/algorithm] for [task].
[Name] addresses [problem] by [core idea].
As shown in Figure [X], [Name] consists of [module 1], [module 2], and [module 3].
```

## Module Writing Pattern

Each major module should contain three elements.

### 1. Motivation

Explain why the module is needed.

```text
A remaining challenge is [problem]. Existing [method type] fails because [technical reason]. Therefore, we design [module] to [goal].
```

### 2. Design and Forward Process

Describe the module in execution order.

```text
Given [input], [module] first [step 1], then [step 2], and finally outputs [output].
```

Define variables before formulas. After each key formula, explain what the quantity means in recommendation terms.

### 3. Technical Advantage

Explain why the design helps.

```text
This design enables [benefit] because [reason].
```

Tie the advantage to observable behavior when possible: recommendation accuracy, fairness, diversity, calibration, valid generation, decoding efficiency, robustness, or adaptation.

## RS-Specific Method Skeletons

### LLM-Based Recommendation

Include:

1. prompt or input construction;
2. output representation: title, ID, semantic ID, list, reasoning tokens, or score;
3. loss/objective: SFT, DPO, GRPO, ranking loss, reward, or custom loss;
4. valid item mapping: constrained decoding, grounding, matching, or candidate filtering;
5. inference workflow and cost.

Recommended structure:

```latex
\subsection{Overview}
\subsection{Input and Output Representation}
\subsection{[Main LLM Module or Alignment Objective]}
\subsection{Training Objective}
\subsection{Valid Item Generation and Inference}
```

### Fairness / Debiasing / Causal Recommendation

Include:

1. bias source or causal mechanism;
2. fairness/debiasing target;
3. module that changes training, inference, exposure, weighting, or reranking;
4. accuracy-fairness trade-off control;
5. measurement connection.

Recommended structure:

```latex
\subsection{Problem Diagnosis}
\subsection{Overview}
\subsection{[Training-stage Debiasing Module]}
\subsection{[Inference-stage or Reranking Module]}
\subsection{Objective}
```

### Sequential Recommendation

Include:

1. user history representation;
2. temporal interest modeling;
3. sequence encoder or retrieval/ranking module;
4. prediction target and loss;
5. inference ranking procedure.

Recommended structure:

```latex
\subsection{Overview}
\subsection{User Behavior Representation}
\subsection{Interest Modeling}
\subsection{Prediction and Training Objective}
```

### Optimization-Oriented Recommendation

Use for DPO, GRPO, GFlowNets, Best-of-N, RL, uncertainty, or confidence alignment.

Include:

1. background objective in Preliminary;
2. failure of the existing objective;
3. proposed objective or reward;
4. algorithmic workflow;
5. cost and stability notes.

Recommended structure:

```latex
\subsection{Limitations of [Existing Objective]}
\subsection{Method Overview}
\subsection{[New Reward / Estimator / Objective]}
\subsection{Optimization Algorithm}
\subsection{Overall Training}
```

## Objective and Training

Put the final objective near the end of Method.

For multiple losses, explicitly state:

1. which samples or rollouts each loss uses;
2. whether losses share parameters;
3. how objectives are weighted;
4. which parameters are updated or frozen;
5. the training order.

Template:

```text
The final objective combines [loss 1] and [loss 2]:
[equation]
Here, [loss 1] optimizes [goal], while [loss 2] encourages [goal].
Training proceeds in three steps: [step 1], [step 2], and [step 3].
```

## Inference and Serving

Write an inference subsection when the method changes recommendation generation, reranking, grounding, decoding, confidence use, or serving cost.

Include:

1. input at inference;
2. candidate generation or scoring;
3. valid item mapping if needed;
4. final ranking or list construction;
5. additional latency, memory, or decoding cost when relevant.

## Method Clarity Checklist

1. Every Method variable is defined in Preliminary or Method.
2. The overview matches the figure and subsection order.
3. Each module has motivation, design, and technical advantage.
4. Formulas are followed by intuition.
5. The training objective is complete.
6. The inference workflow is clear.
7. LLM outputs map to valid recommendation items when needed.
8. The method does not look like a minor patch over a weak baseline.
