# GCP-Fiscal-Forecating
Research project supported by IMF.

## Overview
* Target country: United States, France, Germany, Japan, United Kingdom, Italy, Canada
* Time period: 1950-2018, 69 years
* Target variable: `ngdp_rpch` for annual data, `ngdp_r_sa_pcha` and `ngdp_r_sa_pchy` (respectively) for quarterly data
  * `ngdp_rpch`: Gross domestic product, constant prices, National Currency, percent change (Percent, Units)
  * `ngdp_r_sa_pcha`: Gross domestic product, constant prices, seasonally adjusted, quarter-over-quarter percent change, annualized (Percent, Units)
  * `ngdp_r_sa_pchy`: Gross domestic product, constant prices, seasonally adjusted, year-over-year percent change (Percent, Units)
* Macro data: 11 Macro WEO variables; PMIs; consumer and business sentiment; stock market prices; energy prices; ICRG

## Methedology
* Benchmark: MA and EWMA based on historical GDP growth data
* Variable selection:
  * PCA: [lag 0](https://github.com/lingyixu/GCP-Fiscal-Forecating/blob/master/PCA_Macro_Factors.ipynb), [lag 1](https://github.com/lingyixu/GCP-Fiscal-Forecating/blob/master/PCA_Macro_Factors_lag1.ipynb), [lag 2](https://github.com/lingyixu/GCP-Fiscal-Forecating/blob/master/PCA_Macro_Factors_lag2.ipynb); [Loading Matrix](https://github.com/lingyixu/GCP-Fiscal-Forecating/blob/master/Macro_Factor_Loading_Matrix.png)
  * Random Forest
* NN modeling: LSTM
  * [Two-layer LSTM](https://github.com/lingyixu/GCP-Fiscal-Forecating/blob/master/LSTM_tuning.ipynb), [Multi-layer LSTM](https://github.com/lingyixu/GCP-Fiscal-Forecating/blob/master/Multilayer_LSTM_tuning.ipynb)
  * Hyper-parameter tuninh via [Weights & Biases](https://www.wandb.com/). Best model for two-layer and multi-layer LSTM, respectively:
  
  ![image](https://user-images.githubusercontent.com/35391238/77387192-1b928b00-6d63-11ea-9ddf-89e409dc8d48.png)
  ![image](https://user-images.githubusercontent.com/35391238/77387167-0289da00-6d63-11ea-9978-9b7b34e50bb0.png)
