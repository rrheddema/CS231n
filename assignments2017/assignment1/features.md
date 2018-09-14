# Image features exercise

## Train SVM on features

with: num_color_bins = 30

```
lr 1.400000e-08 reg 5.000000e+05 train accuracy: 0.424571 val accuracy: 0.435000
best validation accuracy achieved during cross-validation: 0.435000
```

### Inline question 1:
The misclassification does not really make sense. With some imagination one could argue that the prediction of planes it is triggered by large empty area's or long shapes: resulting in misclassification of ships and e.g birds flying in a blue sky. This also holds for the ships. For the animals not really an pattern emerges. And the truck and car looks also to be "closer" to each other in feature space.

## Neural Network on image features

```
for hs: 6.600000e+02, lr: 5.000000e-01 and r: 1.000000e-04, valid accuracy is: 0.585000
for hs: 6.600000e+02, lr: 5.000000e-01 and r: 1.000000e-05, valid accuracy is: 0.586000
for hs: 6.600000e+02, lr: 1.000000e+00 and r: 1.000000e-05, valid accuracy is: 0.589000
```

And again
```
for hs: 6.600000e+02, lr: 5.000000e-01 and r: 1.000000e-05, valid accuracy is: 0.599000
for hs: 6.600000e+02, lr: 1.000000e+00 and r: 1.000000e-05, valid accuracy is: 0.598000
for hs: 6.900000e+02, lr: 5.000000e-01 and r: 1.000000e-06, valid accuracy is: 0.611000
```

Accurancy: 0.558
