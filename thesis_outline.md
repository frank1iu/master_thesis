## Thesis outline

### Background

- Double descent phenomenon leading to massive neural networks.

- Need for model compression, then describe methods (quantization, distillation, pruning, weight palettization, etc).

- Introduce TinyStories
    - Their oversight: using GPT-Neo tokenizer instead of training one
    - Results of models reproduced with custom tokenizer

- Quantization. Why it works? Because models aren't using their full capacity (show experiment results here)

- Pre-training of LLaMa-based 0.46M params small LM on TinyStories V2

- Expose model's sensitivity to perturbations (show loss landscape plots here)

### Literature Review

- Describe AdaRound

- Show inversion attack here

### Proposed Method

- Proposed method (TODO: Either first order taylor approximation using EMA or combine both)

### Experimentation

- Describe experiment environment and conditions here

### Results

- Results of proposed method vs. AdaRound on our own language model

- Show robustness to inversion

### Conclusion & Future Prospects

- AdaRound and proposed method both has compute requirement. 

- Perhaps using some of the compute during training (QAT)?