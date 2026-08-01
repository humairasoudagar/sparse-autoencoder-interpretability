# Towards Monosemanticity: Decomposing Language Models With Dictionary Learning

## Abstract

The paper provides evidence that there are better units of analysis than individual neurons for understanding language models.

These units are called **features**, which are patterns (or linear combinations of neuron activations) learned from the model.

The authors show that complex, high-dimensional neuron activations can be decomposed into a larger set of features using Sparse Autoencoders with an expansion factor.

These learned features reveal properties of the model that are difficult or impossible to observe by studying individual neurons alone.

---

## Introduction

### Mechanistic Interpretability

Mechanistic interpretability aims to understand how a neural network works by breaking it down into smaller, understandable components instead of treating the entire network as a black box.

Once these components are identified, their individual functions and interactions can be studied to explain the behaviour of the whole network.

---

### Polysemantic Neurons

Individual neurons are often **polysemantic**, meaning they respond to multiple unrelated concepts instead of representing a single feature.

This makes it difficult to understand what a neuron is actually doing.

The paper argues that this happens because of **superposition**, where the number of useful features is greater than the number of available neurons.

---

### Sparse Autoencoders

The authors use Sparse Autoencoders as a dictionary learning algorithm to learn features from a trained language model.

These learned features are more **monosemantic**, meaning they tend to represent a single interpretable concept rather than a mixture of unrelated concepts.

---

### Goal of the Paper

The main goal of the paper is to demonstrate that Sparse Autoencoders can successfully extract interpretable features from superposition and enable basic circuit analysis.

To test this idea, the authors train a Sparse Autoencoder on the MLP activations of a one-layer transformer with a 512-neuron MLP layer.

The Sparse Autoencoder learns an expanded set of sparse features using an expansion factor.

---

# Questions I Still Have

- How does superposition naturally arise when useful features are sparse in the training data?

- How does sparsity allow the model to determine which combination of features produced a given activation vector?

- Why were sparse architectural approaches insufficient to prevent polysemanticity?
