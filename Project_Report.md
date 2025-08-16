# Boston House Price Prediction

## 1. Introduction
This project focuses on predicting housing prices in Boston using the **Boston Housing dataset**.  
The dataset includes information on housing characteristics (crime rate, number of rooms, pollution levels, etc.) and the target variable is the **median value of owner-occupied homes (PRICE)** expressed in $1000s.  

⚠️ **Ethical Note:** The Boston dataset contains a variable *“B”* that encodes race-related information. The dataset has been criticized for ethical issues. Here, it is used **strictly for educational purposes** in machine learning.

## 2. Objectives
- Understand the structure and statistics of the dataset  
- Explore correlations between features and target  
- Build a predictive model using **XGBoost Regressor**  
- Evaluate model performance using **R²** and **Mean Absolute Error (MAE)**  

## 3. Dataset Overview
- **Total rows:** 506  
- **Total columns:** 14 (13 features + 1 target variable `PRICE`)  
- **No missing values** in the dataset  

### Key Features:
- `CRIM`: Per capita crime rate by town  
- `ZN`: Proportion of residential land zoned for large lots  
- `INDUS`: Proportion of non-retail business acres  
- `CHAS`: Charles River dummy variable (1 if tract bounds river, 0 otherwise)  
- `NOX`: Nitric oxide concentration (pollution level)  
- `RM`: Average number of rooms per dwelling  
- `AGE`: Proportion of houses built before 1940  
- `DIS`: Distance to employment centers  
- `RAD`: Accessibility to highways  
- `TAX`: Property tax rate  
- `PTRATIO`: Pupil–teacher ratio  
- `B`: Race-related variable (**problematic**)  
- `LSTAT`: % lower status population  
- `PRICE`: Median house price (target variable)  

## 4. Data Analysis
- **Positive correlation:**  
  - `RM` (number of rooms) has a strong positive correlation with house price.  
- **Negative correlation:**  
  - `LSTAT` (% lower status) and `CRIM` (crime rate) strongly reduce house price.  

## 5. Model Development
- **Algorithm:** XGBoost Regressor  
- **Train–Test Split:** 80% training (404 samples), 20% testing (102 samples)  
- **Random state:** 2 (reproducibility)  

## 6. Results

### 🔹 Training Performance
- **R²:** 0.9999  
- **MAE:** 0.0091  

⚠️ Extremely high accuracy because the model is evaluated on **training data** (overfitting/memorization risk).  

### 🔹 Test Performance
- **R²:** 0.905  
- **MAE:** 2.07  

The model generalizes well: it explains ~90% of variance in unseen data.  
On average, predictions differ from actual prices by about **$2000**.  

## 7. Visualization
- Scatter plot of **Actual vs Predicted Prices** confirms most predictions align closely with true values.  
- Small deviation exists at **very high price points**.  

## 8. Conclusion
- The **XGBoost model** successfully predicts Boston housing prices with high accuracy.  
- **Strengths:** Handles non-linear relationships, robust performance.  
- **Limitations:** Dataset size is small (506 rows) and contains ethical concerns (`B` variable).  

### Future Work:
- Perform **cross-validation** for more reliable performance estimation.  
- Apply **hyperparameter tuning** in XGBoost to reduce MAE further.  
- Compare with alternative models (Random Forest, Linear Regression).  

## 9. Technologies Used
- Python  
- Pandas, NumPy, Matplotlib, Seaborn  
- Scikit-learn  
- XGBoost  

## Key Results Summary
- **R² (Test Data):** 0.905  
- **MAE (Test Data):** 2.07 (~$2000)  

The model explains most of the variability in house prices and provides **reasonably accurate predictions**.

✍️ **Author:** Nahidul Islam 
Master in Business Intelligence, Aarhus University
