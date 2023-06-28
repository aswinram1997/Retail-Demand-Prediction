# Retail-Demand-Prediction

![tara-clark-Gk8LG7dsHWA-unsplash](https://github.com/aswinram1997/Credit-Card-Approval-Prediction-Streamlit-App/assets/102771069/035eceab-ff4a-4a12-b6c4-db856dd9d69d)


## Project Overview
Accurate demand prediction is of utmost importance in the retail industry, as it enables retailers to optimize inventory, meet customer demands, and drive profitability. This project focuses on comparing the performance of two forecasting algorithms, namely Facebook's univariate Prophet algorithm and multivariate LSTM-based algorithm, specifically tailored for demand prediction using the [Walmart Dataset](<https://www.kaggle.com/datasets/yasserh/walmart-dataset>). By evaluating their accuracy and efficiency, the project aims to determine the superior algorithm for predicting aggregated weekly sales. The outcomes of this project have the potential to provide Walmart with a competitive edge in the dynamic retail market by enabling precise demand forecasting and informed decision-making for inventory management. The project's findings will also contribute to the broader understanding of which algorithm is better suited for the nature of the dataset at hand, promoting more accurate and tailored demand forecasting for the retail industry.

## Dataset Overview
The dataset used provides historical sales data from 2010-02-05 to 2012-11-01. It contains the following fields:

- Store: Represents the store number.
- Date: Indicates the week of sales.
- Weekly_Sales: Reflects the sales for the given store during the specific week.
- Holiday_Flag: Indicates whether the week is a special holiday week, with a value of 1 for holiday weeks and 0 for non-holiday weeks.
- Temperature: Represents the temperature on the day of sale.
- Fuel_Price: Indicates the cost of fuel in the region during that week.
- CPI: Refers to the prevailing consumer price index during the week.
- Unemployment: Reflects the prevailing unemployment rate during the week.

## Methodology
The project utilized two forecasting algorithms: univariate Prophet and multivariate LSTM. Each algorithm had its own distinct methodology for data preparation, data splitting, model fitting, model evaluation, and future prediction.

### Univariate Prophet:

- Data Preparation: Only the date and weekly sales fields were used as input features, excluding additional features like temperature, fuel price, CPI, unemployment, and holiday events to create the univariate model.
- Train-Test Split: The dataset was divided into a training set (80% of the data) and a testing set (the remaining 20%).
- Model Training and Evaluation: The Prophet model was fitted on the training set, automatically adjusting its parameters based on observed data patterns such as trends, seasonality, and holiday effects.
- Future Prediction: After model fitting, the Prophet model had the ability to predict future time points beyond the available data. This is accomplished by recursively predicting into the future, specifying the desired number of forecast periods.

### Multivariate LSTM:

- Data Preparation: The historical sales data, along with additional features such as temperature, fuel price, CPI, unemployment, and holiday events, were prepared as input for the multivariate LSTM model. These features aimed to capture the potential influence of macroeconomic factors on sales patterns.
- Train-Validation-Test Split: The dataset was divided into three subsets: a training set, a validation set, and a testing set. This division facilitated model exploration, hyperparameter tuning, and performance evaluation.
- Model Training and Evaluation: Various LSTM architectures and seq2seq models were explored, considering different network configurations, layer structures, activation functions, and hyperparameter settings. The goal was to find the best model that could accurately predict future sales.
- Future Prediction: The LSTM was trained to learn the patterns and relationships between the input sequence (multivariate historical sales data) and the output sequence (future sales). 


## Results
In comparison to the multivariate LSTM model, the Prophet model demonstrated superior performance in demand prediction using Walmart's dataset. The Prophet model, a univariate forecasting algorithm, exhibited exceptional performance surpassing the baseline moving average model in demand prediction for Walmart's dataset when compared with root mean squared error (RMSE) metric. It showcased a remarkable improvement of approximately 75% on the training set and an impressive 85% on the test set compared to the baseline model. This notable accuracy and superiority of the Prophet algorithm are particularly noteworthy given its univariate nature. Lastly, it should be noted that the presence of seasonality in the time series data and the relatively small dataset size further support the suitability and effectiveness of the Prophet model in accurately forecasting demand.

## Conclusion
These findings underscore the suitability of the univariate Prophet model for seasonal time series data and relatively small datasets. Despite the invested efforts in training the multivariate LSTM model, its performance remained suboptimal, likely due to the limited size of the dataset. Therefore, based on this evaluation, it can be concluded that the Prophet algorithm emerges as the superior choice for demand prediction in this specific context. However, it is important to note that further research and experimentation with larger datasets are warranted. This future work could provide valuable insights into the various factors influencing demand by leveraging the multivariate LSTM model. This approach can offer a deeper understanding of the nature of demand, surpassing the limitations of the univariate Prophet model.



