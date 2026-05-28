# Novel Task Challenge Decomposition

Use when the problem has multiple independent challenges.

```text
In this work, we study LLM-based recommendation under rapidly changing user interests.
This problem is challenging for three reasons.
First, newly observed feedback may reveal short-term intent that is not captured by a model trained on older logs.
Second, frequently updating large language models is expensive and difficult to deploy.
Third, the model must incorporate recent feedback without forgetting the recommendation knowledge learned during instruction tuning.
```

Reusable logic:

1. Name the new setting.
2. Decompose into two or three challenges.
3. Ensure each challenge motivates a later method component.
