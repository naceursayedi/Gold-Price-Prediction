# 📈 Gold Price Prediction

This project focuses on forecasting the gold price using macroeconomic and market indicators. It includes data extraction, exploratory analysis, and time series modeling using ARIMAX, Prophet, and XGBoost.

---

## 🔧 Setup

1. **Clone the Repository**  
   Clone the main branch from GitLab:  
   👉 [GitLab Project Link](<https://gitlab.hs-anhalt.de/stnasaye/gold-team>)

2. **Create Virtual Environment and Install Dependencies**
   ```bash
   python -m venv venv
   source venv/bin/activate      # Windows: venv\Scripts\activate
   pip install -r requirements.txt

## 📊 Data
The project utilizes a comprehensive set of macroeconomic and financial data extracted from FRED (Federal Reserve Economic Data) and Yahoo Finance. For consistency, all monthly data has been linearly interpolated to daily frequency to align with the daily gold price.

The data_extraction notebook is responsible for fetching all these features, along with the gold price in USD, and storing them in a single gold_macro_combined.parquet file.

Here's a list of the features used, along with their frequencies:

- USD Index (DXY): Daily

- EUR/USD Exchange Rate (EURUSD): Daily

- S&P 500 Index (SP500): Daily

- Oil Price (Oil): Daily

- Bitcoin Price (Bitcoin): Daily

- VIX Index (VIX): Daily

- Consumer Price Index (CPI): Monthly

- Unemployment Rate (Unemp): Monthly

- Gross Domestic Product (GDP): Quarterly (interpolated to daily)

- Interest Rate (Interest): Monthly

- Federal Funds Rate (FEDFUNDS): Monthly

- Gold ETF Holdings: Daily

- M2 Money Supply (M2SL, MYAGM2EZM196N): Monthly

- Geopolitical Risk Index (GPR Index): Monthly

## 📂 Notebooks
data_extraction.ipynb: This notebook handles the extraction of all the aforementioned features and the gold price, saving the combined dataset as gold_macro_combined.parquet.

EDA.ipynb: This notebook contains the Exploratory Data Analysis (EDA) performed on the combined dataset to understand data distributions, correlations, and potential insights.

## 🤖 Models
We explored three different models for gold price prediction:

- ARIMAX (AutoRegressive Integrated Moving Average with eXogenous regressors)

- Prophet (Facebook Prophet)

- XGBoost (eXtreme Gradient Boosting)

## 📌 Tools & Techniques
- MLflow for experiment tracking

- Optuna for hyperparameter tuning

- GitLab and Git for version control

## 🧠 Insights & Challenges

Challenge: Future exogenous data is unknown, making forecasting with them less practical for real-time use