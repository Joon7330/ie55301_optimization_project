# Optimization Matters in Adversarial Attacks

This repository provides the code for reproducing optimization project:

**Optimization Matters in Adversarial Attacks:  
A Systematic Study of Optimizer-Driven PGD Performance**

The goal of this project is to analyze how different first-order optimizers,
when applied to the adversarial perturbation variable, affect PGD attack strength
under fixed computational budgets.

---

## Overview

We formulate adversarial attacks as a constrained optimization problem over the
perturbation variable $\delta$ and systematically replace the standard PGD update
rule with various first-order ascent optimizers.

All experiments keep the threat model, perturbation budget, and number of steps fixed,
varying only the optimizer used in the inner loop.

Optimizers evaluated include:
- Vanilla PGD (sign-gradient)
- SGD
- SGD with Momentum
- Adam / AdamW / Adamax
- RMSProp
- Adagrad

---

## Repository Structure

.
├── main.ipynb              # Main experiment notebook

└── README.md

---

## Dataset

The ImageNet dataset must be downloaded separately from:
https://image-net.org/index.php

Please specify the local ImageNet path directly in `main.ipynb`.

---

## Supported Optimizers

The following optimizers are evaluated as inner-loop adversarial optimizers:
	•	SGD
	•	SGD + Momentum
	•	Adam
	•	AdamW
	•	Adamax
	•	RMSProp
	•	Adagrad

All optimizers are implemented using PyTorch and applied directly to the perturbation variable.

---

## Environment

Tested with:
- Python 3.10.15
- PyTorch 2.5.0
- torchvision
- numpy

--- 

## Usage

All experiments are implemented and can be reproduced by running `main.ipynb`.
Hyperparameters can be configured in the final cell of the notebook.