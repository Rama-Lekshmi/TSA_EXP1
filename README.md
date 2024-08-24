### NAME:  RAMA E.K. LEKSHMI
### REGISTER NUMBER: 212222240082
###  DATE: 
# Ex.No: 01A PLOT A TIME SERIES DATA


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
Thus we have created the python code for plotting the time series of given data.




