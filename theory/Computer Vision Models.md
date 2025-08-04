## ResNet-18

**ResNet-18** is no longer considered the fastest widely used computer vision model. While it’s still a common baseline in research and small-scale applications due to its simplicity and interpretability, it has been surpassed in both **speed** and **accuracy** by newer architectures. Here’s a breakdown of the current landscape:

## EfficientNet (especially EfficientNet-Lite or EfficientNetV2)

- Designed for edge devices
- Much better **accuracy-to-FLOPs** ratio than ResNet-18
- Widely used in mobile and real-time applications

## MobileNetV3

- Optimized for **speed on mobile and embedded hardware**    
- Outperforms ResNet-18 in both **latency** and **parameter efficiency**

## Vision Transformers (ViT, MobileViT, DeiT)

- While heavier in compute, **MobileViT** and **TinyViT** are competitive with ResNet-18 in latency but offer better accuracy

## ConvNeXt-Tiny or Nano

- Modern reinterpretation of ResNet-style networks with superior performance
- Comparable or faster than ResNet-18 depending on hardware and batch size

## Speed Comparison

> Inference Latency on CPU/Edge

| **Model**        | **Params** | **Throughput** | **Relative Latency**    |
| ---------------- | ---------- | -------------- | ----------------------- |
| ResNet-18        | ~11M       | Medium         | Baseline                |
| MobileNetV3-S    | ~2.9M      | High           | ~2x faster              |
| EfficientNetV2-S | ~21M       | High           | Similar/slightly faster |
| MobileViT-S      | ~5.6M      | Medium         | Similar/slightly slower |
## In Summary

- **ResNet-18** is still used as a simple, well-understood baseline
- For **production use** where speed matters (e.g. mobile, embedded, real-time systems), **MobileNetV3**, **EfficientNet-Lite/V2**, or **ConvNeXt-Tiny** are **much better choices**
- If you’re optimizing for **inference speed**, ResNet-18 is not the fastest anymore