# Logistic Regression Mathematics


## 1. Overview

Logistic Regression is a binary classification algorithm.

Given input features:

$$
x \in R^d
$$

The goal is to predict:

$$
y \in \{0,1\}
$$


The model learns parameters:

$$
W,b
$$

where:

- $W$ is the weight vector
- $b$ is the bias term



# 2. Linear Model


The first step is computing a linear combination:

$$
z=W^Tx+b
$$


where:

$$
W^Tx=\sum_{i=1}^{d}w_i x_i
$$


For a batch of samples:

$$
Z=XW+b
$$


where:

- $X$ is the input matrix
- $W$ is the weight matrix
- $b$ is the bias vector



# 3. Sigmoid Function


The linear output $z$ is converted into a probability using the sigmoid function:


$$
\sigma(z)=\frac{1}{1+e^{-z}}
$$


Properties:

$$
0 < \sigma(z) < 1
$$


Therefore, the output can be interpreted as:


$$
P(y=1|x)=\sigma(z)
$$



# 4. Prediction


The predicted probability is:


$$
\hat{y}=\sigma(W^Tx+b)
$$


Expanded form:


$$
\hat{y}
=
\frac{1}{1+e^{-(W^Tx+b)}}
$$


The classification rule:


$$
\hat{y}
=
\begin{cases}
1, & \hat{y}\geq0.5\\
0, & \hat{y}<0.5
\end{cases}
$$



# 5. Binary Cross Entropy Loss


For binary classification, the loss function is:


$$
L(y,\hat{y})
=
-
[y\log(\hat{y})
+
(1-y)\log(1-\hat{y})]
$$


For $N$ samples:


$$
J(W,b)
=
-\frac{1}{N}
\sum_{i=1}^{N}
[
y_i\log(\hat{y_i})
+
(1-y_i)\log(1-\hat{y_i})
]
$$


The goal is minimizing:


$$
\min_{W,b} J(W,b)
$$



# 6. Gradient Derivation


For the linear output:


$$
z=W^Tx+b
$$


The derivative of the sigmoid function:


$$
\sigma'(z)
=
\sigma(z)(1-\sigma(z))
$$


The prediction error:


$$
\frac{\partial L}{\partial z}
=
\hat{y}-y
$$


Gradient of weights:


$$
\frac{\partial L}{\partial W}
=
x(\hat{y}-y)
$$


Gradient of bias:


$$
\frac{\partial L}{\partial b}
=
\hat{y}-y
$$



For a batch:


$$
\frac{\partial J}{\partial W}
=
\frac{1}{N}
X^T(\hat{Y}-Y)
$$


$$
\frac{\partial J}{\partial b}
=
\frac{1}{N}
\sum_{i=1}^{N}
(\hat{y_i}-y_i)
$$



# 7. Gradient Descent


Parameters are updated using gradient descent:


$$
W=W-\eta
\frac{\partial J}{\partial W}
$$


$$
b=b-\eta
\frac{\partial J}{\partial b}
$$


where:

- $\eta$ is the learning rate



# 8. Complete Forward Pass


The complete computation:


$$
x
\rightarrow
z=W^Tx+b
\rightarrow
\hat{y}=\sigma(z)
\rightarrow
L(y,\hat{y})
$$



# 9. Algorithm


1. Initialize parameters $W,b$

2. Compute linear output:

$$
z=W^Tx+b
$$


3. Apply sigmoid:

$$
\hat{y}=\sigma(z)
$$


4. Compute binary cross entropy loss:

$$
J(W,b)
$$


5. Compute gradients

6. Update parameters:

$$
W=W-\eta\nabla_W J
$$


7. Repeat until convergence



# 10. Relationship with Neural Networks


Logistic Regression can be viewed as a single neuron:


$$
z=W^Tx+b
$$


$$
output=\sigma(z)
$$


A neural network extends this idea by stacking multiple layers:

$$
x
\rightarrow
Layer_1
\rightarrow
Layer_2
\rightarrow
...
\rightarrow
Output
$$



# References

- Bishop, Pattern Recognition and Machine Learning
- Murphy, Machine Learning: A Probabilistic Perspective
- Deep Learning Book, Goodfellow et al.