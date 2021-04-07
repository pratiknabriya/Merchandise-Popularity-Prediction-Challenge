# Merchandise Popularity Prediction Challenge

## Overview

Big Brands spend a significant amount on popularizing a product. Nevertheless, their efforts go in vain while establishing the merchandise in the hyperlocal market. Based on different geographical conditions same attributes can communicate a piece of much different information about the customer. Hence, insights this is a must for any brand owner. 

For this competition, the data is gathered from one of the top apparel brands in India. Provided the details concerning category, score, and presence in the store, the challenge is to predict the popularity level of the merchandise. The popularity class decides how popular the product is given the attributes which a store owner can control to make it happen.

### Dataset Description

* Train.csv - 18208 rows x 12 columns (Includes popularity Column as Target variable)
* Test.csv - 12140 rows x 11 columns

### Attributes

store_ratio, basket_ratio, category_1, store_score, category_2, store_presence, score_1, score_2, score_3, score_4, time and popularity - Class of popularity (Target Column)


### Evaluation metric 

The submission will be evaluated using the Log Loss metric. One can use log_loss(y_true, y_pred) to calculate the same.

## My Solution Summary

