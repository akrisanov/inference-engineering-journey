# Convolutional Neural Networks (CNNs)

## How CNNs Learn: Step-by-Step

Here's how ResNet and similar image recognizers learn using these layers:

1. **Input image** — The image is passed into the network (e.g., a cat photo)
2. **Forward pass through layers**
    1. Layer 1 detects edges
    2. Layer 2 combines those into textures and patterns
    3. Higher layers combine them into parts and whole objects
3. **Prediction** — The last layer (fully connected or classification head) makes a prediction: “cat,” “dog,” “car,” etc.
4. **Loss computation** — The network compares the prediction to the **true label** (e.g., “cat”) and calculates a **loss** (how wrong the prediction was)
5. **Backpropagation** — The model calculates gradients (how much each neuron contributed to the error) and **updates the weights** in all layers using gradient descent.
6. **Repeat** — This process is repeated across millions of images during training

## What Are CNN Layers Doing?

Think of a CNN like a visual processing pipeline. Each **layer** extracts increasingly complex patterns from the input image:

### Layer 1

- Detects **basic features** like edges, lines, and simple colors
- These are akin to Gabor filters in early human vision

### Layer 2

- Detects **combinations** of those basic features: corners, circles, textures, color transitions, curves, etc.
- We start seeing structured patterns, often resembling shapes like wheels, eyes, or ripple effects

### Deeper layers (Layer 3+)

- Start detecting **parts of objects** (e.g., fur, textures, eyes, wheels)
- Eventually, full **object representations** like faces, animals, or tools emerge

> The main principle: progressively learn more complex visual features layer by layer.

## What Layers Have to Do with Learning

- Each layer in a CNN has **filters (aka kernels)** with learnable weights
- These weights determine what features the layer will detect
- The training process **optimizes** these weights so that the network becomes good at detecting patterns helpful for classification

So, learning in a CNN = **learning good filters per layer**.

## What the Figure Shows

[Visualizing and Understanding Convolutional Networks](https://arxiv.org/pdf/1311.2901)

![[assets/Screenshot 2025-08-05 21-14-01.png]]

**Left side**: Visualizations of Layer 2 filters after training. Each grid shows what kind of patterns activate a filter (e.g. spirals, arcs, stripes).

**Right side**: Image patches from real data that highly activate specific Layer 2 neurons. These are examples of “what the network pays attention to.”

This helps us understand the **interpretability** of what a CNN learns at each stage.
