# Weather Forecasting with Ridge Regression

**Motive**  
Model next‑day maximum temperature using historical daily weather data, focusing on building a simple but structured machine‑learning pipeline for time‑series style regression. 

**Dataset**  
Daily weather observations loaded from `weather.csv`, indexed by date and including variables such as maximum temperature (`tmax`), minimum temperature (`tmin`), precipitation (`prcp`), and related station metadata. 

**What I did**  
- Cleaned and filtered the raw dataset by removing columns with high missingness, standardizing column names, forward‑filling gaps, and handling placeholder values. 
- Converted the index to a proper datetime format and created a supervised learning target by shifting `tmax` one day ahead to represent “tomorrow’s max temperature”. 
- Engineered rolling and seasonal features (rolling means over multiple horizons and expanding monthly/day‑of‑year averages) to capture short‑term trends and typical climate patterns. 
- Trained and repeatedly backtested a Ridge regression model on expanding windows of historical data, evaluating it with mean absolute error and mean squared error. 

**What I learned / Results**  
- The pipeline produces a cleaned, feature‑rich time‑series dataset suitable for regularized linear modeling. 
- Backtesting with MAE and MSE shows how well Ridge regression can approximate next‑day `tmax`, and error distributions over time highlight when the model struggles versus when it is accurate. 
