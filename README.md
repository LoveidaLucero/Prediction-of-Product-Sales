# Prediction-of-Product-Sales
## Analyzing the relationshp between features and the target Sale Price. 

**Author: Loveida Lucero**

### Business Problem:
The goal is to predict the sales price for various products sold at various stores. 

### Data:
[Sale Prediction Data](https://drive.google.com/drive/u/0/folders/1Vi9HtxqFz0o0JEs6B-qcdZLCbP_g5Rxf)

## Methods
1. Data was first cleaned looking for inconsistencies, duplicates, impossible values and missing values.
2. The data is next explored through various graphs visually showing each feature alone as well a how it relates to the target feature of Sales Price.
3. Finally different types of models were created and tuned in order to most accurately predict the sale price with the smallest margin of errors.

## Results

The following heatmap shows the correlation of the numerical values: 

![Heatmap](https://github.com/LoveidaLucero/Prediction-of-Product-Sales/assets/141985693/798e0439-e855-4432-8919-cc50d1406e13)

- Out of the two strongest correlations, the Item_MRP/Item_Outlet_Sales looks to be the only that has a "cause" relationship.


The following map shows the ralationship of Item_Outlet_Sales and Outlet_Location_Types:

![Sales by Location Type](https://github.com/LoveidaLucero/Prediction-of-Product-Sales/assets/141985693/3245b3c8-5dcf-4bdd-b62c-9feee00a7b29)

- There seems to be no significant difference in sales regardless of location.

## Model
The final model chosen is the tuned Random Forest Model. 

**Scoring:**
- MAE (Mean Average Error)
  - 732.84
- MSE (Mean Squared Error)
  - 1107484.38
- RMSE (Root Mean Squared Error)
  - 1052.37
  - The model is still underfit because the data RSME shows a low performance on the RSME. The RSME calculaiton on the test data is greater by 100.1583 the train data (train_RSME 952.2125, test_RSME).
  - The RSME provides better insight as includes more insight to the outliers or errors for the data. The models RSME has an error calculation of $1052.37 and coupled with the low performance score on the R^2 the data provided and model is not a reliable predictor of the Sales.
- R^2 (Coefficient of Determination)
  -  0.60
  -  - The models testing data has 59.86% of the variance of target(Item_Outlet_Sales) explained by the remaining features.

 
