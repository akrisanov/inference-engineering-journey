# Fastai: A Layered API for Deep Learning

> <https://docs.fast.ai/>

Fastai: A Layered API for Deep Learning paper: [Information Journal](https://www.mdpi.com/2078-2489/11/2/108) or [arxiv](https://arxiv.org/abs/2002.04688) or [fast.ai](https://www.fast.ai/2020/02/13/fastai-A-Layered-API-for-Deep-Learning/)

## Example

```python
def is_cat(x):
    return x[0].isupper()

dls = ImageDataLoaders.from_name_func(
    path,
    get_image_files(path),
    valid_pct=0.2, seed=42,
    label_func=is_cat,
    item_tfms=Resize(224))

learn = cnn_learner(dls, resnet34, metrics=error_rate)
learn.fine_tune(1)
```

A `Transform` contains code that is applied automatically during training. There are two kinds:

- `item_tfms` are applied to each item (in this case, each item is resized to a 224-pixel square)
- `batch_tfms` are applied to a batch of items at a time using the GPU (fast)

The the standard size (224px) is used for historical reasons (old pretrained models require this size exactly), but we can pass pretty much anything. By increasing the size, we’ll often get a model with better results (more details to be able to focus on), but in exchange of speed and memory consumption.
