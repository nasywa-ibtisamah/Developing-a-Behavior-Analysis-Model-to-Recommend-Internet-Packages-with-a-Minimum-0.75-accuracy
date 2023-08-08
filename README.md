# Project Description

Hello there :wave:
I hope this project finds you well!

In this project, I will train a model that can analyze consumer behavior and recommend one of the two new packages: Smart or Ultra. For this project, the threshold for the accuracy level is 0.75. I evaluated the accuracy metric of my model using the test dataset.

**Objective**
To train a model that can recommend a package based on consumer behavior with a minimum accuracy score of 0.75.

**Used Model**
1. Logistic Regression
2. Decision Tree
3. Random Forest

# Steps

1. Data Overview
2. Splitting the Data
3. Assessing Model Quality
4. Hyperparameter Tuning
5. Sanity Check

## 1. Data Overview

**Data Description** 

The dataset contains the following columns:
- `calls` - number of calls
- `minutes` - total call duration in minutes
- `messages` - number of text messages
- `mb_used` - internet usage traffic in MB
- `is_ultimate` - package for the current month (Ultimate - 1, Surf - 0)


## 2. Splitting the Data

The data will be splitted into:
1. Training Set: This data is used to train and build the model.
2. Validation Set: This data is used to optimize the model during its construction. It helps assess the model's ability to recognize patterns in a general sense. The validation set is also used to evaluate the accuracy of the created model. If the accuracy is not satisfactory, hyperparameter tuning can be performed.

3. Test Set: This data is used to test the model's performance.


## 3. Assessing Model Quality

1. Based on the training dataset, overfitting is observed. This is indicated by the accuracy value of 1.0 when using the decision tree and random forest models. This could be due to the small amount of data and the presence of imbalance.

2. Based on the accuracy of the validation dataset,

- Logistic regression has the lowest accuracy rate and has not reached the threshold with an accuracy of 75% on the test dataset.

- Decision Tree has a moderate accuracy rate and has not reached the threshold with an accuracy of 75% on the test dataset.

- Random Forest has the highest accuracy rate and has already reached the 75% threshold on the test dataset.

## 4. Hyperparameter Tuning

### Logistic Regression

**the hyperparameters that were tuned:**
- solver
- random_state

**The breakdown of accuracy results before and after hyperparameter tuning is as follows:**

1. Training dataset --> Before: 74.8%, After: 74.5%. Decreased by 0.3%.

2. Validation dataset --> Before: 76.8%, After: 76.2%. Decreased by 0.6%.

3. Test dataset has an accuracy of 74.5%, which hasn't yet exceeded the threshold.

### Decision Tree

**the hyperparameters that were tuned:**
- max_depth
- random_state

**The breakdown of accuracy results before and after hyperparameter tuning is as follows:**

1. Training dataset -> Before: 1, After: 83.1% > No longer experiencing overfitting.
2. Validation dataset > Before: 75.2%, After: 82.1%. Increased by 6.9%.
3. Test dataset has an accuracy of 77.7%, which meets the threshold for accuracy.

### Random Forest

**the hyperparameters that were tuned:**
- max_depth
- random_state
- n_estimators

**The breakdown of accuracy results before and after hyperparameter tuning is as follows:**

1. Training dataset > Before: 1, After: 88.4%. No longer experiencing overfitting.
2. Validation dataset > Before: 80%, After: 84%. Increased by 4%.
3. Test dataset has an accuracy of 80.5%, exceeding the threshold.

## 5. Sanity Check

Based on the above sanity check, the model is dominated by 0. Therefore, the results are not satisfactory.

# General Conclusion

Among the three models, the highest accuracy on the test set is achieved by the Random Forest model. The difference between the training set, validation set, and test set accuracy is also not substantial, indicating that overfitting is not a concern.

Therefore, I would recommend the client to use the **Random Forest model** to determine the appropriate package choice between "Smart" and "Ultra".
