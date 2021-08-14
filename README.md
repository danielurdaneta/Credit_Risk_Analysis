# Credit Risk Analysis

## Overview of the project

The purpose of this project was to find a machine learning model that can predict effectively high risk loans, we did this by creating 6 different models, we used a database of over 68000 rows with 'loan_status' as target variable and over 80 different variables like 'interes rate' and 'annual income' as features.

## Results

As the amount high risk loans are disproportionately smaller than the amount of lowe risk loans, all this models use different kind of resampling.

- Naive Random Oversampling

This is the first of 2 oversampling models we created, the classification report and balanced accuracy score is shown below:

![CR](https://user-images.githubusercontent.com/81272629/129459246-0160d5c6-085f-4ee2-9f5e-c4841ca79ac4.png)

As we can see, the precision of the  model to predict high risk loans is extremely low (0,01) which means there is a lot of false positive in the model, in the other hand we have a recall of 0.68  which means that 68% of the high risk loans were predicted, and we have a balance accuracy barely performing better than randomness of 54,7% which means that the model predicted correctly 54,7% of all loans.

- SMOTE Oversampling

The model we created using the SMOTE oversamplimg algorithm deliver these results:

![CR](https://user-images.githubusercontent.com/81272629/129459715-1358fb4d-390c-4b3d-b199-f9699b914b77.png)

We can see a precision in high risk loans equally poor than the previous model, we also see a recall that is slightly worse, predicting correctly 63% of the high risk loans, there is an improvement in the accuracy (66%) that is due an improvement in predicting correctly low risk loans. As it is more important to us to predict most of high risk loans, we can argue this model is worse than the previous.

- ClusterCentroids undersampling

We created this model using ClusterCentroids undersampling algotithm and got this results:

![CR](https://user-images.githubusercontent.com/81272629/129460238-5d30499a-0440-4f7b-b56c-b09ec6609aaa.png)


With this model we do not see any real improvements with results very similar to the Naive Random Oversampling model.


- SMOTEENN

This model is a combination of oversampling and undersapling algorithms, using this model we got the following results:

![CR](https://user-images.githubusercontent.com/81272629/129460248-5cc0d763-97e0-4c8c-b040-1151331818c7.png)

The SMOTEENN algorithm not seem to perform significantly better than the other models.

- Balanced Random Forest Classifier

This is the first of two Esemble Learners algorithms, and we got the following results:

![CR](https://user-images.githubusercontent.com/81272629/129460362-f1492c88-d482-4259-80a6-7512c1a88003.png)

We have a precision of high risk loans of 0.03, although it is low, it is an improvement comparing to the other models, we also find the highest recall so far (0.70) and the highest accuracy (0.79).

- Easy Ensemble AdaBoost Classifier

This model delivered the following results:

![CR](https://user-images.githubusercontent.com/81272629/129460468-2a9e2f16-914a-4b4d-a181-963fa837228f.png)

This is our best model by far, with an outstanding recall of 92% which means that of all the high risk loans, the model predicted correctly 92% of them, and an accuracy 93% which means that 93% of all predictions were correct.

## Summary

We found that the models using ensemble algorithms performed significantly better than the models using resampling algorithms. Of all 6 models we recommend to use the model that apply the Easy Ensemble AdaBooost Classifier algotithm, as we expect it will detect 93% of the high risk loans, and although the precision is still very low (0,09) we may argue that further investigation may discard all those false positives easily.
