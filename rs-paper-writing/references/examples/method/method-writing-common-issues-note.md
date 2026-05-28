# Method Writing Common Issues

Common problems:

1. The Method starts with implementation details before stating the overall idea.
2. Variables appear before they are defined.
3. A module is described mechanically but its motivation is missing.
4. A loss function is written without explaining what recommendation behavior it encourages.
5. LLM-generated outputs are not connected to valid catalog items.
6. The inference workflow is missing even though the method changes decoding, reranking, or grounding.
7. Added complexity is not tied to a measurable benefit.

Usage recommendation:

1. First write a table of modules, inputs, outputs, motivations, and advantages.
2. Then write each module paragraph in the order: motivation, design, advantage.
3. Finally write the total objective and inference procedure.
