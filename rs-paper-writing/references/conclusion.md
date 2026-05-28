# Conclusion Writing Guide

## Goal

Close the paper with clear takeaways, bounded claims, and credible limitations.

## Structure

1. Restate the recommendation problem.
2. Restate the proposed technical object and core idea.
3. Summarize the strongest evidence.
4. State the main implication.
5. Add a limitation or future direction when appropriate.

## Template

```text
This paper studies [recommendation task/problem] and proposes [Name], a [object noun] that [core idea].
By [main mechanism], [Name] addresses [problem].
Experiments on [datasets/settings] show that [Name] improves [main metric/property] over [baseline group].
These results suggest that [bounded implication].
A remaining limitation is [scope boundary], and extending [Name] to [future setting] is a useful direction.
```

## Limitation Guidance

Prefer limitations tied to scope:

1. specific recommendation setting;
2. type of feedback;
3. item modality;
4. user behavior assumption;
5. fairness or causal scope;
6. LLM size, decoding cost, or grounding assumption;
7. offline evaluation scope.

Avoid framing the conclusion around fixable implementation flaws unless they define the method's scope.

## Checklist

1. Claims are no stronger than experiments.
2. The method name and object noun are consistent.
3. The conclusion does not introduce new technical details.
4. Limitations are honest but not self-defeating.
5. Future work follows naturally from the limitation.
