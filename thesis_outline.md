## Thesis outline

### Background

- Double descent phenomenon leading to massive neural networks.

- Methods of model compression.

- Pre-training of LLaMa-based 0.5M params small LM

- Quantization. Why it works? Because models aren't using their full capacity (show experiment results here)

- Expose models' sensitivity to perturbations (show loss landscape plots here)

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