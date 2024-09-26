### NAME:Nivetha A
### REG NO:212222230101
### DATE:

# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)


### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("tsla_2014_2023 (1).csv", nrows=35)
time_series = data['high'] 

n_data_points = len(time_series)
n_lags = min(35, n_data_points - 1)
acf_values = np.zeros(n_lags)

mean = np.mean(time_series)
variance = np.var(time_series)
normalized_data = time_series - mean

for lag in range(n_lags):
    lagged_data = np.roll(normalized_data, -lag)
    acf_values[lag] = np.sum(normalized_data[:n_data_points-lag] * lagged_data[:n_data_points-lag]) / (variance * (n_data_points - lag))

plt.figure(figsize=(10, 6))
plt.stem(range(n_lags), acf_values)
plt.title('ACF Plot for Tesla stock predication')
plt.xlabel('Lag')
plt.ylabel('ACF')
plt.show()
print("Mean = ",mean)
print("Variance = ",variance)
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/4e3bd322-d0e0-4b08-a0a0-659ec4564904)

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
