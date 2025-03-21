# Logistic regression model:

This part uses the binary classification model - logistic regression as the benchmark model. I first put the data of the training set into the logistic regression model and let the model automatically find the most suitable straight line. Next, I applied the trained model to the test data to observe the accuracy of the prediction, so as to obtain a benchmark accuracy. This provides a reference benchmark for the results obtained by the subsequent neural network.

# Single-layer neural network:

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
