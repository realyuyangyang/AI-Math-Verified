# Contributing to AI-Math-Verified

Thank you for your interest in **AI-Math-Verified**.

This project aims to build a complete understanding of Artificial Intelligence through **mathematics**, **implementation**, and **experimental verification**.

---

# Project Philosophy

Every topic in this repository should answer four questions:

1. **What is it?** (Theory)
2. **Why does it work?** (Mathematics)
3. **How is it implemented?** (Code)
4. **How can we verify it?** (Experiments)

The goal is not only to reproduce algorithms, but also to understand and validate them from first principles.

---

# Repository Structure

Each top-level module follows the same structure:

```text
module/
├── README.md
├── theory/
├── mathematics/
├── code/
├── experiments/
├── references/
└── assets/
```

## Directory Responsibilities

### README.md

Module overview, learning objectives, and navigation.

### theory/

Conceptual explanations with minimal mathematics.

### mathematics/

Complete mathematical derivations and proofs.

### code/

Implementations from scratch using NumPy and/or PyTorch.

### experiments/

Reproducible experiments that verify theoretical conclusions.

Examples include:

* Numerical Gradient Check
* Optimization Comparison
* Variance Analysis
* Attention Visualization
* Loss Curves

### references/

High-quality learning resources.

Examples include:

* Research papers
* Books
* Official documentation
* Educational articles

### assets/

Images, figures, animations, and experiment outputs.

---

# Coding Principles

* Prefer readability over clever implementations.
* Keep implementations simple and educational.
* Avoid unnecessary abstractions.
* Clearly explain important equations.
* Keep experiments reproducible.

---

# Mathematical Principles

Every mathematical derivation should:

* Clearly define symbols.
* Explain intermediate steps.
* State assumptions when necessary.
* Connect equations to implementation.

---

# Experiment Principles

Every experiment should have:

* Objective
* Method
* Expected result
* Conclusion

Experimental results should support or validate the mathematical analysis whenever possible.

---

# Naming Conventions

Directories:

```text
lowercase-with-hyphens
```

Examples:

```text
gradient-descent
batch-normalization
multi-head-attention
```

Python files:

```text
snake_case.py
```

Examples:

```text
gradient_check.py
attention_visualization.py
```

---

# Project Goals

This repository is designed to become a comprehensive AI learning resource covering:

* Mathematics
* Machine Learning
* Deep Learning
* Neural Network Architectures
* Transformer
* Large Language Models

Every module should follow the same philosophy:

> **Theory → Mathematics → Code → Experiments → Verification**

---

# License

Unless otherwise stated, all source code and documents follow the repository license.

