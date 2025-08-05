# What Is a Neural Network?

## Definitions

- **A neural network** is a specific type of machine learning model composed of layers of simple mathematical functions that are adjusted (trained) to approximate solutions to complex problems.

- The **functional form** of the model is called its **architecture**. _(Sometimes, “model” is used as a synonym for “architecture.”)_

- The model’s adjustable values are called **parameters**, often referred to as **weights** in the context of neural networks.

- **Predictions** are calculated from the **independent variables** — i.e., the **input data** excluding the labels.

- The **results** produced by the model are called **predictions**.

- The **measure of performance** is called the **loss**.

- The _loss_ depends not only on the _predictions_, but also on the correct _labels_ (also known as **targets** or the **dependent variable**); e.g., “dog” or “cat.”

- The **loss** depends on both the model’s **predictions** and the correct **labels** (also known as the **targets** or the **dependent variables**, e.g., “dog” or “cat”).

- When using a pretrained model, we remove its final layer — which is specific to the original task — and replace it with a new _head_: one or more layers with randomly initialized weights sized for our target dataset.

- **Transfer learning** is the practice of using a pretrained model for a task different from the one it was originally trained on.

- A process to adapt a pretrained model for a new dataset is called **fine-tuning**.

- **Epoch** – One complete pass through the entire training dataset. In practice, the number of epochs controls how many times the model "sees" each training example. _The number of epochs is a key training parameter._ Choosing it depends on available time and how quickly the model starts to generalize.

## Key Ideas from fast.ai

- It’s often **not obvious what features a model should look for** in tasks like image recognition, language understanding, or other complex domains
- Is there a type of function that’s **flexible enough** to solve _any_ problem, simply by adjusting its weights?
- The answer is yes — this function is called a **neural network**, and it aligns well with Arthur Samuel’s original idea of machine learning through weight assignment
- The [**Universal Approximation Theorem**](https://www.deep-mind.org/2023/03/26/the-universal-approximation-theorem/) shows that, in theory, a neural network can approximate _any_ function to _any_ desired level of accuracy
- To make a neural network perform better at a task, we need a **general method for finding and updating its weights**. This is called **Stochastic Gradient Descent (SGD)**
- Neither neural networks nor SGD are particularly complex mathematically — they primarily rely on **repeated addition and multiplication** (just at large scale)
- To evaluate “actual performance,” we can define it simply: _How accurate is the model at predicting the correct label?_

### Example

- **Inputs**: images (e.g. a picture of a dog or a cat)
- **Model**: a neural network
- **Weights**: internal adjustable parameters of the network
- **Output**: predicted class (e.g. “dog” or “cat”)

#### Detailed Training Loop

![[assets/Screenshot 2025-08-05 at 08.58.09.png|Detailed Training Loop]]
