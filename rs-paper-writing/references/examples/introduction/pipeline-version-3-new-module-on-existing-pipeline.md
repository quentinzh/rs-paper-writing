# Pipeline Version 3: New Module on Existing Pipeline

Use when the paper adds a new module to a standard RS pipeline.

```text
To address the efficiency limitation, we add a lightweight reranking module to the existing retrieval-then-ranking pipeline.
The module receives the top candidates from the base retriever and estimates [property] before the final ranker is applied.
Because this module operates only on a small candidate set, it improves [target property] while introducing limited additional latency.
```
