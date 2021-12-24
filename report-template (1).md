# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Mansi Chilwant

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
When I tried to submit my first raw prediction, I discovered that if we don't set it to zero, Kaggle won't accept it. Both positive and negative values may be present in the prediction. There can't be any negative values in the predictions. So, before submitting my prediction, I always make sure that the negative values are set to 0.
### What was the top ranked model that performed?
WeightedEnsemble_L3 is one of the top ranked model that performed. 

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
The exploratory analysis found that how the added features like weather, season, holidays, humidity, etc had effect on tha bike sahring demand on daily , monthly, yearly basis. To add addional features like season or weather I used astype("category") function.

### How much better did your model preform after adding additional features and why do you think that is?
Adding features imporved my performance from 1.39759  to 0.45492.
## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Hyper parameter tuning did improve my autogluon model performance with score of 0.50932 . 
### If you were given more time with this dataset, where do you think you would spend more time?
Expoloring the predictions of other features , and improving the performance of various autogluon models suing hyperparameters. 
### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|   | model        | time | num_boost_round | num_epochs | hyperparameters    | hyperparameter_tune_kwargs | score    |
|---|--------------|------|-----------------|------------|--------------------|----------------------------|----------|
| 0 | initial      | 600  | default         | default    | default            | None                       | 1.397590 |
| 1 | add_features | 600  | default         | default    | default            | None                       | 0.454926 |
| 2 | hpo          | 900  | 100             | 5          | NN, CAT, GBM tuned | auto                       | 0.509320 |

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](https://github.com/LittleAlchemy/ML_bike_sharing/blob/main/model_train_score.png)


### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](https://github.com/LittleAlchemy/ML_bike_sharing/blob/main/model_test_score.png)

## Summary
The project provided a learning opportunity with the goal of applying atuogluon models to test-train and predict the Kaggle dataset. For the project's completion, the AWS sagemaker service is employed. The focus of the study was on feature engineering and modifying hyperparameters over time to improve the performance of the multiple autogluon models and make better predictions.