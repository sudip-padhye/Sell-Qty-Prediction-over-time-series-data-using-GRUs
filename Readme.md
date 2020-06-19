# Introduction
In this project, we will use hierarchical sales data from Walmart, the world’s largest company by revenue, to forecast daily sales for the next 28 days and to make uncertainty estimates for these forecasts. The data, covers stores in three US States (California, Texas, and Wisconsin) and includes item level, department, product categories, and store details. In addition, it has explanatory variables such as price, promotions, day of the week, and special events. Together, this robust dataset can be used to improve forecasting accuracy.

## Data
Data contains numerous categorical variables such as Event type, weekday etc. which are encoded using Label encoder and later scaled using Standard Scaler. To understand the seasonality and trend in the time-series data, I did EDA on it. 

<img src="comparison of each statewise stores.PNG" alt="drawing" width="400"/>

<img src="comparison of mean statewise stores.PNG" alt="drawing" width="400"/>

<img src="event days.PNG" alt="drawing" width="400"/>

<img src="rows per category.PNG" alt="drawing" width="400"/>

<img src="time series plot.PNG" alt="drawing" width="400"/>


## Methodology
The project uses Gated Recurrent Units (GRUs) to learn the trend present in the data and forecast futures sales of stock quantity. The input data is first transformed into Auto-correlation data and then fed to the model. The model uses 4 GRUs followed by a dense layer with a dropout of 0.3 at each layer in order to avoid overfitting. Moreover, the model uses Adam optimizer with a mean squared error metric for evaluation. The model was trained with 50 epochs with a batch-size of 32 rows. 

The project achieves mean squared error of 0.17 on the training data.
