# Module Design Example: Sequential Interest Encoder

Each annotation explains the role of the paragraph below it.

% Motivation of this module
User histories contain both stable long-term preferences and recent short-term intents. A single pooled representation may lose temporal structure and overemphasize frequent items. To capture both signals, we design a sequential interest encoder.

% Module design: representation
For each user, we represent the interaction history as an ordered sequence \(H_u = [i_1, i_2, ..., i_t]\). Each item \(i_j\) is mapped to an embedding \(e_j\), and positional embeddings are added to preserve interaction order.

% Module design: forward process
Given the embedded sequence, the encoder first applies a temporal attention layer to obtain contextualized item representations. It then aggregates recent interactions into a short-term interest vector and the full sequence into a long-term preference vector. The two vectors are combined to produce the final user representation.

% Technical advantage
This design allows the model to distinguish transient intent from persistent preference. As a result, the final representation can support both immediate next-item prediction and stable personalized ranking.
