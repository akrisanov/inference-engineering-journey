# What is Machine Learning?

#ML #DL #week1

## Definitions

...

## Key Ideas from fast.ai

...

## 📖 Notes from *fastbook* Ch.1

A normal computer program:

![[Screenshot 2025-08-02 at 16.01.38.png]]

---

In 2012, this is how image recognition was done:

![](./assets/Screenshot%202025-08-02%20at%2016.01.38.png)

This is the classical ML (pre-deep learning) approach. While it was successful, such projects took
**years**, involved **many people**, required **tons of code**, and relied heavily on **handcrafted math**.

Once the team spent enormous resources building features, they passed them into a machine learning model.

> In deep learning, we don't feed features to a model — we ask it to learn them.

---

Deep learning is called *deep* because it stacks multiple layers of transformations. These layers
combine low-level features to form more abstract and complex representations. The deeper the network,
the more sophisticated the features it can extract.

![](assets/Screenshot%202025-08-02%20at%2014.43.11.png)

---

Image-based algorithms aren't just for images. For example, sound classification often begins by
converting audio into images (like spectrograms), which are then processed using vision models.

> 💡 With some creativity, we can do a lot of things with images.

![](assets/Screenshot%202025-08-02%20at%2014.47.32.png)

This general approach works for many real-world tasks.

Computer vision isn’t just for object recognition — it's broadly applicable to classification problems.

---

Another powerful use case is **tabular data analysis**.
Unlike with vision or NLP, there aren’t standard pre-trained models for tabular problems — because
every table is different. That’s why fine-tuning makes less sense here. Instead, we usually train
from scratch using simple `.fit()` methods.

---

**Collaborative filtering** is the basis for most modern recommendation systems.
We try to predict what other products a user might like by identifying similar users and seeing what they’ve liked.

---

`MSE` (Mean Squared Error) tells us how far, on average, our predictions are from the validation set.

![](assets/Screenshot%202025-08-02%20at%2016.02.59.png)

A model is just a mathematical function — it won’t do anything useful until its weights are carefully tuned.

![](assets/Screenshot%202025-08-02%20at%2016.05.53.png)

We measure how good the model is by calculating the **loss**.
Then, we **iterate** to improve performance — often measured with metrics like accuracy.

> How do we define the `update` step that improves our model?

---

Once the model is trained, we no longer need the loss function — we just save the weights and integrate
them into the model for inference. From that point on, using the model is similar to calling any
other function in a program.

![](assets/Screenshot%202025-08-02%20at%2016.10.15.png)

### 🤖 What We Can Do with Deep Learning

- **Natural Language Processing (NLP)**
  - Answering questions
  - Speech recognition
  - Summarizing documents
  - Classifying documents
  - Extracting names, dates, and other entities from text
  - Searching for articles that mention a concept

- **Computer Vision (CV)**
  - Interpreting satellite and drone imagery (e.g., for disaster resilience)
  - Face recognition
  - Image captioning
  - Reading traffic signs
  - Detecting pedestrians and vehicles in autonomous driving

- **Medicine**
  - Detecting anomalies in radiology scans (CT, MRI, X-ray)
  - Counting features in pathology slides
  - Measuring features in ultrasound images
  - Diagnosing diabetic retinopathy from retina scans

- **Biology**
  - Protein folding (e.g., AlphaFold)
  - Protein classification
  - Genomic analysis (e.g., tumor/normal sequencing, variant classification)
  - Cell classification
  - Modeling protein–protein interactions

- **Image Generation**
  - Colorizing black-and-white images
  - Increasing image resolution (super-resolution)
  - Removing noise from images (denoising)
  - Style transfer (e.g., turning photos into Van Gogh-style art)

- **Recommendation Systems**
  - Personalized product recommendations
  - Optimizing web search results
  - Dynamically generating homepage layouts

- **Games**
  - Playing Chess, Go, and most Atari video games
  - Mastering complex real-time strategy games (e.g., StarCraft II)

- **Robotics**
  - Handling difficult-to-manipulate objects (e.g., transparent, reflective, or textureless items)
  - Navigating real-world environments with partial or noisy information

- **Other Applications**
  - Financial forecasting
  - Supply chain and logistics optimization
  - Text-to-speech synthesis
  - Real-time translation

## My Own Understanding

...
