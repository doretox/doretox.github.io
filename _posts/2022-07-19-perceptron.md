---
layout: post
title:  "Understanding the Linux file system"
description: Understanding how Linux file system is organized.
date:   2020-04-13 00:00:00 +0530
categories: [Linux]
---
The Perceptron was created in 1958 by Rosenblatt, being the most simple form of an artificial neural network, built of one single neural layer and a single neuron.
The following image shows how a perceptron works.

![Perceptron](/images/perceptron/perceptron.png)

For inputs, we have a vector of values and a vector of weights. The computation of a single layer perceptron is performed over the calculation of the sum of the input vector each with the value multiplied by the corresponding element of the vector of the weights. The value displayed in the output will be the input of an activation function.

The activation function will return 0 or 1. If the return is 0 the neuron will not activate, if the result is 1 the neuron will activate.
Down below you can see a simple code representation of a perceptron.

```python
import numpy as np

# if you change the first value to -1 in inputs, the neuron will return 0 and
# will not activate.
inputs = np.array([1, 7, 5])
weights = np.array([0.8, 0.1, 0])


def multiply_and_sum(i, w):
    """Multiply and sum all the inputs and weights."""
    return i.dot(w)  # dot product


s = multiply_and_sum(inputs, weights)


def step_function(sm):
    """Determine if the neuron will of not activate."""
    if sm >= 1:
        return 1
    return 0


r = step_function(s)
print(r)
```
