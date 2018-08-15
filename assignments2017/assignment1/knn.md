# k-Nearest Neighbor (kNN) exercise

**Inline Question #1**

Bright means high distances, so for the rows is means images in the test data that are not matching any in the training data. And for the columns, it means images in the training data that don't match any in the test data.

**predict labels**
```
# 1) sort the date related to the ith testing point:
#    limit it to k elements
indices=np.argsort(dists[i])[:k]
# 2) find labels, labels are numbers!
closest_y=self.y_train[indices]

# 3) count the lables occurrances first
counts = np.bincount(closest_y)
# 4) use argmax (find max and return index)
#    when multiple max values are found, first occurrance is returned
#    therefore the smallest label
y_pred[i]=np.argmax(counts)
```

**compute_distances_two_loops**

```
dists[i,j]=np.sqrt(np.sum(np.power(X[i]-self.X_train[j],2)))
```

**compute_distances_one_loop**

```
dists[i, :] = np.linalg.norm((self.X_train - X[i]), axis=-1)
```

**compute_distances_no_loops**

```
# HINT: 
# (a - b)^2 = (a - b) . (a - b ) = a.a - 2 a.b + b.b = a^2 + b^2 - 2 a.b
dists = np.sqrt(np.sum(X**2, axis=1).reshape(num_test, 1) + np.sum(self.X_train**2, axis=1) - 2 * X.dot(self.X_train.T))
```

**split in folds**
```
X_train_folds = np.array_split(X_train,num_folds)
y_train_folds = np.array_split(y_train,num_folds)
```


**k-fold cross validation**
```
for i in range(len(k_choices)):
    k_accuracies = []
    
    for j in range(num_folds):
        # train
        X_train_folds_sel=[x for l,x in enumerate(X_train_folds) if l!=j]
        y_train_folds_sel=[x for l,x in enumerate(y_train_folds) if l!=j]
        classifier.train(np.concatenate(X_train_folds_sel), np.concatenate(y_train_folds_sel))     
                                 
        # predict
        dists_two = classifier.compute_distances_no_loops(X_train_folds[j])
        y_test_pred = classifier.predict_labels(dists_two, k=k_choices[i])
        num_correct = np.sum(y_test_pred == y_train_folds[j])
        accuracy = float(num_correct) / num_test
        
        k_accuracies.append(accuracy)
     
    k_to_accuracies[k_choices[i]]=k_accuracies
```

**best k**
```
best_k = 10
```
