# Neural Networks

## Definitions

**A neural network** is a specific type of machine learning model composed of layers of simple
mathematical functions that are adjusted (trained) to approximate solutions to complex problems.

---

**Label** is the data that we're trying to predict, such as "dog" or "cat".

**Architecture** is the *template* of the model that we're trying to fit; i.e., the actual
mathematical function that we're passing the input data and parameters to.

**Model** is the combination of the architecture with a particular set of parameters.

**Parameters** (**weights** in the context of neural networks) are the values in the model that
change what task it can do and that are updated through model training.

**Fit** is update the parameters of the model such that the predictions of the model using the input
data match the target labels.

**Train** is a synonym for *fit*.

**Pretrained model** is a model that has already been trained, generally using a large dataset,
and will be fine-tuned.

**Fine-tune** is update a pretrained model for different task.

**Epoch** is one complete pass through the entire training dataset; controls how many times the
model "sees" each training example.

**Loss** is a measure of how good the model is (*performance* on a single prediction), chosen to
drive training via SGD.

**Metric** is a measurement of how good the model is using the validation set, chosen for human consumption.

**Validation set** is a set of data held out from training, used only for measuring how good the model is.

**Training set** is the data used for fitting the model; doesn't include any data from the validation set.

**Overfitting** is training a model such a way that it *remembers* specific features of the input data,
rather than generalizing well to data not seen during training.

**Predictions** are the results produced by the model; they are calculated from the independent
variables — i.e., the input data excluding the labels.

When using a pretrained model, we remove its final layer — which is specific to the original task —
and replace it with a new **head**: one or more layers with randomly initialized weights sized
for our target dataset.

**Transfer learning** is the practice of using a pretrained model for a task different from the one
it was originally trained on.

## Key Ideas from fast.ai

- It’s often **not obvious what features a model should look for** in tasks like image recognition,
  language understanding, or other complex domains
- Is there a type of function that’s **flexible enough** to solve *any* problem, simply by adjusting its weights?
- The answer is yes — this function is called a **neural network**, and it aligns well with
  Arthur Samuel’s original idea of machine learning through weight assignment
- The [**Universal Approximation Theorem**](https://www.deep-mind.org/2023/03/26/the-universal-approximation-theorem/)
  shows that, in theory, a neural network can approximate *any* function to *any* desired level of accuracy
- To make a neural network perform better at a task, we need a **general method for finding and updating its weights**.
  This is called **Stochastic Gradient Descent (SGD)**
- Neither neural networks nor SGD are particularly complex mathematically — they primarily rely on
  **repeated addition and multiplication** (just at large scale)
- To evaluate “actual performance,” we can define it simply: *How accurate is the model at
  predicting the correct label?*

### Example

- **Inputs**: images (e.g. a picture of a dog or a cat)
- **Model**: a neural network
- **Weights**: internal adjustable parameters of the network
- **Output**: predicted class (e.g. “dog” or “cat”)

#### Detailed Training Loop

![[assets/Screenshot 2025-08-05 at 08.58.09.png|Detailed Training Loop]]
