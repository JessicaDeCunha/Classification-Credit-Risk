# Risky Business

## Background

Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online. Peer-to-peer lending services such as Loans Canada and Mogo let investors loan people money without using a bank. However, because investors always want to mitigate risk, it would be helpful to predict credit risk with machine learning techniques.

In this repo I have built and evaluated several machine learning models to predict credit risk using data you'd typically see from peer-to-peer lending services. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so you will need to employ different techniques for training and evaluating models with imbalanced classes. I have used the two following techniques to build and evaluate models using imbalanced-learn and Scikit-learn libraries:

1. [Resampling](#Resampling)
2. [Ensemble Learning](#Ensemble-Learning)

- - -

### Instructions

#### Resampling

Using the [imbalanced learn](https://imbalanced-learn.readthedocs.io) library, I resampled the LendingClub data to build and evaluate logistic regression classifiers using the resampled data.

Steps taken:

1. Oversample the data using the `Naive Random Oversampler` and `SMOTE` algorithms.

2. Undersample the data using the `Cluster Centroids` algorithm.

3. Over- and undersample using a combination `SMOTEENN` algorithm.


Further steps:

1. Train a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.

2. Calculate the `balanced accuracy score` from `sklearn.metrics`.

3. Calculate the `confusion matrix` from `sklearn.metrics`.

4. Print the `imbalanced classification report` from `imblearn.metrics`.

### Questions

* Which model had the best balanced accuracy score?
> The SMOTEEN model has the best balanced accuracy score because it is closest to 1.0
* Which model had the best recall score?
> Each model has a consistent total recall score of 0.99; a score above 0.50 is considered a good score.
* Which model had the best geometric mean score?
> The Naive Random Oversampling, SMOTE Oversampling, and the Combination (Over and Under) Sampling all produced the highest geometric mean score of 0.99

---

#### Ensemble Learning

In this section, you will train and compare two different ensemble classifiers to predict loan risk and evaluate each model. You will use the [Balanced Random Forest Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.BalancedRandomForestClassifier.html#imblearn-ensemble-balancedrandomforestclassifier) and the [Easy Ensemble Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.EasyEnsembleClassifier.html#imblearn-ensemble-easyensembleclassifier). Refer to the documentation for each of these to read about the models and see examples of the code.

Complete the following steps for each model:

1. Train the model using the quarterly data from LendingClub provided in the `Resource` folder.

2. Calculate the balanced accuracy score from `sklearn.metrics`.

3. Print the confusion matrix from `sklearn.metrics`.

4. Generate a classification report using the `imbalanced_classification_report` from imbalanced learn.

5. For the balanced random forest classifier only, print the feature importance sorted in descending order (most important feature to least important) along with the feature score.

### Questions

* Which model had the best balanced accuracy score?
> the Easy Ensemble Classifier has the best balanced accuracy score as it is closer to 1.0
* Which model had the best recall score?
> both models have a recall score of 0.99
* Which model had the best geometric mean score?
> both models have a geometric mean score of 0.99
* What are the top three features?
>the top three features are interest rate, borrower income, and debt to income

- - -

### Hints and Considerations

Use the quarterly data from the LendingClub data provided in the `Resources` folder. Keep the file in the zipped format and use the starter code to read the file.

Refer to the [imbalanced-learn](https://imbalanced-learn.readthedocs.io/en/stable/) and [scikit-learn](https://scikit-learn.org/stable/) official documentation for help with training the models. Remember that these models all use the model->fit->predict API.

For the ensemble learners, use 100 estimators for both models.
