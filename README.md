# Task 1
## Logistic regression model:

This part uses the binary classification model - logistic regression as the benchmark model. I first put the data of the training set into the logistic regression model and let the model automatically find the most suitable straight line. Next, I applied the trained model to the test data to observe the accuracy of the prediction, so as to obtain a benchmark accuracy. This provides a reference benchmark for the results obtained by the subsequent neural network.

## Single-hidden-layer neural network:

Forward propagation and backpropagation are implemented. During the training process, I let the model continuously adjust the weights and biases to reduce the prediction error. From the training log, as the epoch increases, the loss (Loss) drops rapidly from 0.6127 to 0.0529, indicating that the model is gradually converging. At the same time, I used a dynamic learning rate (learning rate decay) so that the learning rate gradually decreases as the training progresses to improve the stability of the training. In the end, the accuracy of the neural network on the test set reached 99.05%, which is much higher than logistic regression, indicating that the neural network can learn data features more effectively and achieve higher classification performance.

| Epoch | Loss  | Learning Rate |
|-------|-------|--------------|
| 0     | 0.6127 | 0.050000 |
| 5     | 0.1205 | 0.049692 |
| 10    | 0.0855 | 0.048776 |
| 15    | 0.0756 | 0.047275 |
| 20    | 0.0660 | 0.045225 |
| 25    | 0.0653 | 0.042678 |
| 30    | 0.0588 | 0.039695 |
| 35    | 0.0634 | 0.036350 |
| 40    | 0.0561 | 0.032725 |
| 45    | 0.0560 | 0.028911 |
| 50    | 0.0552 | 0.025000 |
| 55    | 0.0545 | 0.021089 |
| 60    | 0.0546 | 0.017275 |
| 65    | 0.0544 | 0.013650 |
| 70    | 0.0539 | 0.010305 |
| 75    | 0.0534 | 0.007322 |
| 80    | 0.0533 | 0.004775 |
| 85    | 0.0532 | 0.002725 |
| 90    | 0.0530 | 0.001224 |
| 95    | 0.0529 | 0.000308 |

**Neural Network Accuracy: 0.9905**


## Explaining "Self-Learning" to my Boss

**Explanation:**

“In a neural network, ‘self-learning’ refers to the process of the model improving it's output on it's own based on it's past mistakes or experiences, just like human beings. 

Here’s how it works:

**Initial Guess:** The neural network starts by making an initial prediction (which could be wrong). This is based on the random weights assigned to it's inputs at the beginning.

**Error Calculation:** After that, the network compares it's perdiction with the correct answer (often referred to as label), and calculates the deviation, which is the error. 

**Learning from Mistakes (Backpropagation):** After calculating the error, the network goes through a process of back propagation which means figuring out the weights that might have cause the biggest deviation, and adjusting that accordingly to reduce error. This is learning from past mistakes.

**Iteration:** As the model repeats this process many times, it fine tunes it's parameters and weights, improving the accuracy of it's results over time. 

In summary, ‘self-learning’ is just the model figuring out how to adjust itself based on its errors so it can make better predictions in the future.”


# Task 2
## Transformer Model Overview

This notebook implements a **Transformer-based sequence reversal model**. The model takes a numerical sequence as input and predicts its reversed version. Below is an overview of the key components:

## Model components
- **Token Embedding:** Maps input tokens to a dense representation.
- **Positional Encoding:** Provides information about the position of tokens in the sequence to the model.
- **Multi-Head Self-Attention:** Enables the model to focus on different parts of the input sequence.
- **Feedforward Network (FFN):** Applies a two-layer neural network with a ReLU activation function.
- **fully connected linear layer** maps the encoder output to logits.
