# What is Machine Learning?

## Definitions

- **Machine learning** is the process of training programs by allowing a computer to learn from experience, rather than manually coding every individual step.

- **Deep learning** is a subfield of machine learning that focuses on learning from data using multi-layered neural networks.

- A **validation set** is used to measure the accuracy of the model and often is selected randomly.

- The **random seed** is the value we use for this random selection process. We use the same value to get the same validation set every time we run our code and make sure our model improves by retraining and not by a different validation set.

- Eventually model accuracy will start getting worse as the model starts to memorize the training set rather than finding generalizable underlying patterns in data. When this happens, we say that the model is **overfitting**.

## Key Ideas from fast.ai

- In **1949**, Arthur Samuel introduced the idea of machines learning from experience
- In **1962**, he published _Artificial Intelligence: A Frontier of Automation_, proposing that:
    > Instead of telling the computer the exact steps required to solve a problem, show it examples and let it figure out the solution itself.

### Core Components of Machine Learning (according to Samuel)

#### Weight Assignment

- _Weights_ are just variables
- _A weight assignment_ is a particular choice of values for those variables → _how the program will operate_
- _The program’s inputs_ are values that it processes in order to produce its results

![[assets/Screenshot 2025-08-05 at 07.53.53.png|A program using weight assignment]]

- A **model** is a special kind of program that behaves differently depending on its weights
- In modern ML, “weights” are typically called **model parameters**, and “weights” often refer to a specific kind of parameter (e.g., in neural nets)

#### Automatically Testing Performance

- We need a way to **measure the performance** of a given weight assignment
- Example: In a game of checkers, we can test how well a model plays (e.g., win rate, speed)
- One common method: let two models play against each other and measure which one wins more often

#### Mechanism for Improving Performance

- We need a way to update the weights to improve performance
- Example: Compare the weights of the winning model to the losing one, and adjust the weights slightly toward the winner’s configuration

#### Full Automation

- The training process automates all of the above: testing performance and adjusting weights

![[assets/Screenshot 2025-08-05 at 08.05.04.png|Training a machine learning model]]

#### Final Insight

- Once a model is trained, **its weights become part of the program**
- A **trained model** can then be used like any other computer program — it just happens to have learned its behavior from data

### Limitations Inherent to Machine Learning

- A model **cannot be created without data**
- A model can only learn from **patterns present in the training data** — it cannot generalize beyond what it has seen
- Machine learning models generate **predictions**, not **recommendations** or **decisions**. They attempt to replicate labels, not prescribe actions.
- Having examples of input data is **not sufficient** — we also need **labeled data** to train the model
- In practice, saying _“we don’t have enough data”_ usually means _“we don’t have enough labeled data”_
- ML systems are vulnerable to **feedback loops** in real-world scenarios
- A **positive feedback loop** occurs when a model’s predictions influence future data collection, reinforcing biases and making the model even more skewed over time
