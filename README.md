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
  * Hyper-parameter tuninh via [Weights & Biases](https://www.wandb.com/)
* Model tuning:   
Hyperparameters are tuned via [wandb](https://www.wandb.com/). Here is a [sample notebook](https://colab.research.google.com/drive/181GCGp36_75C2zm7WLxr9U2QjMXXoibt#scrollTo=aIhxl7glaJ5k) from wandb working with CNN.
