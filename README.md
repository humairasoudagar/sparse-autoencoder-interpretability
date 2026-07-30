# Sparse Autoencoder Interpretability

> Exploring whether biologically inspired sparse coding can make language model representations easier to understand.

---

## Research Question

**Can biologically inspired sparse coding make language models easier to interpret?**

---

## Overview

Modern language models contain millions of internal features, yet understanding what those features represent remains an open challenge.

Sparse Autoencoders (SAEs) have emerged as one of the most promising tools for mechanistic interpretability by learning sparse representations of language model activations. However, most existing approaches are driven primarily by mathematical optimisation rather than principles observed in biological neural systems.

This project investigates whether ideas from biological sparse coding can lead to representations that are easier for humans to interpret while preserving the usefulness of Sparse Autoencoders.

---

## Why this project?

I'm a Computer Science student interested in AI and neuroscience.

Mechanistic interpretability is a rapidly developing area of AI research, but it's also a field I am learning from the ground up.

This repository documents that journey. It serves as both a research notebook and a record of experiments as I investigate whether ideas from biological sparse coding can improve the interpretability of language models.

My goal is not only to build a working system, but to understand every major concept along the way.

## Tech Stack

**Programming**
- Python

**Deep Learning**
- PyTorch

**Language Models**
- GPT-2 Small *(planned)*

**Interpretability**
- Sparse Autoencoders
- TransformerLens *(planned)*

**Data Handling**
- NumPy
- Pandas

**Visualisation**
- Matplotlib
- Plotly

**Experiment Tracking**
- Git
- GitHub

---

## Dataset

*To be finalised after the literature review.*

Potential datasets and activation sources:

- OpenWebText
- WikiText-103
- The Pile (small subset)
- Residual stream activations extracted from GPT-2 Small

---

## Estimated Process

1. Learn the fundamentals of representation learning.
2. Understand Autoencoders.
3. Build a simple Autoencoder from scratch.
4. Implement a baseline Sparse Autoencoder.
5. Study biological sparse coding.
6. Design biologically inspired constraints.
7. Train and evaluate both models.
8. Compare interpretability and reconstruction quality.
9. Document findings.

---

## Learning Map

- [ ] Neural Networks
- [ ] Representation Learning
- [ ] Autoencoders
- [ ] Sparse Autoencoders
- [ ] Transformers
- [ ] GPT-2 Architecture
- [ ] Mechanistic Interpretability
- [ ] Biological Sparse Coding
- [ ] Experimental Design
- [ ] Model Evaluation

---

## Repository Structure
```
.
├── docs/
├── papers/
├── notebooks/
├── src/
├── experiments/
├── results/
├── figures/
├── assets/
└── README.md
```

---

## References

The literature review and references will be added as the project progresses.
