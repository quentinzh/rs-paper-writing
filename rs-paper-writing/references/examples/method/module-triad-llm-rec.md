# Module Triad Example: LLM Recommendation Grounding

Use this example to understand the three elements of a Method module.

## Module

Valid item grounding for LLM-based recommendation.

## Motivation

LLM recommenders may generate item titles that do not exactly match the catalog. If generated text cannot be mapped to valid items, ranking metrics and user-facing recommendations become unreliable. Therefore, the method needs a grounding module that converts generated outputs into catalog items.

## Design

Given a generated response, the grounding module first extracts candidate item strings, then encodes each string and catalog item into a shared representation space, and finally selects the nearest valid item under the matching score. If constrained decoding is used, the module restricts token generation to valid item identifiers and directly returns the matched item.

## Technical Advantage

This module separates language generation quality from catalog validity. It ensures that recommendation evaluation is performed on real items and allows the paper to report invalid generation rate or grounding success rate as additional evidence.
