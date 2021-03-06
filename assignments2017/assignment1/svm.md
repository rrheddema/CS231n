# Multiclass Support Vector Machine exercise

**svm_loss_naive and svm_loss_vectorized**

References to resolve this exercise:

* http://cs231n.github.io/optimization-1/
* https://en.wikipedia.org/wiki/Indicator_function
* https://stackoverflow.com/questions/36020583/compute-the-gradient-of-the-svm-loss-function
* https://mlxai.github.io/2017/01/06/vectorized-implementation-of-svm-loss-and-gradient-update.html


In the notes of cs231 the next loss function is mentioned (you can copy-paste in free-online-latex-equation-editor):
```
L_{i} =  \sum_{j \neq y_{i}}^{}    \begin{bmatrix} max(0,w_{j}{^T x_{i} - w_{y_{i}}^T x_{i} +  \Delta  \end{bmatrix}
```
Notice the difference in sign before w_{j} and w_{y_{i}}.
Closely look at formula and realize that you want:
```
\nabla_{W_{j}L_{i}=x_{i}(...)
```
and
```
\nabla_{W_{y_{i}}L_{i}=-x_{i}(...)
```

When the gradient is with respect of j, the summation over j does not make sense.
Then when in the notes of cs231 the derivates are made, the indicator function is being used too.

**Inline Question 1**

Differences are expected due to difference of the nature of the methods. Due to rounding errors a numeric approach will differ from an analytic approach.

### Stochastic Gradient Descent

**Tuning the hyperparameters**

* Adapt arrays for learning_rates and regularization_strengths manually
* Loop throught these arrays
* For debugging, using scatter:
    * plotted learning_rates against accurancy
    * plotted regularization_strengths against accurancy

```
learning_rates = [5e-9,1e-8, 2.5e-8, 5e-8]
regularization_strengths = [1.25e4, 2.5e4, 3.75e4 ,5e4, 6.25e4,7.5e4]
```
**Results**
```
...
lr 2.500000e-08 reg 1.250000e+04 train accuracy: 0.374918 val accuracy: 0.386000
...
best validation accuracy achieved during cross-validation: 0.386000
```

**Inline Question 2**
The visualized SVM weights look like mean images for the different classes,
which is the result of the training that will strengthen the weights for images
that have the correct class and weaken the weight wrt of incorrect classes.
