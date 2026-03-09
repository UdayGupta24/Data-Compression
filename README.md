# Data Compression Using Sparse Autoencoder

## Overview
This project explores **data compression using deep learning**, specifically a **Sparse Autoencoder**. The goal is to learn a compact representation of time-series signals while preserving the essential information required for reconstruction.

Unlike traditional compression techniques that focus purely on file size reduction, this project focuses on **information compression** by learning **low-entropy and sparse latent representations**.

The encoder removes redundancy from the signal, while the decoder reconstructs the signal from the compressed representation.

---

# Key Concepts

## 1. Autoencoder

An **autoencoder** is a neural network that learns an efficient representation of input data.

It consists of two parts:

### Encoder
Compresses the input signal into a **latent representation**.

### Decoder
Reconstructs the original signal from the compressed representation.

Pipeline:
#### Input Signal → Encoder → Latent Representation → Decoder → Reconstructed Signal


The model is trained to minimize reconstruction error.

---

# 2. Sparse Representation

Compression is achieved by enforcing **sparsity in the latent representation**.

A sparse representation means:

- Most neurons are **inactive (≈ 0)**
- Only a few neurons carry important information

Sparsity reduces redundancy and improves compressibility.

Sparsity is measured as:

#### Sparsity = Number of near-zero coefficients / Total coefficients


---

# 3. KL Divergence Sparsity Constraint

To enforce sparsity, a **Kullback-Leibler Divergence (KLD)** penalty is added to the loss function.

Total loss:

# 4. Sliding Window Segmentation

The time-series signal is divided into **fixed-length windows**.

Example:Raw Signal → Sliding Window → Segments (length = 64)

This allows the model to learn **local signal structures**.

---
# Compression Evaluation Metrics

## Percent Root Difference (PRD)

PRD measures reconstruction error relative to signal energy.

PRD = sqrt( Σ(x − x̂)² / Σx² ) × 100
## Signal-to-Noise Ratio (SNR)

SNR measures how well the reconstructed signal matches the original.

SNR = 10 log10 ( Σx² / Σ(x − x̂)² )

## Sparsity

Measures how many latent coefficients are near zero.
Sparsity = 1 − (nonzero elements / total elements)
Higher sparsity indicates stronger compression capability.

---

# Experimental Results

## Testing Data

PRD:9.67

SNR:20.28

Latent Sparsity:0.351

# Visualization

The project includes plots comparing:

- Original signal
- Reconstructed signal

These visualizations confirm that the **important signal structure is preserved after compression**.

---
# Technologies Used

- Python
- NumPy
- TensorFlow / Keras
- Matplotlib
- SciPy

---
# Helper

This Includes the Lifting Wavelet Discrete Transform And Inverse Lifting Wavelet Discrete Transform .py Code
In model this has been converted into TensorFlow Because in python Gradients were stopped .

#Author 

Uday Gutpa
