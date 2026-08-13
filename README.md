# Biologically Inspired Sparse Autoencoder

## Investigating Whether Biologically Inspired Sparse Coding Can Make Language Model Representations More Interpretable

Exploring whether biologically inspired sparse coding can make language model representations easier to understand.

Language models have representations that are difficult to interpret. Sparse Autoencoders can turn those representations into sparse features. This project tests whether a biologically motivated way of encouraging sparsity can make those features easier to interpret than the usual L1 approach.

---

## Research Question

**When both Sparse Autoencoders reconstruct the original language-model activations equally well, do biologically motivated target-activity constraints produce features that are easier to interpret and more semantically coherent than standard L1 sparsity?**

---

## How It Works

A small open-weight language model is used to produce residual-stream activations.

These activations are given to two Sparse Autoencoders:

```text
Language Model
      ↓
Residual-Stream Activations
      ↓
 ┌───────────────┐
 │               │
 ↓               ↓
Standard SAE   Experimental SAE
 │               │
 └───────┬───────┘
         ↓
   Sparse Features
         ↓
  Feature Analysis
```

The Standard SAE uses L1 regularization to encourage sparse activations.

The Experimental SAE uses a biologically motivated constraint based on sparse population coding.

The two approaches are compared while keeping their ability to reconstruct the original language-model activations approximately the same.

## Repository Layout

Biologically-Inspired-SAE/
├── papers/       Paper notes
├── docs/         Concepts and methodology
├── src/          Implementation
├── experiments/  Training and analysis
├── results/      Experimental results
└── figures/      Visualisations

