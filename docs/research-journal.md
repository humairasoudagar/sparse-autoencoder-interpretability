# Research Journal

This journal documents my progress throughout this project.

---

## Day 1 

### What I know

- Sparse Autoencoders are used for mechanistic interpretability.
- This project combines ideas from AI and neuroscience.
- I have a lot to learn before I can build the full system.

### Questions

- What is a representation?
- What is an activation?
- Why do Sparse Autoencoders work?
- How does biological sparse coding differ from mathematical sparsity?

### Next Steps

- Learn what representations are.
- Read the first research paper.
  

## Day 2

### Objectives
- Understand the fundamentals of autoencoders.
- Study Sparse Autoencoders and their role in mechanistic interpretability.
- Build a foundation for the research project.

### Completed
- Documented the following concepts:
  - Autoencoder
  - Latent Representation
  - Reconstruction Loss
  - Sparse Autoencoder
  - Sparsity Constraint
  - Expansion Factor
  - Representation Learning
  - Feature

### Next Steps
- Begin reviewing the literature on Sparse Autoencoders.
- Study the concepts of superposition and monosemanticity.

## Day 3

### Objectives
- Begin the literature review.
- Study the motivation behind Sparse Autoencoders.
- Understand the research problem addressed by Anthropic.

### Completed
- Read the Abstract and Introduction of *Towards Monosemanticity: Decomposing Language Models with Dictionary Learning*.
- Documented notes from the paper.
- Identified the central research problem:
  - Individual neurons are often polysemantic.
  - Features provide a better unit of analysis than individual neurons.
  - Sparse Autoencoders can learn more interpretable feature representations.
- Recorded questions for further study regarding:
  - Superposition
  - Compressed sensing
  - Sparse architectural approaches

### Next Steps
- Continue reading the paper.
- Study the sections on feature decomposition and Sparse Autoencoder methodology.
- Expand the concepts documentation as new ideas are understood.

## Day 4

### Objectives

* Complete the first research paper.
* Understand how Sparse Autoencoders are used to study language model representations.
* Identify what we need to implement from the paper.

### Completed

* Completed *Towards Monosemanticity: Decomposing Language Models With Dictionary Learning* by Bricken et al. (2023).
* Studied polysemanticity, superposition, dictionary learning, and Sparse Autoencoders.
* Understood the basic SAE objective: reconstruct the original activation while encouraging sparse feature activations.
* Studied feature density, dead features, feature splitting, feature universality, and feature steering.
* Decided to implement the relevant SAE method from Paper 1 before moving to the next paper.

### Next Steps

* Build a normal Autoencoder.
* Convert it into a basic L1 Sparse Autoencoder.
* Train and inspect the learned features.
* Complete the Paper 1 implementation before reading the next paper.

## Day 5

### Objectives

* Build a basic ordinary Autoencoder in PyTorch.
* Understand how the encoder and decoder work together.
* Train the Autoencoder to reconstruct its input.
* Build the foundation needed for the Sparse Autoencoder implementation.

### Completed

* Built an ordinary Autoencoder using PyTorch.
* Created an encoder that maps the input from 8 dimensions to 16 dimensions.
* Created a decoder that maps the 16-dimensional representation back to 8 dimensions.
* Implemented the forward pass:

```text id="p4c6zm"
Input
  ↓
Encoder
  ↓
Latent Representation
  ↓
Decoder
  ↓
Reconstruction
```

* Used Mean Squared Error (MSE) as the reconstruction loss.
* Created an SGD optimizer.
* Implemented the training loop.
* Used `zero_grad()`, `backward()`, and `step()` to train the model.
* Evaluated the trained Autoencoder.

### What I Learned

The Autoencoder learns to reproduce its input rather than predicting a separate target.

The encoder produces an internal representation, and the decoder uses that representation to reconstruct the original input.

The basic training process is:

```text id="9g9wtx"
Input
 ↓
Encoder
 ↓
Latent representation
 ↓
Decoder
 ↓
Reconstruction
 ↓
MSE loss
 ↓
Backpropagation
 ↓
Update weights
```

I also learned how the PyTorch model, loss function, optimizer, gradients, and training loop work together.

### Questions

* What does the latent representation actually contain?
* Why does an ordinary Autoencoder not necessarily produce sparse features?
* How can sparsity be added to the latent representation?
* How does the L1 penalty used in Paper 1 change the training objective?

### Next Steps

* Convert the ordinary Autoencoder into a Sparse Autoencoder.
* Add the L1 sparsity penalty described in Paper 1.
* Train the Sparse Autoencoder.
* Compare reconstruction and feature activity.

## Day 6

### Objectives

* Convert the ordinary Autoencoder into a basic Sparse Autoencoder.
* Understand how L1 sparsity is added to the Autoencoder.
* Implement the loss function described in Paper 1.
* Train the Sparse Autoencoder.

### Completed

* Added ReLU after the encoder to produce non-negative feature activations.
* Modified the forward pass to return both the reconstruction and feature activations.
* Added the reconstruction loss using MSE.
* Added an L1 sparsity penalty on the feature activations.
* Combined the reconstruction loss and sparsity penalty:

[
L = L_{\text{reconstruction}} + \lambda \sum_i |z_i|
]

* Trained the Sparse Autoencoder using SGD.
* Checked the individual parts of the loss after training.

### Result

Using:

```text
λ = 0.1
```

the model produced:

```text
Reconstruction loss: 0.181694
Sparsity penalty:     0.336953
Total loss:           0.215390
```

The total loss was verified using:

[
0.181694 + (0.1)(0.336953) \approx 0.215390
]

### What I Learned

The ordinary Autoencoder only has to reconstruct its input.

The Sparse Autoencoder has an additional goal: keep the feature activations small.

The L1 penalty is calculated by taking the absolute value of the feature activations and adding them together.

I also learned how to translate this mathematical expression into PyTorch:

```python
torch.sum(torch.abs(features))
```

and how the sparsity coefficient controls how much this penalty contributes to the total loss.

### Questions

* Are the learned feature activations actually sparse?
* How many features are active for each input?
* How should we measure the sparsity of the representation?
* What happens when the value of λ changes?

### Next Steps

* Inspect the learned feature activations.
* Measure the number of active features.
* Compare reconstruction quality and sparsity.
* Understand L0 activity as used in Paper 1.
