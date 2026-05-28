# Related Work Writing Guide

## Goal

Position the paper against the most relevant recommender-system task lines and make the novelty easy to verify.

By default, organize Related Work by task line rather than by technique alone.

## Default Workflow

1. List directly competing and recent papers first.
2. Group literature by task line.
3. Within each task line, summarize the mainstream paradigm.
4. Explain the limitation relevant to this paper.
5. End each topic by clarifying the paper's distinction.

## Recommended Topic Lines

Choose two to four focused topics.

Examples:

1. Sequential Recommendation.
2. LLM-based Recommendation.
3. Fairness-aware Recommendation.
4. Debiasing in Recommender Systems.
5. Causal Recommendation.
6. Generative Recommendation.
7. Retrieval and Matching.
8. Ranking and CTR/CVR Prediction.
9. Multimodal Recommendation.
10. Graph-based Recommendation.

Only include a topic if it helps readers understand the paper's position.

## Paragraph Template

```text
[Task line] has been widely studied for [goal].
Representative methods [brief common paradigm].
However, these methods usually [limitation related to this paper].
In contrast, this paper [specific difference].
```

## Rules

1. Compare mechanisms, assumptions, and failure modes.
2. Cover the strongest direct competitors.
3. Do not make Related Work a citation dump.
4. Do not overstate novelty by ignoring related task lines.
5. Keep technical comparison factual and specific.
6. Use the same terminology as Introduction and Method.

## Checklist

1. Are all strongest/recent competitors covered?
2. Is each topic connected to the paper's problem setting?
3. Is the difference explained technically?
4. Is citation coverage complete for core claims?
5. Does the section avoid repeating the Introduction?
