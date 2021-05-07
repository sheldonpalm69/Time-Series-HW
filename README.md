# Forecasting Yen Future Prices
![DollarYen]( yendollar.jpg)

#### UM FinTech BootCamp 2021

#### May 8th, 2021

---

## Prepared by:

- Sheldon Palm

---

## Time-Series Forecasting
Loading historical Dollar-Yen exchange rate futures data and apply time series analysis and modeling I will present my predictions using the confluence of these models. 
To reach my predictions I first:
* Decomposition using the Hodrick-Prescott Filter (Decompose the Settle price into trend and noise)


* Forecasting Returns using the ARMA Model.
* Forecasting the Settle Price using an ARIMA Model.
* Forecasting Volatility with GARCH.




The objective of this assigment is to apply these time series models, and be able to conclusively address the below questions:

### Questions and Answer

* Based on your time series analysis, would you buy the yen now?
* Is the risk of the yen expected to increase or decrease?
* Based on the model evaluation, would you feel confident in using these models for trading?

## Linear Regression
Will be by second observation to continue the main objective of this assignment. I will build a Scikit-Learn linear regression model to predict Yen futures ("settle") returns with lagged Yen futures returns and categorical calendar seasonal effects (e.g., day-of-week or week-of-year seasonal effects).
After this regression analysis I will complete the following:

* Data Preparation (Creating Returns and Lagged Returns and splitting the data into training and testing data)
* Fitting a Linear Regression Model.
* Making predictions using the testing data.
* Out-of-sample performance.
* In-sample performance.

With the results of the linear regression analysis and modeling I will be able to answer the following question:

Does this model perform better or worse on out-of-sample data compared to in-sample data?


### Datasets To Be Used

- https://miami.bootcampcontent.com/Miami-Boot-Camp/mia-virt-fin-pt-02-2021-u-c/-/blob/master/Homework/10-Time-Series/Instructions/Starter_Code/yen.csv

#### References

- https://www.investopedia.com/
