# 2025-08-06, Wednesday

## 🎯 Goals for Today

- [x] Finish [Fastbook: Chapter 1, Intro](https://colab.research.google.com/github/fastai/fastbook/blob/master/01_intro.ipynb)
- [x] Answer questions in Questionnaire
- [x] Answer questions in Further Research
- [ ] Create cards for spaced repetition
- [ ] Read [notes on learning deep learning](../daily_journal/assets/meta%20learning%20how%20to%20learn%20deep%20learning%20and%20thrive%20in%20the%20digital%20world%20notes.pdf)

## 📖 What I Studied

- Image recognizers can be applied to other kinds of problems such as sound analysis, fraud detection, and security
- Deep learning is suitable for a wide range of problems — from image classification to recommendation systems
- A validation set is important to avoid the model memorizing the data and performing poorly on new data
- A test set is also crucial for model assessment and helps avoid failure in DL projects

## 💡 Insights and Reflections

- Many problems can be reframed as image recognition tasks
  - Sound → spectrogram
  - Time series → graph
  - Mouse behavior → image
- How you represent your data is critical
- If a human can recognize categories in images, a model likely can too
- `doc(func)` in [Jupyter](../tools_and_frameworks/Jupyter.md) shows brief documentation for a [fastai](../tools_and_frameworks/fastai.md) function
- Tabular data comes from tables (e.g. spreadsheets, databases, CSVs)
- Pretrained models are generally unavailable for tabular or recommendation data
- Start with small data subsets for experimentation; use the full dataset only when confident
- Overfitting isn't just for models — we can overfit validation data through repeated trial and error
- To avoid this, introduce a test set held back even from ourselves — only used for final evaluation
- Training uses the training set
- Hyperparameter tuning uses the validation set
- Final assessment uses the test set
- Models tend to memorize; humans tend to overestimate performance
- If using external vendors, ensure they never see your test data
- Always try a simple baseline to know what a basic model can achieve
- Validation/test sets must reflect the data your model will see in production
  - For time series, use earlier data for training and later data for validation
  - For image classification tasks involving people, don’t include pictures of the same individual in both the training and validation sets.

## ❓ Questions

- What are hyperparameters?

## Questionnaire

- Do you need these for deep learning?
  - Lots of math — false
  - Lots of data — false
  - Lots of expensive computers — false
  - A PhD — false
- Name five areas where deep learning is now the best tool in the world
  - NLP
  - CV
  - Recommendation systems
  - Medicine (e.g. diagnostics, radiology)
  - Biology (e.g. protein folding, genomics)
- What was the name of the first device that was based on the principle of the artificial neuron?
  - The **Perceptron** was invented by Frank Rosenblatt in 1958
  - It was the first hardware implementation based on the idea of the artificial neuron
  - It could perform simple binary classifications by learning weights from input data
- Based on the book of the same name, what are the requirements for parallel distributed processing (PDP)?
  - **Distributed Representations**: Information is not stored in a single unit, but across many units in a pattern of activation
  - **Processing Units (Neurons)**: Simple computational units that activate based on input from other units
  - **Connections and Weights**: Units are connected by weighted links, and learning occurs by adjusting these weights
  - **Parallel Processing**: Processing occurs simultaneously across many simple units, each performing basic local computations — no central controller
  - **Graceful Degradation**: The system is robust — even if parts are damaged or inputs are noisy, it degrades gradually rather than failing completely
- What were the two theoretical misunderstandings that held back the field of neural networks?
  - Neural nets are fundamentally limited (e.g. can’t solve XOR) -> Only true for single-layer networks
  - Deep nets are too hard to train -> Solved with backpropagation, GPUs, and more data
- What is a GPU?
  - A **GPU** is a processor designed to perform many calculations **in parallel**, making it ideal for tasks like training neural networks.
- Why is it hard to use a traditional computer program to recognize images in a photo?
  - Because it's nearly impossible to explicitly program all the patterns, variations, and edge cases that appear in real-world images
- What did Samuel mean by “weight assignment”?
  - Adjusting the weights in a model to influence how much each input contributes to the final prediction — a process now known as training
- What term do we normally use in deep learning for what Samuel called “weights”?
  - Parameters
- Draw a picture that summarizes Samuel’s view of a machine learning model
  - input, weights -> model -> results
- Why is it hard to understand why a deep learning model makes a particular prediction?
  - A deep learning model is often considered a black box because it has many layers and parameters that interact in complex, nonlinear ways.
  - Understanding why it makes a particular prediction requires analyzing how information flows through each layer and how the learned features combine to produce the output.
- What is the name of the theorem that shows that a neural network can solve any mathematical problem to any level of accuracy?
  - The [**Universal Approximation Theorem**](https://www.deep-mind.org/2023/03/26/the-universal-approximation-theorem/)
- What do you need in order to train a model?
  - An **architecture** — the model structure (e.g. ResNet, Transformer)
  - A **training set** — labeled data used to learn
  - A **validation set** — data to evaluate generalization and tune parameters
  - A **loss function** — tells the model how wrong its predictions are
  - A **metric** — a human-readable measure of model performance (e.g. accuracy)
- How could a feedback loop impact the rollout of a predictive policing model?
  - The model stops learning from reality and starts learning from its **own outputs**, creating a self-fulfilling bias
- Do we always have to use 224×224-pixel images with the cat recognition model?
  - 224×224 is a convention, not a requirement. Choose image size based on what works best for your dataset and model.
- What is the difference between classification and regression?
  - Classification — Predicts a category or label, such as "dog" or "cat"
  - Regression — Predicts a continuous number, such as a price, temperature, or weight
- What is a validation set? What is a test set? Why do we need them?
  - A **validation set** is a portion of the dataset **excluded from training** but used during development to evaluate the model’s performance and guide decisions like hyperparameter tuning or architecture changes.
  - We use a **validation set** to catch overfitting during training and guide improvements.
  - A **test set** is a separate portion of the data that is **completely held out** — not used during training or model selection, and ideally not even seen by the developers. It is used **only once** at the end to assess how well the model generalizes to truly unseen data.
  - We use a **test set** to ensure that our final evaluation is unbiased — simulating how the model would perform in the real world.
- Can we always use a random sample for a validation set? Why or why not?
  - **No**, we can't always use a random sample for a validation set. It depends on the nature of the problem and the structure of the data.
- What is overfitting? Provide an example.
  - **Overfitting** happens when a model learns to **memorize the training data** instead of learning patterns that generalize to new, unseen data. It performs well on the training set but poorly on the validation or test set.
  - If some data points from the **validation set leak into the training set**, the model may learn to predict them perfectly — not because it understands the underlying patterns, but because it has **seen them before**. As a result, the model appears accurate during training but fails to generalize.
- What is a metric? How does it differ from loss?
  - A **metric** (such as accuracy or error rate) is a human-friendly way to **evaluate model performance**. It helps us understand how well the model is doing, but it's not used to update the weights.
  - A **loss** is a function (such as cross-entropy or mean squared error) used by the training algorithm to **optimize the model’s weights**. It measures how far the model’s predictions are from the true labels.
- How can pretrained models help?
  - It can save time, resources and speed up development by reusing knowledge from large datasets.
  - We can fine-tune pretrained models for our specific tasks.
- What is the “head” of a model?
  - The **head** of a model refers to the **final layers** that are added (or replaced) during fine-tuning to adapt a pretrained model to a **specific task**.
  - These layers are initialized with random weights and trained on your dataset, while the earlier layers (the "body") retain knowledge from pretraining.
- What kinds of features do the early layers of a CNN find? How about the later layers?
  - Early layers detect low-level features like edges, textures, and simple shapes
  - Later layers detect high-level features, such as object parts or combinations of features that resemble full objects or target classes
- Are image models useful only for photos?
  - No. With enough creativity, image models can be applied to other types of data that can be visually represented.
- What is an architecture?
  - An architecture is the template or structure of a model — it defines how the layers are arranged and how data flows through them.
- What is segmentation?
  - Segmentation is the process of classifying each individual pixel in an image into a specific category, e.g.identifying which pixels belong to pedestrians, cars, or background.
- What is `y_range` used for? When do we need it?
  - `y_range` is used in **regression** to specify the **range of target values** the model should predict.
  - It ensures that the model’s output stays within a defined interval avoiding unrealistic values.
- What are **hyperparameters**?
  - Hyperparameters are settings that control how a model is trained, but are not learned by the model itself. They must be set manually (or tuned) before training begins.
  - Common examples:
    - *Learning rate* – how fast the model updates weights during training
    - *Batch size* – how many samples are processed at once
    - *Number of epochs* – how many times the model sees the full training data
    - *Optimizer type* – e.g. Adam, SGD
    - *Dropout rate* – how much to randomly ignore during training to prevent overfitting
    - *Weight decay* – controls regularization strength
- What’s the best way to avoid failures when using AI in an organization?
  - One of the best ways is to establish a simple baseline model and hold out a test set that is hidden from everyone involved in development.

## Further Research

- Why is a GPU useful for deep learning? How is a CPU different, and why is it less effective for deep learning?
  - A **GPU (Graphics Processing Unit)** is designed to perform **many simple calculations in parallel**, which makes it ideal for deep learning.
  - Training neural networks involves a lot of matrix and vector operations — especially in large batches — which GPUs can process very efficiently.
  - A **CPU (Central Processing Unit)** has fewer, more powerful cores optimized for **sequential tasks** and general-purpose computing.
  - It can handle complex logic and multitasking well, but it struggles with the **massively parallel** math operations deep learning requires.

|Feature|GPU|CPU|
|---|---|---|
|Core type|Many small cores|Few powerful cores|
|Strength|Parallel math (e.g. matrix ops)|General-purpose, sequential tasks|
|DL performance|Fast training and inference|Much slower for large models|

- Try to think of three areas where feedback loops might impact the use of machine learning. See if you can find documented examples of that happening in practice.
  - **Search/Recommendations**: The system promotes what users click → users click what they see → the system reinforces those types of results
    - [Mozilla Report on YouTube Recommendations (2021)](https://foundation.mozilla.org/en/blog/tracking-youtube-algorithm/)
    - [Zeynep Tufekci, TED Talk: “We're building a dystopia just to make people click on ads](https://www.ted.com/talks/zeynep_tufekci_we_re_building_a_dystopia_just_to_make_people_click_on_ads)
  - **Predictive Policing**: The model predicts high crime in certain neighborhoods → more policing in those areas → more arrests and reports → the model sees "high crime" → and keeps reinforcing the same outcome
    - [“PredPol: How Predictive Policing Reinforces Police Bias” – The Markup](https://themarkup.org/2021/12/07/predpol)
    - [ACLU: Predictive Policing Today](https://www.aclu.org/issues/privacy-technology/surveillance-technologies/predictive-policing)
  - **Hiring and Resume Screening**: The system is trained on resumes from previously hired candidates → it learns patterns from past (possibly biased) hiring → reinforces those patterns → continues filtering out qualified but “non-traditional” applicants
    - [Reuters: “Amazon scraps secret AI recruiting tool that showed bias against women”](https://www.reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G)
