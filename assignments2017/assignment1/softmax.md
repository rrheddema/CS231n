# Softmax exercise

## Softmax Classifier

**Inline Question 1**
When we initialize the weights with small random values we expect the prediction for the 10 classes to be uniformly distributed, which means 10 times a value around 0.1. If we apply this to the Loss function we get -log(e^0.1/(10*e^0.1) = -log(1/10) = -log(0.1).
So we expect our loss to be close to -log(0.1)

**hyperparameter tuning**

```
learning_rates = [1e-8, 1e-7, 5e-7, 1e-6, 1e-5, 1e-4]
regularization_strengths = [0, 2.5e4, 5e2, 1e3, 1e4, 5e4]
```

With training with 150 iters, best 3 performing
```
lr 5.000000e-07 reg 1.000000e+03 train accuracy: 0.376714 val accuracy: 0.397000
lr 1.000000e-06 reg 0.000000e+00 train accuracy: 0.383469 val accuracy: 0.402000
lr 1.000000e-06 reg 1.000000e+03 train accuracy: 0.387939 val accuracy: 0.394000
```

With 1500 iters, results:
```
lr 1.000000e-07 reg 1.000000e+03 train accuracy: 0.398469 val accuracy: 0.405000
lr 1.000000e-06 reg 0.000000e+00 train accuracy: 0.417306 val accuracy: 0.412000
lr 1.000000e-06 reg 1.000000e+03 train accuracy: 0.403714 val accuracy: 0.410000
```
