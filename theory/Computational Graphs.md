# Computational Graphs

A **computational graph** is a way to represent the sequence of operations in a model — like matrix multiplications, activations, loss calculations — as a graph of interconnected nodes (operations) and edges (data tensors). It enables automatic differentiation, which is essential for training neural networks.

There are two main types of computational graphs:

## 🔄 Dynamic Computational Graph (aka Eager Execution)

Used by: **PyTorch**, **JAX (by default)**

- The graph is **built on-the-fly** as operations are executed
- Feels like regular Python — intuitive, debuggable, step-by-step
- Great for experimentation, research, and rapid prototyping
- You can use native Python control flow (`if`, `for`, etc.) without extra tricks

🧠 **Analogy**: Like writing and executing each line of code immediately in a Python REPL.

✅ Pros:

- Easy to debug (e.g., use `pdb`, print shapes)
- Flexible for model architectures with dynamic behavior (e.g. RNNs, variable input lengths)
- Intuitive and beginner-friendly

❌ Cons:

- Slightly slower training performance (unless compiled with TorchScript or JIT)
- Harder to optimize globally across the whole model (because it's not known in advance)

## 🗂️ Static Computational Graph

Used by: **TensorFlow 1.x**, **TensorFlow 2.x with `@tf.function`**, **MXNet (hybrid mode)**

- The entire graph is **defined before execution** and then compiled
- You first **declare** the model's structure and only then run it
- Enables global optimization and graph-level transformations

🧠 **Analogy**: Like writing a full script, compiling it, then executing all at once.

✅ Pros:

- More performant for deployment (thanks to optimizations and graph compilation)
- Easier to export and run across different platforms (e.g., TFLite, XLA)
- Better suited for embedded/edge environments

❌ Cons:

- Harder to debug (no immediate feedback)
- More boilerplate (especially for conditionals, loops, etc.)
- Steeper learning curve

## Summary

| Feature           | PyTorch (Dynamic)           | TensorFlow (Static)      |
| ----------------- | --------------------------- | ------------------------ |
| Graph Definition  | On-the-fly (imperative)     | Predefined (declarative) |
| Debugging         | Simple, Pythonic            | Complex, indirect        |
| Flexibility       | High (e.g., variable input) | Low (needs workarounds)  |
| Deployment Speed  | Slower (unless compiled)    | Faster with compilation  |
| Beginner-Friendly | Yes                         | No                       |

---

📌 **Takeaway**: PyTorch’s dynamic graph makes it easier to learn, experiment, and iterate quickly —
which is why it has become the de facto standard in research.
