## Thesis outline

Title:

```
Adaptive Rounding for Efficient Post-Training Quantization of Deep Neural Networks
```

### Background

- Double descent phenomenon leading to massive neural networks.

- Motivation: Need for model compression, then describe methods (quantization, distillation, pruning, weight palettization, etc).

- Introduce TinyStories
    - Their oversight: using GPT-Neo tokenizer instead of training one
    - **Experiment**: Results of pretrained models with custom tokenizer - better perplexity with half model size

- Quantization. Why it works? Because models aren't using their full capacity
    - Show computed entropy of weights on Qwen 3, showing that it only uses 2/3 of its capacity

- **Experiment**: Pre-training of LLaMa-based 0.46M params small LM on TinyStories V2. And loss landscape plots of this small LM to demonstrate models' sensitivity to perturbations

### Literature Review

- Describe AdaRound

- **Experiment**: Inversion results of AdaRound, showing potential privacy risk

- Another limitation: AdaRound assumes zero gradient for converged models, but central flows paper says otherwise. (Introduce Central Flows paper here, then show Kimi K2 training loss curve as empirical evidence on frontier LLMs)

### Proposed Method

- Purpose: investigate the inconsistency between the two papers (AdaRound and Central Flows). 

- Proposed method (Post-training on 2% of the data, then steer rounding using the direction from the original model to the post-trained model)

  - TODO: vary amount of post training data. does it depend on the dataset? maybe even very few calibration samples would work too?

### Experiments

#### Setup

- Experiment environment and conditions.

#### Results

- **Experiment**: Results of proposed method vs. AdaRound on our own language model, showing decreased perplexity

#### Discussion

- Analysis of results. For methods that didn't work: why it doesn’t work so well.

### Conclusion & Future Prospects

- AdaRound and proposed method both has compute requirement. 

- Future work: perhaps using some of the compute during training (QAT)?

## Notes

Important for master thesis: 
- Purpose of research 
- Good explanation of proposed method
- Analysis of results. If it doesn't work well, why it doesn’t work so well.

Length requirement: 30 is minimum but 40-50 is optimal


TODO: Direction for EMA of last few iterations might have reversed direction