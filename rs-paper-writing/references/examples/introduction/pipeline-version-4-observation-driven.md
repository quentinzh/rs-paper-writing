# Pipeline Version 4: Observation-Driven Method

Use when the method is motivated by a clear empirical or theoretical observation.

```text
Our design is motivated by the observation that DPO-trained LLM recommenders tend to assign excessive probability mass to popular items.
Based on this observation, we construct negative samples from the model's own predictions rather than from a fixed random sampler.
This design forces the model to suppress its emerging biased peaks, improving the balance between recommendation utility and item exposure.
```
