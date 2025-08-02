# PyTorch

## PyTorch vs TensorFlow

TensorFlow's popularity has been steadily declining since around 2018–2019, especially in research.

Most modern deep learning researchers and practitioners have adopted PyTorch due to its:

- Pythonic, imperative style
- Dynamic computation graph (eager execution)
- Cleaner integration with Python debugging tools
- Growing ecosystem (e.g., Hugging Face, Lightning, fastai)

By contrast, TensorFlow’s static graph paradigm and complex APIs have made it harder for newcomers and slower to iterate.

**Notable exceptions**: TensorFlow is still widely used in some production environments
(especially with TFX, TensorFlow Lite, and TensorFlow.js) and Google-backed infrastructure.

## PyTorch Disadvantages

- More boilerplate for some tasks compared to `fastai`, `Keras`, or `sklearn`
- Less out-of-the-box support for mobile/web deployment (compared to TensorFlow Lite / TF.js)
- Fewer mature, official high-level tools for full ML pipelines (though this is changing fast)
- Serialization (saving/loading models) is slightly more brittle than in TensorFlow SavedModel format
- Historically lagged in distributed training support, though newer tools like `torch.distributed`,
`Lightning`, and `Accelerate` are closing that gap
