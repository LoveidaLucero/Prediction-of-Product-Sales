# Prediction-of-Product-Sales

**Author: Loveida Lucero**

### Business Problem:
The store chain is looking to increase revenue and determine which steps can be taken to improve the sales in individual products and locations. . 

### Data:
[Sale Prediction Data](https://drive.google.com/drive/u/0/folders/1Vi9HtxqFz0o0JEs6B-qcdZLCbP_g5Rxf)

## Methods
1. Data was first cleaned by looking for inconsistencies, duplicates, impossible values and missing values.
2. The data is next explored through various visuals showing each feature alone as well a how it relates to the target feature of Sales Price.
3. Finally different types of models were created and tuned in order to most accurately predict the sale price with the smallest margin of errors.

## Results

The following heatmap shows the correlation of the numerical values: 

![Heatmap](https://github.com/LoveidaLucero/Prediction-of-Product-Sales/assets/141985693/798e0439-e855-4432-8919-cc50d1406e13)

- Out of the two strongest correlations, the Item_MRP looks to be the only that has a causal relationship. This makes sense givien that vairous products have various value.


The following map shows the ralationship of Item_Outlet_Sales and Outlet_Location_Types:

![Sales by Location Type](https://github.com/LoveidaLucero/Prediction-of-Product-Sales/assets/141985693/3245b3c8-5dcf-4bdd-b62c-9feee00a7b29)

- There seems to be no significant difference in sales regardless of location. This could be a factor to consider if the locations are in similar neighborhoods. If this is the case it could be wourth adding locations or relocating to higher income areas where disposable income is more plentiful and either higher volumes or more more frequent purchases could be made. 

## Prediction Model
After running multiple models, the final model chosen is the tuned Random Forest Model since it produced the smallest margins of error. However, even with this model outperforming the others, the model still had a poor performance with only 59.86% of the various being explained by the remaining features. It would benefit the project to gather more relevant feature information to more accurately predict the outcome.  

**Scoring:**
- MAE (Mean Average Error)
  - The margin of error in the predicted amount was averaged out to an error of $732.84.
- MSE (Mean Squared Error)
  - The average of each margin of error squared is $1107484.38.
- RMSE (Root Mean Squared Error)
  - The root of the MSE is $1052.37. As this is larger than just the average error this points to outliers in the margins or errors 
  - The model is still underfit because the data RSME shows a low performance on the RSME. The RSME calculaiton on the test data is greater by 100.1583 the train data (train_RSME 952.2125, test_RSME).
  - The RSME provides better insight as includes more insight to the outliers or errors for the data. The models RSME has an error calculation of $1052.37 and coupled with the low performance score on the R^2 the data provided and model is not a reliable predictor of the sales price.
- R^2 (Coefficient of Determination)
  -  The models testing data has 59.86% of the variance of target(Item_Outlet_Sales) explained by the remaining features. This leads adds to the recommendation that more target related feature data should be gathered to have a more concrete and reliable pridection.
   
## Model Insights

**Linear Regression Coefficients**

![image](https://github.com/LoveidaLucero/Prediction-of-Product-Sales/assets/141985693/01142792-4261-4094-80dd-18b469c15c32)

- Top 3 Coefficients:
  - **Outlet_Identifer_OUT027**:
    - If the Outlet_Identifier is OUT027, the sales will increase by $1,476.41.
  - **Outlet_Type_Supermarket Type3**:
    - If the Outlet Type is a Supermarket Type3, the sales will increase by $1,476.41.
  - **Outlet_Type_Supermarket Type1**:
      - If the Outlet_Type id Supermarket Type1, the sales will increase by $1,260.40


 **Random Forest Regression (final chosen model) Feature Importance**

![image](https://github.com/LoveidaLucero/Prediction-of-Product-Sales/assets/141985693/864636ae-5bdb-4b21-9801-0ced324fcf59)

- Top 5 most important features in predicting the model:
  - Item_MRP
  - Item_Visibility
  - Outlet_Type_Supermarket Type1
  - Item_Weight
  - Outlet_Type_Supermarket Type3
 
# Recomendations
Currently the store 'OUT027' has a the largest increase in sales by $1,476.41. I would recomend auditing the store to gain some insight into the things done differently there that can be applied to the other stores as well. Supermarket_Type3/1 also have a significant higher increase than the Supermarket_Type2 and an audit should be performed to gain insights to improve the Supermarket_Type2.
