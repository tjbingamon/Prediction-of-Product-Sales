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




