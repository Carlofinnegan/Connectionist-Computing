# Connectionist Computing

By Carlo Finnegan

## Table of Contents
- [Weight Initialization](#initializing-weights)
- [Models](#models)
  - [XOR Problem](#model-1-xor-problem)
  - [Sine Function](#model-2-sine-function)
  - [Letter Recognition](#model-3-letter-recognition)
- [Model Results](#model-results)
- [Conclusion](#conclusion)

## Initializing Weights

Initial weight initialization was a critical concern for network performance. Key findings include:

- Simple random initialization between -0.1 and 0.1 sometimes led to slow convergence
- Larger weight ranges (-1 to 1) often resulted in faster convergence
- Xavier Weight Initialization proved most effective for general cases
- He initialization was necessary for ReLU activation layers

### Xavier Weight Initialization
The scale factor is given by:
```
Scale = sqrt(2 / (hiddenSize + outputSize))
```

### He Weight Initialization
For ReLU activation layers, the scale factor is:
```
Scale = sqrt(2 / inputSize)
```

## Models

### Model 1 (XOR Problem)
- Used sigmoid activation functions in both hidden and output layers
- Implemented mean absolute error loss
- Higher learning rates (0.3, 1.0) led to faster convergence
- Small learning rates struggled with convergence
- Achieved excellent binary classification results

### Model 2 (Sine Function)
- Implemented to predict sin(x1 - x2 + x3 - x4)
- Used tanh activation function for symmetrical properties
- Demonstrated superior performance with moderate learning rates (0.01)
- Higher learning rates (0.3) showed poorest performance
- Interesting pattern of error increase before reduction during training

### Model 3 (Letter Recognition)
- Processes 16-dimensional input vector for letter classification
- ReLU activation in hidden layer for feature selection
- 26 output neurons with softmax activation
- One-hot encoding for letter probability representation
- Achieved 94.08% accuracy in final testing

## Model Results

### XOR Function Results
| Input | Predicted Output |
|-------|-----------------|
| [0 0] | 0.0399 |
| [0 1] | 0.9646 |
| [1 0] | 0.9665 |
| [1 1] | 0.0275 |

### Sine Function Results
| Threshold | Accuracy |
|-----------|----------|
| Within 0.1 | 11.45% |
| Within 0.001 | 0.18% |
| Within 0.0001 | 0.02% |

### Letter Recognition Performance
- Achieved 94.08% classification accuracy
- Successfully separated multiple character classes
- Demonstrated good generalization capabilities

## Conclusion

The project revealed several key insights about neural network architecture:

1. Weight initialization significantly impacts model performance
2. Network size correlates with task complexity
3. Learning rates should be adapted based on problem complexity
4. Larger networks generally perform better but follow diminishing returns
5. Simple problems (like XOR) benefit from higher learning rates
6. Complex problems benefit from larger networks and smaller learning rates

The SINE model's poor test performance suggests potential overfitting issues, despite good training metrics. This highlights the importance of proper generalization strategies in neural network design.

---
For detailed methodology, results, and further discussion, please refer to the full paper.[full paper](.Connectionist_18379666/connectionist_computing.pdf).
