# Forecasting Yen Future Prices
![DollarYen](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/yendollar.jpg)

#### UM FinTech BootCamp 2021

#### May 8th, 2021

---

## Prepared by:

- Sheldon Palm

---

## Time Series Forecasting
Loading historical Dollar-Yen exchange rate futures data and apply time series analysis and modeling I will present my predictions using the confluence of these models. 
To reach my predictions I first:
* # Decomposition using the Hodrick-Prescott Filter (Decompose the Settle price into trend and noise)
![HP Decomposition](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/HPDecomposition.png)
Plotting the Settle Prices versus the Trend
![Settle vs_Trend](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/Settle_vs%20_Trend.png)

* # Forecasting Returns using the ARMA Model.
![ARMA](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/ARMA.png)
ARMA Model shows AIC of 15798.142 and an p-Value of .421
![ARMA Results](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/ARMAResults.png)

* # Forecasting the Settle Price using an ARIMA Model.
![ARIMA](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/ARIMA.png)
ARIMA model shows AIC of 83905.238 and a p-Value of .652
![ARIMA Results](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/ARIMAResults.png)

* # Forecasting Volatility with GARCH.
![GARCH Results](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/GARCH.png)
GARCH result shows a p-Value of 3.708e-02 
![GARCH Results](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/GARCHResults.png)



**The objective of this assignment is to apply these time series models, and be able to conclusively address the below questions:**

### Questions and Answer

* Based on your time series analysis, would you buy the yen now?
* Is the risk of the yen expected to increase or decrease?
* Based on the model evaluation, would you feel confident in using these models for trading?

**The results of the time series analysis weigh in with an ARMA p-Value of .421, which is higher than the recommended .05. The ARIMA p-Value is .652 also higher than the recommended .05 value. The coefficient for the autoregressive term is not statistically significant and those terms should not be kept in the models. After forecasting the Volatility using the GARCH model, it is conclusive that even though there is an upward-trend in the next 5 days forecast, the EWMA (D) from 2015 to 2019 reflects a lower price expectation for the Yen. The confluence in the EWMA and the p-Values concludes a decision not to buy the Yen at this moment. The ARMA and the ARIMA AIC and BIC were different because we use "Settle" prices versus "Returns", when both models were set for comparison using "Returns" they perform almost identical. It is also conclusive that these models will not give an exceptionally good indication of the future returns of the Yen. 
![EWMA 2015 - 2019](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/EWMA%20.png)
Higher Volatility means a great chance of higher risk. The GARCH plot, expect increased short-term volatility in the markets, using this approach a short-term investor may buy the Yen now and exit before the price return to the mean of the EWMA.**

## Linear Regression
Will be by second observation to continue the main objective of this assignment. I will build a Scikit-Learn linear regression model to predict Yen futures ("settle") returns with lagged Yen futures returns and categorical calendar seasonal effects (e.g., day-of-week or week-of-year seasonal effects).
After this regression analysis I will complete the following:

* Data Preparation (Creating Returns and Lagged Returns and splitting the data into training and testing data)
![DF Returns and Lagged Returns](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/DF_Lagged.png)
* Fitting a Linear Regression Model.
![Linear Regression Model Load](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/LR_Model.png)
* Making predictions using the testing data.
![Predictions using Data](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/F20_Returns.png)

* Out-of-sample performance.
![Out of Sample Result](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/Out_RMSE.png)

* In-sample performance.
![In Sample Result](https://raw.githubusercontent.com/sheldonpalm69/Time-Series-HW/main/images/In_RMSE.png)

With the results of the linear regression analysis and modeling I will be able to answer the following question:

Does this model perform better or worse on out-of-sample data compared to in-sample data?

**The OUT of Sample RMSE (.415) is lower than the IN Sample RMSE (.596). The IN Sample RMSE is typically lower for training data but is higher in this case. This means the model gave better predictions for data it has never seen before the "test set" than on the actual "training set". Therefore, I would not trust these predictions, and would instead develop a new model.**

### Datasets to Be Used

[Yen.csv](https://github.com/sheldonpalm69/Time-Series-HW/blob/main/yen.csv)

#### References

- https://www.investopedia.com/