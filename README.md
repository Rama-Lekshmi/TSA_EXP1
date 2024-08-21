# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```python
DEVELOPED BY : RAMA E.K. LEKSHMI
REGISTER NUMBER:212222240082
``` 

```python
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
from statsmodels.tsa.seasonal import seasonal_decompose
```
Load the dataset
```python
df = pd.read_csv('AirPassengers.csv', parse_dates=["Month"], index_col="Month")
```
Display the first few rows of the dataset
```python
print("Dataset Head:")
print(df.head())
```
Filter the data from 1949 to 1960 (entire range of the dataset)
```python
df_filtered = df["1949":"1960"]
```
# Resample the data annually and calculate the mean number of passengers
annual_mean = df_filtered.resample('Y').mean()

# Plot the annual mean number of passengers
plt.figure(figsize=(10, 6))
plt.plot(annual_mean, marker='o')
plt.xlabel("Year")
plt.ylabel("Number of Passengers")
plt.title("Average Annual Number of Passengers (1949-1960)")
plt.grid(True)
plt.show()

 Resample the data monthly and calculate the mean number of passengers
```python
monthly_mean = df_filtered.resample('M').mean()
```
 Plot the monthly mean number of passengers
```python
plt.figure(figsize=(10, 6))
plt.plot(monthly_mean, marker='o')
plt.xlabel("Month")
plt.ylabel("Number of Passengers")
plt.title("Average Monthly Number of Passengers (1949-1960)")
plt.grid(True)
plt.show()
```
 Calculate the 12-month moving average
```python
moving_avg_12 = df_filtered['#Passengers'].rolling(window=12).mean()

# Plot the original data with the 12-month moving average
plt.figure(figsize=(10, 6))
plt.plot(df_filtered['#Passengers'], label='Original Data', marker='o')
plt.plot(moving_avg_12, color='orange', label='12-Month Moving Average', linewidth=3)
plt.xlabel("Year")
plt.ylabel("Number of Passengers")
plt.title("Air Passengers with 12-Month Moving Average (1949-1960)")
plt.legend()
plt.grid(True)
plt.show()
```
Decompose the time series to observe trend, seasonality, and residuals
```python
decomposition = seasonal_decompose(df_filtered['#Passengers'], model='multiplicative')
trend = decomposition.trend
seasonal = decomposition.seasonal
residual = decomposition.resid

Plot the decomposed components
plt.figure(figsize=(10, 8))
plt.subplot(411)
plt.plot(df_filtered['#Passengers'], label='Original Data')
plt.legend(loc='upper left')
plt.subplot(412)
plt.plot(trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.subplot(413)
plt.plot(seasonal, label='Seasonality', color='green')
plt.legend(loc='upper left')
plt.subplot(414)
plt.plot(residual, label='Residuals', color='red')
plt.legend(loc='upper left')
plt.tight_layout()
plt.show()
```
Summary Statistics
```python
summary_stats = df_filtered.describe()
print("Summary Statistics:")
print(summary_stats)
```
Correlation Matrix

```python
correlation_matrix = df_filtered.corr()
print("Correlation Matrix:")
print(correlation_matrix)

```

# OUTPUT:
![2652045a-60df-49df-b334-6c845c2be0a8](https://github.com/user-attachments/assets/d6e30db0-8173-47fb-9997-c8908d488121)

![025a207e-c0cf-4898-a903-71d71361ccde](https://github.com/user-attachments/assets/2ff28788-5843-48f4-a516-95d616839c5e)

![fe14f095-de43-4ada-8c50-41dd17284041](https://github.com/user-attachments/assets/63da40bb-89ac-457c-8beb-3de27c168e0a)

![12f5667d-119e-40cb-8c9e-ac1a090b165a](https://github.com/user-attachments/assets/005c13a4-1046-4df4-aad6-2a80253242bd)




# RESULT:
Thus we have created the Python code for plotting the time series of given data.

