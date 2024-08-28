### NAME:  RAMA E.K. LEKSHMI
### REGISTER NUMBER: 212222240082
###  DATE: 
# Ex.No: 01A PLOT A TIME SERIES DATA


# AIM:
To Develop a python program to Plot a time series data (Air Passenger Data)
# ALGORITHM:

1. Import Libraries: Import necessary libraries such as pandas, matplotlib.pyplot, and numpy.

2. Load Data: Read the air passenger data into a pandas DataFrame from a CSV file or other sources.

3. Preprocess Data: Convert the date column to datetime format and set it as the DataFrame index.

4. Plot Data: Use plt.plot() to plot the time series data, showing the number of passengers over time.

5. Customize Plot: Add labels, a title, and gridlines using plt.xlabel(), plt.ylabel(), plt.title(), and plt.grid().

6. Show Plot: Display the plot using plt.show().

# PROGRAM:
```python
DEVELOPED BY: RAMA E.K. LEKSHMI
REGISTER NUMBER: 212222240082
```
```python
import matplotlib.pyplot as plt
import pandas as pd
```
Load the dataset
```python
df = pd.read_csv('AirPassengers.csv', parse_dates=["Month"], index_col="Month")
```
Display the first few rows of the dataset
```python
df.head()
```
Filter the data from 1949 to 1960 (entire range of the dataset)
```python
df_filtered = df["1949":"1960"]
```
Resample the data annually and calculate the mean number of passengers
```python
annual_mean = df_filtered.resample('Y').mean()
```
Plot the annual mean number of passengers
```python
annual_mean.plot(kind='line')
plt.xlabel("Year")
plt.ylabel("Number of Passengers")
plt.title("Average Annual Number of Passengers (1949-1960)")
plt.show()
```
Resample the data monthly and calculate the mean number of passengers
```python
monthly_mean = df_filtered.resample('M').mean()
```
Plot the monthly mean number of passengers
```python
monthly_mean.plot(kind='line')
plt.xlabel("Month")
plt.ylabel("Number of Passengers")
plt.title("Average Monthly Number of Passengers (1949-1960)")
plt.show()

```
# OUTPUT:

![image](https://github.com/user-attachments/assets/2139ff4f-1f1a-4d37-a2f5-4c35a71b013a)

![image](https://github.com/user-attachments/assets/9422da8e-b82a-49a7-a3b3-3746d0d12e37)


# RESULT:
Thus  a time series plot of the air passenger data is successfully generated , visualizing monthly passenger counts over time with appropriate labels, title, and gridlines.




