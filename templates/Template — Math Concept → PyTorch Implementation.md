# {{Concept Name}}  <!-- e.g. Vector Addition -->

## 📘 Definition

A short, plain-language description of the concept.

Example:
> Vector addition combines two vectors of the same dimension by adding their corresponding components.

---

## 🧠 Key Properties

- Property 1
- Property 2
- Property 3

---

## ✏️ Math Example

Given vectors:  
\[
\mathbf{a} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} 3 \\ 4 \end{bmatrix}
\]

Their sum is:
\[
\mathbf{a} + \mathbf{b} = \begin{bmatrix} 4 \\ 6 \end{bmatrix}
\]

---

## 💻 PyTorch Implementation

```python
import torch

a = torch.tensor([1, 2])
b = torch.tensor([3, 4])
result = a + b
print(result)  # tensor([4, 6])
