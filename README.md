# Refusal in LLMs

![Refusal in LLMs](https://res.cloudinary.com/lesswrong-2-0/image/upload/f_auto,q_auto/v1/mirroredImages/jGuXSZgv6qfdhMCuJ/v7efehn5o9q3gib0917k)

This repository contains an implementation and exploration of the **Refusal Mechanism** in large language models (LLMs) detailed in the [Refusal in Language Models
Is Mediated by a Single Direction paper](https://arxiv.org/pdf/2406.11717), based on recent findings that refusal behaviors in these models are mediated by a single direction in the activation space.

## Introduction

Recent research has identified that refusal in LLMs, the behavior where the model declines to answer certain queries or generates refusals, is governed by a specific direction in the model's high-dimensional activation space. Understanding and manipulating this refusal direction can provide deeper insights into the model's behavior and improve the control over generated outputs.

### Key Concepts

- **Single Direction Mediation**: Refusal behaviors are linked to a single, identifiable direction in the model's activation space. Adjusting the influence of this direction can modulate the model's likelihood to refuse certain queries.
- **Activation Space**: The high-dimensional space in which the internal states of the model's neurons are represented during computation.
- **Behavior Control**: By leveraging the identified refusal direction, it is possible to enhance or suppress the model's tendency to refuse responses, offering a new level of control over LLM outputs.

## Steps

As presented in the paper, the steps are the following:

1. **Identification of Refusal Heads**:
   - Attention heads in LLMs were identified as key contributors to the model’s ability to refuse harmful instructions.

2. **Extraction of Refusal Direction**:
   - The refusal direction was calculated by computing the mean difference in outputs on harmful versus harmless prompts for each identified refusal head.

3. **Manipulating Refusal Behavior**:
   - **Inducing Refusal**: Adding the refusal direction to the model's residual stream at specific layers (positions 17, layers 5-10) induced refusal responses to even harmless prompts.
   - **Suppressing Refusal**: Subtracting the refusal direction suppressed the model's refusal, resulting in detailed responses to harmful prompts.
