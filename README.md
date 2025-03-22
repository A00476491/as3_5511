# Task 1

## Data Generation and Preprocessing Explanation

This dataset consists of *10,000 randomly generated samples, each with **10 features*. The features are constructed as follows:

- The *first 5 features* are randomly generated integers between 1 and 9.
- The *last 5 features* are either:
  - a *reversed version* of the first 5 features (labeled as 1), or  
  - a *randomly shuffled version* of the first 5 features (labeled as 0).

### Label Interpretation

- 1: The second half of the sequence is a reversed copy of the first half.
- 0: The second half of the sequence is a randomly shuffled version of the first half.

### Data Splitting

The dataset is split into:

- *80% training data*
- *20% testing data*

This is done using train_test_split from sklearn.model_selection with a fixed random seed for reproducibility (random_state=42).

### Summary

| Feature Range | Sequence Length | Label Meaning | Split Ratio |
|---------------|------------------|----------------|-------------|
| 1 to 9        | 10 (5 + 5)       | 1 = reversed, 0 = shuffled | 80% train / 20% test |

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


## Explaining "Self-Learning" to Your Boss
Here’s how you might explain the concept of “self-learning” in the context of backpropagation to someone unfamiliar with neural networks:

**Explanation:**

“In a neural network, the term ‘self-learning’ refers to the process of the model improving itself over time by learning from its mistakes. Here’s how it works:

**Initial Guess:** The neural network starts by making an initial prediction (which is often wrong). This is based on random weights assigned at the beginning.

**Error Calculation:** After making the prediction, the network compares the prediction to the actual answer (the label). It calculates how wrong the prediction was, and this difference is called the error.

**Learning from Mistakes (Backpropagation):** The network uses a method called backpropagation to adjust its weights. It essentially asks, ‘Which weights caused the biggest errors?’ and adjusts those weights to reduce the error in future predictions.

**Iteration:** The network repeats this process many times, gradually improving its predictions as it ‘learns’ from its past mistakes. The more data it sees, the better it becomes at making accurate predictions.

In summary, ‘self-learning’ is just the model figuring out how to adjust itself based on its errors so it can predict better in the future.”


# Task2
## Transformer Model Overview

This notebook implements a **Transformer-based sequence reversal model**. The model takes a numerical sequence as input and predicts its reversed version. Below is an overview of the key components:

## Model components
- **Token Embedding:** Maps input tokens to a dense representation.
- **Positional Encoding:** Provides information about the position of tokens in the sequence to the model.
- **Multi-Head Self-Attention:** Enables the model to focus on different parts of the input sequence.
- **Feedforward Network (FFN):** Applies a two-layer neural network with a ReLU activation function.
- **fully connected linear layer** maps the encoder output to logits.
