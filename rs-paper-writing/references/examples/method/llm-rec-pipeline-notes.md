# LLM Recommendation Pipeline Notes

Use these notes to map a pipeline figure into Method text.

## Common Pipeline

1. Input construction:
   - Convert user history, item metadata, or candidate items into a prompt.
2. Generation or scoring:
   - The LLM generates an item, semantic ID, ranked list, reasoning tokens, or relevance score.
3. Validity control:
   - Use constrained decoding, grounding, matching, or candidate filtering.
4. Optimization:
   - Train with SFT, DPO, GRPO, ranking loss, reward optimization, or a custom loss.
5. Inference:
   - Produce the final item or list and report cost if decoding or reranking is expensive.

## Suggested Paragraph Roles

1. Overview paragraph: state the method name and list modules.
2. Representation paragraph: define prompt, output format, and valid item space.
3. Objective paragraph: define loss or reward and explain why it matches recommendation.
4. Validity paragraph: explain how outputs become catalog items.
5. Training/inference paragraph: describe execution order and cost.
