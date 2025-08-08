# Rainfall Prediction using Linear Regression

## 📌 Project Overview
This project predicts rainfall (precipitation) levels based on historical weather data from Austin, Texas.  
Using **Linear Regression** from `scikit-learn`, the model is trained on various weather parameters such as temperature, humidity, dew point, and wind speed to estimate daily precipitation.

The project also includes data cleaning, preprocessing, and visualization to better understand the relationships between weather attributes and rainfall.

---

## 📂 Dataset
**Source:** `austin_weather.csv`  
**Rows:** 1319  
**Columns:** 21 (after cleaning, 19 columns were used in modeling)  

Key features:
- **Temperature (High, Avg, Low)** in Fahrenheit
- **Dew Point**
- **Humidity**
- **Sea Level Pressure**
- **Visibility**
- **Wind Speed**
- **Precipitation (target variable)**

---

## ⚙️ Steps Implemented

1. **Data Cleaning**
   - Removed unnecessary columns (`Events`, `Date`, `SeaLevelPressureLowInches`)
   - Replaced non-numeric values (`T`, `-`) with `0.0`
   - Exported cleaned dataset as `austin_weather_final.csv`

2. **Feature Selection**
   - Input features: All columns except `PrecipitationSumInches`
   - Target variable: `PrecipitationSumInches`

3. **Model Training**
   - Algorithm: **Linear Regression**
   - Trained model to predict precipitation values

4. **Visualization**
   - Scatter plot for precipitation over time
   - Subplots for precipitation vs. key weather attributes

🛠 Challenges Faced
Data Cleaning

Handling T and - in precipitation and other numeric columns
Solution: Replaced them with 0.0 to ensure numerical consistency.

Feature Correlation

Some weather attributes were weakly correlated with rainfall, making predictions harder.
Solution: Selected the most relevant features for visualization and analysis.

Visualization

Large dataset made some scatter plots dense and harder to interpret.
Solution: Used subplots and focused on the most important variables.




💡 Possible Interview Questions & Answers


Q1: Why did you choose Linear Regression for this project?
A: Linear Regression is simple, interpretable, and effective for continuous numerical prediction when relationships between variables are approximately linear.

Q2: How did you handle missing or non-numeric data?
A: Replaced non-numeric indicators like T and - with 0.0 to ensure numeric compatibility.

Q3: Did you check for multicollinearity?
A: Not extensively in this version, but some weather features like TempHighF and TempLowF are highly correlated. Feature selection or PCA could be applied in future improvements.

Q4: What improvements would you suggest?
A:

Try advanced models like Random Forest or XGBoost

Normalize/scale features

Add feature importance analysis

Use time-series models like ARIMA or LSTM for better sequence learning

Q5: How would you deploy this model?
A: Package the trained model with Flask or FastAPI, serve it as a REST API, and integrate it into a weather dashboard.
