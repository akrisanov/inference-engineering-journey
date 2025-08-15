# 2025-08-13, Wednesday

## 🎯 Goals for Today

- [x] Watch [Khan Academy: Linear subspaces](https://www.khanacademy.org/math/linear-algebra/vectors-and-spaces/subspace-basis/v/linear-subspaces)
- [x] Watch [Khan Academy: Basis of a subspace](https://www.khanacademy.org/math/linear-algebra/vectors-and-spaces/subspace-basis/v/linear-algebra-basis-of-a-subspace)
- [x] Work through examples shown in the videos — manually and in PyTorch
- [x] Add a few examples for 2D, 3D, and higher dimensions
- [ ] Make Anki cards

## 📖 What I Studied

### Linear subspaces

Subspace of $\mathbb{R}^n$ is just an infinitely large set of vectors $\{\begin{bmatrix} x_1 \\ x_2 \\ x_3\end{bmatrix}\}, x_i\in\mathbb{R}, 1\le i \le n$

$V$ — subset of $\mathbb{R}^n$

To become **a subspace of $\mathbb{R}^n$**, $V$ has to:

first, contain a zero vector $0 = \begin{bmatrix} 0 \\ 0 \\ ... \\ 0\end{bmatrix}$
$\vec x$ in $V$ = $c\vec x$ in $V$ (*closure under multiplication*) — if I take some member of my set and multiply it on some scalar, I'm still going be in my set. Otherwise $V$ wouldn't be a subspace.

$a$ in $V$
$b$ in $V$
$\vec a + \vec b$ in $V$
*close under addition* -> we still end up with a vector withing a subset

Is $V = \{0\} = \{\begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix}\}$ a subspace of $\mathbb{R}^3$?

1. It includes zero vector
2. It is closed under multiplication, i.e. $c\begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix} = \begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix}$
3. It is closed under addition, i.e. there is no other vector in a $V$ we can add to $\begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix}$ -> $\begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix} + \begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix} = \begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix}$
So, the answer is yes.

Another example:

![Векторное представление](assets/Pasted%20image%2020250815090122.png)

What if we consider $U = span(\vec v_1, \vec v_2, \vec v_3)$. Is it valid subspace of of $\mathbb{R}^n$?
$0\vec v_1 + 0\vec v_2 + 0\vec v_3 = 0$

$\vec x = c_1\vec v_1 + c_2\vec v_2 + c_3\vec v_3$
$a\vec x = ac_1\vec v_1 + ac_2\vec v_2 + ac_3\vec v_3$, $a\vec x$ in $U$ -> closed under multiplication

$\vec y = d_1\vec v_1 + d_2\vec v_2 + d_3\vec v_3$
$\vec x + \vec y = (c_1 + d_1)\vec v_1 + (c_2 + d_2)\vec v_2 + (c_3 + d_3)\vec v_3$ — another linear combination -> closed under addition

Even $U = span(\begin{bmatrix}0 \\ 0\end{bmatrix})$ is a valid subspace of $\mathbb{R}^2$.

**The span of any set of vectors is a valid subspace.**

### Basis of a subspace

$V = span(\vec v_1, \vec v_2, ..., \vec v_n)$ — subspace, $\{\vec v_1, ..., \vec v_n\}$ are *linearly independent*, i.e. $c_1\vec v_1 + c_2\vec v_2 + ... c_n\vec v_n = 0$ -> $c_1 = c_2 = ... = c_n = 0$

$S = \{\vec v_1, \vec v_2, ..., \vec v_n\}$
$S$ is a **basis** for $V$

If we add a new vector, such as $\vec v_1 + \vec v_2$ to the $S$ set, it stops being a basis for $V$.

Basis is a **minimum** set of vectors that spans the subspace.

![Геометрическая интерпретация](assets/Pasted%20image%2020250815102649.png)

## 💡 Insights and Reflections

- **Basis** = smallest set of independent vectors that span the space

## 💻 PyTorch Practice

**Task 1 — Compute Basis via Rank**

`torch.linalg.matrix_rank` finds the dimension of the span of the rows (or columns — rank is the same either way).

**Rank** = *number of linearly independent vectors*.

```python
import torch

# Example set of vectors
vectors = [
    torch.tensor([1., 2., 3.]),
    torch.tensor([4., 5., 6.]),
    torch.tensor([7., 8., 9.])
]

# Stack into matrix
mat = torch.stack(vectors)

# Find rank (dimension of span)
rank = torch.linalg.matrix_rank(mat)
print("Dimension of span:", rank.item()) # => 2
```

**Task 2 — Extract a Basis**
(Simple approach: keep only independent vectors)

```python
def basis_from_vectors(vectors):
    basis = []
    for v in vectors:
        if not basis:
            basis.append(v)
        else:
            mat = torch.stack(basis + [v])
            if torch.linalg.matrix_rank(mat) > len(basis):
                basis.append(v)
    return basis

basis_vectors = basis_from_vectors(vectors)
print("Basis vectors:", basis_vectors) # => Basis vectors: [tensor([1., 2., 3.]), tensor([4., 5., 6.])]
print("Basis dimension:", len(basis_vectors)) # => Basis dimension: 2
```

💡 **Basis** is a set of *linearly independent* vectors that span the space.

### Example

Here you can see it visually:

- **Red** = $\vec v_1$
- **Green** = $\vec v_2$
- **Blue** = $\vec v_3$​ (lies in the same plane)
- **Cyan plane** = all linear combinations of $\vec v_1$​ and $\vec v_2$

Because all three vectors lie in that same 2D plane in $\mathbb{R}^3$, the **basis** has only 2 vectors → dimension = 2.

![Пример 1](assets/Pasted%20image%2020250815105633.png)

![Пример 2](assets/Pasted%20image%2020250815110505.png)

## ❓ Questions

- Why dimension = number of basis vectors?
