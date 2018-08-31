# Multiclass Support Vector Machine exercise

**svm_loss_naive and svm_loss_vectorized**

References to resolve this exercise:

* http://cs231n.github.io/optimization-1/
* https://en.wikipedia.org/wiki/Indicator_function
* https://stackoverflow.com/questions/36020583/compute-the-gradient-of-the-svm-loss-function
* https://mlxai.github.io/2017/01/06/vectorized-implementation-of-svm-loss-and-gradient-update.html


In the notes of cs231 the next loss function is mentioned:

![equation](http://www.sciweavers.org/tex2img.php?eq=L_%7Bi%7D%20%3D%20%20%5Csum_%7Bj%20%5Cneq%20y_%7Bi%7D%7D%5E%7B%7D%0A&bc=White&fc=Black&im=png&fs=12&ff=arev&edit=0)

Notice the difference in sign before w_{j} and w_{y_{i}}.

Closely look at formula and realize that you want:

![equation](http://www.sciweavers.org/tex2img.php?eq=%5Cnabla_%7BW_%7By_%7Bi%7D%7D%7DL_%7Bi%7D%20%3D%20-x_%7Bi%7D%20%28...%29%0A&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)

and

![equation](http://www.sciweavers.org/tex2img.php?eq=%5Cnabla_%7BW_%7Bj%7D%7DL_%7Bi%7D%20%3D%20x_%7Bi%7D%20%28...%29%0A&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)

When the gradient is with respect of j the summation over j does not make sense.

Then when in the notes of cs231 the derivates are made, the indicator function is being used too.

** Inline Question 1 **
Differences are expected due to difference of the nature of the methods. Due to rounding errors a numeric approach will differ from an analytic approach.

### Stochastic Gradient Descent

**tuning the hyperparameters**

* Adapt arrays for learning_rates and regularization_strengths manually
* Loop throught these arrays
* For debugging, using scatter:
    * plotted learning_rates against accurancy
    * plotted regularization_strengths against accurancy

```
learning_rates = [5e-9,1e-8, 2.5e-8, 5e-8]
regularization_strengths = [1.25e4, 2.5e4, 3.75e4 ,5e4, 6.25e4,7.5e4]
```
Results:
```
...
lr 2.500000e-08 reg 1.250000e+04 train accuracy: 0.374918 val accuracy: 0.386000
...
best validation accuracy achieved during cross-validation: 0.386000
```

** Inline Question 2 **
The visualized SVM weights look like mean images for the different classes,
which is the result of the training that will strengthen the weights for images
that have the correct class and weaken the weight wrt of incorrect classes.
