# Technical Challenge Version 2: Existing Task With Prior Insight

Use when an older or simpler paradigm reveals an insight that the proposed method modernizes.

```text
Traditional recommender systems often separate candidate generation from ranking so that expensive models operate only on a small candidate set.
This design reflects an important efficiency principle: high-quality ranking must be balanced against serving cost.
However, recent LLM-based recommenders often generate or rerank items with expensive decoding, and the cost can grow rapidly with prompt length, beam size, or sample count.
This motivates a method that preserves the expressiveness of LLM-based recommendation while reducing unnecessary decoding overhead.
```

Reusable logic:

1. Extract an insight from prior practice.
2. Explain why new methods violate or stress this insight.
3. Use the tension to motivate the proposed method.
