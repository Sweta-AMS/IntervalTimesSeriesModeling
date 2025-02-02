# *Project: Modeling Financial Interval Time Series*

## 📌 Project Overview
This project, "Modeling Financial Interval Time Series," was conducted as part of my MSc in Statistics at the University of Calcutta (2018–2020) under the supervision of Prof. A. Chattopadhyay, Prof. A. Sengupta, and Prof. R. Bhattacharya.

The study focuses on analyzing stock market volatility and forecasting price intervals using:

•	Vector Autoregressive (VAR) models

•	Generalized Autoregressive Conditional Heteroscedasticity (GARCH) models

The analysis was performed on intraday daily stock data of Tata Consultancy Services Ltd (TCS) spanning January 2015 to December 2019.

 
## 📊 Objective
•	Analyze dynamic relationships between stock market variables.

•	Model interval-valued stock price data using a VAR model.

•	Estimate and forecast stock market volatility using PCA and GARCH models.

•	Predict high and low price intervals for future stock movements.
 
## 📂 Dataset
•	Source: Yahoo Finance

•	Time Period: January 2015 – December 2019

•	Features Used: Open, High, Low, Close prices


## 🛠 Methodology

### 1️⃣ Time Series Analysis
✔️ Graphical visualization of TCS stock data

✔️ Stationarity check using Augmented Dickey-Fuller (ADF) test

✔️ Cross-correlation & Covariance analysis to assess dependencies

### 2️⃣ Model Fitting
✔️ Vector Autoregressive (VAR) Model for interval forecasting

✔️ Principal Component Analysis (PCA) to extract dominant stock patterns

✔️ GARCH(1,1) Model to estimate and forecast market volatility

### 3️⃣ Forecasting
✔️ VAR Model for price interval prediction

✔️ GARCH Model for volatility trend forecasting

✔️ Evaluation using Ljung-Box tests & ARCH-LM diagnostics
 
## 📈 Key Findings
•	The VAR(5) model effectively predicts high-low price intervals.

•	The GARCH(1,1) model successfully captures market volatility trends.

•	The combined models provide reliable interval forecasts for stock prices.

## 💻 Implementation

### 🔹 Install Required Packages
r software
```
CopyEdit
install.packages(c("MTS",
                   "forecast",
                   "vars",
                   "tseries", 
                   "rugarch",
                   "gridExtra",
                   "ggplot2"))
library(MTS)
library(forecast)
library(vars)
library(tseries)
library(rugarch)
library(gridExtra)
library(ggplot2)
```

### 🔹 Run Analysis
```
# Load and preprocess data
data <- read.csv("TCS_data.csv")
head(data)

# Fit VAR Model
fit <- VAR(data, p=5)
summary(fit)

# Fit GARCH Model
garchSpec <- ugarchspec(variance.model=list(model="sGARCH",
                        garchOrder=c(1,1)))
garchFit <- ugarchfit(spec=garchSpec,
                      data=data$Close)
summary(garchFit)
 ```

## 📌 Results & Forecasting

### 📊 Price Interval Forecasts:

•	VAR(5) model predicts high-low price ranges for the next 15 days

•	GARCH(1,1) model estimates future volatility levels

### 📈 Visualizations:
•	Time series plots for High-Low stock prices

•	PCA-based volatility analysis

•	GARCH forecast trends
 
## 🏆 Conclusion
•	VAR models effectively model interval-valued stock price movements.

•	GARCH models improve volatility estimation and risk assessment.

•	This approach provides a comprehensive framework for financial time series forecasting.
 
### 📜 Acknowledgments
Special thanks to Prof. A. Chattopadhyay, Prof. A. Sengupta, and Prof. R. Bhattacharya for their guidance.
 
### 🏗 Future Enhancements
🔹 Implement Deep Learning-based models (LSTMs, CNNs) for volatility forecasting

🔹 Explore Non-Gaussian models for better uncertainty quantification

🔹 Expand analysis to other financial assets

### 📧 Contact & Contributions

👤 Author: Sweta Rai

📩 Email: swetar63@gmail.com

Feel free to ⭐ the repo if you find this useful! 🚀




