# Take-Home Assignment: Simple CNN for Image Classification

## Overview

This take-home assignment evaluates your understanding of convolutional neural networks (CNNs) in PyTorch. You will implement a basic CNN for image classification.

The task is divided into **two steps**:
1. Build a basic convolutional block.
2. Extend it with a fully connected output layer.

Please write clean, well-documented code and include your parameter calculations as comments or markdown.

---

Assume you are designing a prototype image classifier for a dataset similar to **CIFAR-10**:

- Each image is a **32×32 RGB** image  
- There are **10 target classes**

# 🔧 Step 1: Basic Convolutional Block

## Task

Implement a PyTorch module with the following structure:

- One `Conv2d` layer  
  - `in_channels = 3`  
  - `out_channels = 16`  
  - `kernel_size = 3`  
  - `stride = 1`  
  - `padding = 1`  
- One `ReLU` activation

### Deliverables

1. Complete the class definition below.  
2. **Calculate the number of parameters** in the convolutional layer. Show your full calculation.  
3. *(Bonus)* Write a test function that:
   - Creates an instance of your model  
   - Passes a random tensor of shape `(1, 3, 32, 32)`  
   - Asserts that the output shape is `(1, 16, 32, 32)`  

### Template

```python
import torch
import torch.nn as nn

class Net(nn.Module):
    def __init__(self, in_channels, out_channels):
        super(Net, self).__init__()
        # TODO: Add convolutional layer and ReLU activation
        pass

    def forward(self, x):
        # TODO: Apply convolution and activation
        pass

def test():
    net = Net(in_channels=3, out_channels=16)
    x = torch.randn(1, 3, 32, 32)
    y = net(x)
    assert y.shape == (1, 16, 32, 32)
    print("Test passed!")

# test()
```
## 🔧 Step 2: Add a Fully Connected Layer

### Task

Extend your model by adding a fully connected layer that maps the flattened output

### Changes

After the Conv + ReLU step:

1. **Flatten** the output tensor.  
2. Add a `nn.Linear` layer:
  in_features = 16 × 32 × 32,
  out_features = 10
4. Compute the new total number of parameters (Conv layer + FC layer).
Show your full calculation.

