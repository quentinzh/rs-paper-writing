---
name: rs-paper-writing
description: "Improve academic paper writing for recommender-system papers, including LLM-based recommendation, fairness/debiasing/causal recommendation, sequential recommendation, retrieval, ranking, and RS experiments. Use when drafting or revising Abstract, Introduction, Preliminary, Method, Experiments, Related Work, or Conclusion; polishing figures/tables; checking claim-evidence alignment; or performing pre-submission self-review for KDD, SIGIR, WWW, AAAI, ACL, RecSys, CIKM, or WSDM style papers."
---

# Recommender Systems Paper Writing

## Overview

Use this skill to write or revise recommender-system research papers into clear, reviewer-friendly drafts.

Prioritize three outcomes:

1. The paper story is easy to understand.
2. Every major claim is supported by appropriate evidence.
3. The writing matches recommender-system review expectations.

## Core Workflow

1. Clarify the paper story before sentence-level editing.
2. Identify the paper type: LLM-based recommendation, fairness/debiasing/causal recommendation, sequential recommendation, retrieval/ranking, or another RS task.
3. Load only the needed section guide from `references/`.
4. Build a compact outline before drafting prose.
5. Rewrite paragraph-by-paragraph with one message per paragraph.
6. Run reverse outlining after each section.
7. Check Abstract and Introduction claims against experiments.
8. Run final adversarial review with `references/paper-review.md`.

## Global Principles

1. Keep one paragraph for one message only.
2. State the paragraph message in the first sentence.
3. Make nouns self-contained; define new terms before reusing them.
4. Keep terminology consistent throughout the paper.
5. Choose the object noun based on the paper: model, method, framework, objective, algorithm, system, or evaluation protocol. Once chosen, use it consistently.
6. Use `propose` when introducing the paper's own technical contribution unless another verb is technically necessary.
7. Maintain sentence-to-sentence flow through cause, contrast, consequence, refinement, or example.
8. Treat figures, tables, and captions as core communication, not decoration.
9. Avoid unsupported superiority claims.
10. Read every section as a skeptical recommender-system reviewer.

## RS-Specific Priorities

1. Make the task setting explicit: user-item interaction, candidate generation, ranking, next-item prediction, click/conversion prediction, list generation, fairness, debiasing, causal inference, or LLM-based recommendation.
2. For LLM-based recommendation, define the input prompt, output format, valid-item mapping, and training loss when relevant.
3. For fairness/debiasing/causal papers, define the target distribution, bias source, causal variables, or fairness metric before proposing the method.
4. For sequential recommendation, keep temporal user behavior, short-term/long-term interest, and prediction target unambiguous.
5. For experiments, focus on task-specific metrics, baseline grouping, statistical significance, efficiency/resource cost, LLM generation validity/grounding, and fairness/accuracy trade-off.
6. For experimental setup choices, use recent high-quality literature to justify datasets, compared models, metrics, and common hyperparameters.

## Paragraph Clarity Check

Use this quick test whenever the user asks whether a paragraph flows or is clear.

1. Read as an external reviewer:
   - Does this paragraph have one explicit message?
   - Does the first sentence state that message?
   - Are all key terms readable without hidden context?
   - Does each sentence connect to the previous one with a clear relation?
2. Run reverse outlining:
   - Write down the section thesis.
   - Write down each paragraph topic sentence.
   - Write down the evidence or explanation under each paragraph.
   - Check whether each paragraph maps cleanly to the thesis.
3. If flow is weak, add temporary transition phrases during revision, then remove unnecessary scaffolding before finalizing.

Source reference:

- `references/does-my-writing-flow-source.md`

## Section Guides

Load only the needed section file:

- Abstract: `references/abstract.md`
- Introduction: `references/introduction.md`
- Preliminary / Problem Formulation: `references/preliminary.md`
- Method: `references/method.md`
- Experiments: `references/experiments.md`
- Related Work: `references/related-work.md`
- Conclusion: `references/conclusion.md`
- Paper review: `references/paper-review.md`
- Paragraph clarity source: `references/does-my-writing-flow-source.md`
- Example bank index: `references/examples/index.md`

## Paper Review Core Points

Use `references/paper-review.md` for the full checklist and workflow.

1. Add an end-of-draft self-review question list in five dimensions:
   - contribution,
   - writing clarity,
   - experimental strength,
   - evaluation completeness,
   - method design soundness.
2. Treat claim-evidence alignment as a hard constraint.
3. Resolve recommender-system rejection risks such as weak baselines, unsupported metric choices, missing significance, unclear efficiency cost, invalid LLM outputs, weak grounding, and unexamined fairness/accuracy trade-off.
4. Revise until major rejection risks are explicitly addressed.

## Execution Rules

1. Build a mini-outline before drafting prose.
2. For Method, explicitly include motivation, design, and technical advantage for each major module.
3. For Preliminary, define only what the Method section directly needs.
4. Avoid presenting the paper as a small patch over a weak baseline.
5. Keep terminology stable across the full paper.
6. If a claim cannot be supported by experiments or analysis, weaken or remove it.
7. Do not load all section references at once; load only the guide needed for the current edit target.

## Output Contract

When asked to rewrite or draft sections, return:

1. A compact section outline.
2. Revised paragraphs with explicit paragraph roles.
3. A short self-review checklist covering clarity, flow, terminology consistency, unsupported claims, and missing evidence.
4. A claim-evidence map for each major claim using `Claim: ... | Evidence: ... | Status: supported/needs evidence`.
