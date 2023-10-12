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
The ultimate goal in any business is to have the highest increase in prices. The store 'OUT027' has a the argest increase in sales by $1,476.41. I would recomend auditing the store to gain some insight in improvements that can be apllied to the other stores as well. Supermarket_Type3/1 also have a significant higher increase than the Supermarket_Type2 and an audit should be performed to gain insights to improve the Supermarket_Type2.
