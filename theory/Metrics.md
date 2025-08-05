# Metrics

*A metric* is a function that measures the quality of the model’s predictions using the validation set. It is printed at the end of each epoch during training.

`error_rate` is a metric that tells how many items from the validation set are classified incorrectly.

Another common metric for classification is `accuracy` — `1.0 - error_rate`.

A metric is defined for human consumption. A good metric is one that is easy to understand.

Don't use *loss* as your metric. The entire purpose of loss is to define a “measure of performance” that the training system can use to update weights automatically.
