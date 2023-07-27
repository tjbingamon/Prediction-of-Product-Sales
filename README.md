# Prediction of Product Sales
Thomas Bingamon

Analyzing sales predictions through food items sold in different stores and to better understand what drives sales

![fb-image-sharing-dashboard_5b3c9b63294d3__700](https://user-images.githubusercontent.com/127987424/236351209-d94ea80c-ccef-42c7-a314-6ec158c2a021.jpg)


## Data Source

https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/

## Data Dicitionary

<img width="748" alt="Screenshot 2023-05-04 at 1 06 24 PM" src="https://user-images.githubusercontent.com/127987424/236341715-63525185-5509-4c69-9139-a73ce09732f8.png">

## Exploratory Data Analysis

Through our exploratory data analysis, a histogram and boxplot was created for each of our numeric dataype columns.

Below is a Histogram to view the distributions of various features in this dataset.

<img width="583" alt="Screenshot 2023-05-04 at 3 33 39 PM" src="https://user-images.githubusercontent.com/127987424/236343773-269960f6-9ff2-42be-bb70-4b22257c2b42.png">
This Histogram shows the distribution of Item MSRP by Outlet Size

## Explanatory Data Analysis
1. Does Item Visibility affect Item Outlet Sales?
   - Yes, according to our graph below we can see that it deeply affects sales

![download-1](https://user-images.githubusercontent.com/127987424/236347663-59873c48-8d8c-4f73-a2da-2b827e597217.png)



2. Is there a correlation between Outlet Sales vs Item Visability by Fat Content?
  - There is no correlation between item outlet sales and visibility by fat content

![download](https://user-images.githubusercontent.com/127987424/236344274-1ef9b523-b407-4d20-b6ae-6d256f7c2bd4.png)

## Key Insights
- Low Fat foods are selling more than Regular Fat foods.

## Machine Learning Using Models:
- Linear Regression Model
- Decision Tree Model

## Evaluations of Models and their Results:
- Linear Regression Model (Testing results):
   - Linear Regression Test  Scores
   - MAE: 804.2645 
   - MSE: 1,194,403.5311 
   - RMSE: 1,092.8877 
   - R2: 0.5671

- Decison Tree Model (Testing results):
   - MAE: 738.3556
   - MSE: 1,118,187.9463
   - RMSE: 1,057.4441
   - R2: 0.5947

## Evaluations and Recommendations
Model Best Recommended: Decision Tree
  - We have a lower error percentage on Decision Tree vs Linear Regression.
  - Decision Tree had the lowest MAE. This means our model was only off on it's predictions by 738.36.
  - The mean Item Outlet Sales was 2181.39. We can now understand we have an error percentage of 33.85%.

## Project Revisited
 #### Linear Regression Model: Interpret Our Coefficients
 
 - Intercept: Our model assumed a baseline 'Item Outlet Sales' of -137.99

 - Outlet_Type_Grocery Store:

  -- If the item sold belongs to this category, the Item_Outlet_Sales will be decreased by 1590.41.

- Outlet_Type_Supermarket Type 3:

  -- If the item sold belongs to this category, the Item Outlet Sales increases by 1500.88

- Outlet_Type_Supermarket Type 1:

  -- If the item sold belongs to this category, the Item Outlet Sales increases Item Outlet Sales by 275.17

## Linear Regression Top 3 Coeffiecients

![top3](https://github.com/tjbingamon/Prediction-of-Product-Sales/assets/127987424/4f0a49ca-82a7-4382-9fb5-983e23fe9aae)

### Linear Regression Evaluation:

- Training Data: R2= 0.56 RMSE= 1115.77
- Test Data: R2= 0.56 RMSE= 1164.92
- The mean Item Outlet Sales was 2181.39 and the mean absolute error was 859. which equals to an error percentage of 39.4 %.

### Random Forest Model:
- Feature Importance Plot

![top5 random forest](https://github.com/tjbingamon/Prediction-of-Product-Sales/assets/127987424/1e7e77fe-c782-4a2c-8899-5ea09a5fd3a1)

### SHAP Summary Plot 

![SHAP bar plot](https://github.com/tjbingamon/Prediction-of-Product-Sales/assets/127987424/6b82eb75-589a-4cf6-a85a-c76ad343e77a)

### Compare SHAP vs Random Forest Feature Importances
- The only difference is the order. Item_Visibility and Outlet_Type_Supermarket Type 3 are swapped in place.

### Summary plot - with plot_type='dot'

![SHAP Dot](https://github.com/tjbingamon/Prediction-of-Product-Sales/assets/127987424/87ff7ba8-2ac2-41dd-8e17-d22cccb33c41)

### Top 3 most important features and how they influence your model's predictions.

1) Item_MRP:
- Has the largest effect on the model's predictions as it was the first bar at the top of the plot.
- Since red dots are located on positive side, it means that the higher the Item_MRP, the more likely the model would predict that outlet sales are high

2) Outlet_Type_Grocery Store
- One-Hot-Encoded feature.
- Red dots are on the negative side, it is less likely that the model will predict high outlet sales if Outlet Type = Outlet_Type_Grocery Store.
- If Outlet_Type_Grocery Store == 1, the model is less likely to predict high outlet sales.
- If Outlet_Type_Grocery Store == 0, the model is more likely to predict high outlet sales.

3) Outlet_Type_Supermarket Type3
- One-Hot-Encoded feature.
- Red dots are on the positive side, meaning if the item is sold at Outlet_Type_Supermarket Type3, it is more likely that the model will predict the item to have high outlet sales.
- If Outlet_Type_Supermarket Type3 == 1, the model is more likely to predict high outlet sales.
- If Outlet_Type_Supermarket Type3 == 0, the model is less likely to predict high outlet sales.


# Individual Examples:

- I wanted to see the differences in a row that had the lowest value in their target column and a row that had the highest value in their target column.

# 1) Store that had the item with highest sales (within the 400 samples of SHAP) had Outlet_Type of Supermarket Type1

#### LIME Tabular Explanation:

<img width="931" alt="Screenshot 2023-07-26 at 4 58 37 PM" src="https://github.com/tjbingamon/Prediction-of-Product-Sales/assets/127987424/2b08f538-2bdd-4d7c-85bf-8e770ba0ab42">


### Interpretation: 

- Item from "Supermarket Type 1" group predicted a high of 6673.35 in outlet sales value.

- Item_MRP was greater than 180.25. It has a positive impact on our outlet sales.

- The facility is not an Outlet_Type_Grocery Store (Value == 0) gave it a positive impact on the outlet sales.

- The facility not being an Outlet_Type_Supermarket Type3 (Value == 0) gave it a negative impact on outlet sales.

#### Force Plot:

<img width="1004" alt="Screenshot 2023-07-26 at 4 59 22 PM" src="https://github.com/tjbingamon/Prediction-of-Product-Sales/assets/127987424/7977ff29-5e56-49c5-a7b2-97256e992747">

#### Interpret what features most heavily influenced the predictions, according to SHAP

- The base value = 2,155

- The SHAP value = 6,673.35

- Red features are greater than the blue, which means there is a "push" towards higher outlet sales, so the final prediction is high outlet sales.

- Features that influenced predictions the most (in order from most to least):

  - Item_MRP

  - Item_Weight

  - Item_Visibility

  - Outlet_Type_Grocery Store = 0

  - Outlet_Size_Missing= 1

# 2) Select a row with lowest target value (Item Outlet Sales)


#### LIME Tabular Explanation:

<img width="870" alt="Screenshot 2023-07-26 at 4 59 49 PM" src="https://github.com/tjbingamon/Prediction-of-Product-Sales/assets/127987424/612bd318-46b5-4d0d-8178-86f09e83c67c">

Interpretation:

- Item_MRP being <= 90.72 gave a negative impact on the outlet sales.

- Outlet_Type_Grocery Store (Value == 1) gave a negative impact on the outlet sales.

- Not being an Outlet_Type_Supermarket Type3 (Value == 0) gave a negative impact on the outlet sales.


#### Force Plot:

<img width="1002" alt="Screenshot 2023-07-26 at 5 01 29 PM" src="https://github.com/tjbingamon/Prediction-of-Product-Sales/assets/127987424/78141e13-25ed-4a79-8ebe-6d59ffe272cc">

### Interpretation:

- The base value is 2,155.

- The SHAP value is 64.12.

- The Blue feature is greater than Red, this means there is a "push" towards low outlet sales, so the final prediction would be low outlet sales.

- Features that influenced predictions the most (in order from most to least):

  - Item_MRP
  - Outlet_Type_Grocery Store = 1
