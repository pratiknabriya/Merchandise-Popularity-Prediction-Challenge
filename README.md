# Merchandise Popularity Prediction Challenge

## Overview

Big Brands spend a significant amount on popularizing a product. Nevertheless, their efforts go in vain while establishing the merchandise in the hyperlocal market. Based on different geographical conditions same attributes can communicate a piece of much different information about the customer. Hence, insights this is a must for any brand owner. 

For this competition, the data is gathered from one of the top apparel brands in India. Provided the details concerning category, score, and presence in the store, the challenge is to predict the popularity level of the merchandise. The popularity class decides how popular the product is given the attributes which a store owner can control to make it happen.

### Dataset Description:

* Train.csv - 18208 rows x 12 columns (Includes popularity Column as Target variable)
* Test.csv - 12140 rows x 11 columns

Dataset can be downloaded from [here](https://www.machinehack.com/hackathons/merchandise_popularity_prediction_challenge/data).

### Attributes:

store_ratio, basket_ratio, category_1, store_score, category_2, store_presence, score_1, score_2, score_3, score_4, time and popularity - Class of popularity (Target Column)


### Evaluation metric: 

The submission will be evaluated using the Log Loss metric. One can use log_loss(y_true, y_pred) to calculate the same.

For more details, visit [hackathon webpage](https://www.machinehack.com/hackathons/merchandise_popularity_prediction_challenge/overview).

## My Approach

### Key points:

1. In **data pre-processing** stage it was found that there **no null values** present in train or test data. So no need of any imputation. The **duplicate values were removed** from the dataset.
2. **Exploratory data analysis** revealed that the class labels are seriously **imbalanced with class** '4' highy dominating. The feature set is a **mix of categorical and numerical variables**. The **Heatmap** of the predictor varibles revealed **no significant correlation** among them. So we don't discard any feature from dataset.
3. Then analyzed each of the feature one by one to find that there is a **high overlap among the class** label for each feature (univariate analysis). So, no single feature can do the classification job, but together they just might.
4. Then comes the **data prepration stage** for modelling. Did **one-hot encoding** upon categorical features and scaled the numerical features using **mean centring and scaling** (standardization).
5. In **Feature engineering stage**, I built several new features from the existing data - sum of scores, average of 3 scores, product of scores, store presence multiplied by store score, store presence multiplied by basket ratio, etc. like this managed to construct about **16 new features**.
6. Also for the categorical varibles, I used **probability based response encoding** (as for tree-based models, one-hot encoding doesn't give good results).
7. For building models, first I tested with some linear models like **Logistic Regression and SVM**, then I moved towards non-linear models like **tree-based ensembles**. Finally, I settled with **XGBoost**. Upon rigorous **hyperparameter tuning** using validation data, XGB gave the best results.

### Result:
Using XGBoost model, I managed to reduce **multi-class log loss** to **0.39868** on the test data.
