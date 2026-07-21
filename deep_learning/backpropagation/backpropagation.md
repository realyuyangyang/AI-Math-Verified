# Backpropagation

## 1. Neural Network Forward Propagation

For a simple neural network:

Input:

$$
x
$$

Weight:

$$
W
$$

Bias:

$$
b
$$


Linear transformation:

$$
z = Wx+b
$$


Activation function:

$$
a=f(z)
$$


Output:

$$
\hat{y}=a
$$


---

# 2. Loss Function

For binary classification, Binary Cross Entropy is commonly used:

$$
L
=
-\frac{1}{m}
\sum_{i=1}^{m}
\left(
y_i\log(\hat y_i)
+
(1-y_i)\log(1-\hat y_i)
\right)
$$


The goal is to minimize the loss:

$$
\min_W L
$$


---

# 3. Chain Rule

The core idea of backpropagation is the chain rule:

$$
\frac{\partial L}{\partial W}
=
\frac{\partial L}{\partial a}
\frac{\partial a}{\partial z}
\frac{\partial z}{\partial W}
$$


Backpropagation propagates errors from the output layer back to the input layer.

---

# 4. Single Neuron Backpropagation

Forward propagation:

$$
z=wx+b
$$


$$
a=f(z)
$$


Loss:

$$
L=\frac12(a-y)^2
$$


---

## Gradient of Output

First:

$$
\frac{\partial L}{\partial a}
=
a-y
$$


Derivative of activation function:

$$
\frac{\partial a}{\partial z}
=
f'(z)
$$


Therefore:

$$
\delta
=
\frac{\partial L}{\partial z}
=
(a-y)f'(z)
$$


---

## Weight Gradient


Since:

$$
z=wx+b
$$


we have:

$$
\frac{\partial z}{\partial w}=x
$$


Therefore:

$$
\boxed{
\frac{\partial L}{\partial w}
=
\delta x
}
$$


Bias gradient:

$$
\boxed{
\frac{\partial L}{\partial b}
=
\delta
}
$$


---

# 5. Multi-layer Neural Network

Consider a two-layer neural network.

Hidden layer:

$$
z_1=W_1x+b_1
$$


$$
h=f(z_1)
$$


Output layer:

$$
z_2=W_2h+b_2
$$


$$
\hat y=f(z_2)
$$


---

# 6. Output Layer Gradient


Output error:

$$
\delta_2
=
\frac{\partial L}{\partial z_2}
$$


Weight gradient:

$$
\frac{\partial L}{\partial W_2}
=
\delta_2 h^T
$$


Bias gradient:

$$
\frac{\partial L}{\partial b_2}
=
\delta_2
$$


---

# 7. Hidden Layer Gradient


Hidden layer error:

$$
\delta_1
=
(W_2^T\delta_2)
\odot
f'(z_1)
$$


where:

$$
\odot
$$

represents element-wise multiplication.


Hidden layer weight gradient:

$$
\frac{\partial L}{\partial W_1}
=
\delta_1 x^T
$$


Hidden layer bias gradient:

$$
\frac{\partial L}{\partial b_1}
=
\delta_1
$$


---

# 8. Gradient Descent Update


Parameters are updated using gradient descent:

$$
W=W-\eta\frac{\partial L}{\partial W}
$$


$$
b=b-\eta\frac{\partial L}{\partial b}
$$


where:

$$
\eta
$$

is the learning rate.

---

# 9. Backpropagation Algorithm

