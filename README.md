# FBI_Time_Series_Data
This project focuses on transforming raw event-level data into a structured time series and applying forecasting techniques to predict future trends. The goal is to enable data-driven decision-making through statistical modeling.

---

## 🎯 Objective
- Convert raw data into time series format  
- Perform data cleaning and preprocessing  
- Analyze trends and patterns using visualization  
- Build a forecasting model (SARIMA)  
- Evaluate model performance  
- Generate business insights  

---

## 🧹 Data Preprocessing

Handled missing values using appropriate strategies:
- Dropped columns with excessive missing data (>40%)
- Filled categorical values with `"Unknown"`
- Filled time-related columns using median
- Converted `Date` column to datetime format  
- Sorted and indexed data by date  

---

## 🔄 Time Series Creation

Aggregated data into daily event counts:

```python
ts = df.resample('D').size()

Ensured continuous timeline using:

ts = ts.asfreq('D')

Handled missing dates using forward fill.
----
```
##  📊 EXPLORATORY DATA ANALYSIS (EDA)
```
**Key Visualizations:**

📈 Trend Plot → shows fluctuations over time
📊 Moving Average (MA7) → smooths noise
📅 Monthly Trend → highlights long-term patterns
📦 Boxplot → detects outliers
🔍 Decomposition → identifies trend & seasonality
---
**Key Insights:**

Data shows high variability
Presence of weekly seasonality
Outliers significantly impact trend visualization
----
##🤖 Model Used: SARIMA

The model captures:
-Trend
-Seasonality (weekly pattern)
----
Configuration:
SARIMAX(order=(1,1,1), seasonal_order=(1,1,1,7))
----
## 📉 Model Evaluation

Metric	Value	Interpretation
MAE	16.64	Average prediction error ≈ 16 events
RMSE	20.88	Penalizes larger errors
ADF p-value	0.077	Data is weakly non-stationary
----
##📈 Forecast Analysis

Model captures general trend well
Produces smooth forecasts
Limitations in Forecast:
Struggles with sudden spikes
Cannot fully capture extreme variations
----
## 💼 Business Insights

📌 Improved Data Quality → better model reliability

📊 Fluctuating Trends → variable demand/activity

🔁 Weekly Seasonality → predictable patterns

📉 Outlier Impact → affects forecasting accuracy

----

## 🚀 Business Impact

Resource Planning: Allocate resources based on expected demand
Peak Management: Prepare for high-activity periods
Decision Support: Enable data-driven strategies

----

##⚠️ Limitations
Cannot accurately predict extreme spikes
Forecast is smoother than real-world data
Limited feature engineering
----
##🔮 Future Improvements
Implement advanced models.

Add external features (weather, holidays, etc.)

Perform hyperparameter tuning for better accuracy

----
```
## ✅ Conclusion
```
This project demonstrates how raw data can be transformed into meaningful time series insights.

The SARIMA model provides reasonably accurate forecasts, capturing underlying patterns and enabling better planning. While improvements are possible, the current approach delivers practical and actionable insights.
