# Example of the Three Elements

Use this example to label Method paragraphs.

## Topic

Popularity-aware negative sampling for debiasing LLM-based recommendation.

% Motivation
Standard DPO training for recommendation often samples negative items from a fixed distribution. When the model already over-generates popular items, fixed negative sampling may fail to suppress these biased high-probability outputs. Therefore, the training objective needs negative samples that reflect the model's current biased predictions.

% Module design
Given a user prompt \(x\), we first run the current policy to generate a candidate recommendation \(y_l\). We pair this generated item with the observed positive item \(y_w\) to construct a preference tuple \((x, y_w, y_l)\). The model is then optimized to increase the probability of \(y_w\) and decrease the probability of \(y_l\).

% Technical advantage
Because \(y_l\) is sampled from the model's own prediction distribution, the training process focuses on items that the model is currently likely to over-recommend. This adaptive sampling strategy directly targets emerging popularity bias rather than relying on a static negative sampler.
