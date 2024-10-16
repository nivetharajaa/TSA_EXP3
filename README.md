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
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.graphics.tsaplots import plot_acf
from statsmodels.tsa.stattools import acf
data = pd.read_csv('world_population.csv')
population = data['Population']
acf_values = acf(population, nlags=35)
plt.figure(figsize=(10, 5))
plot_acf(population, lags=35)
plt.title('Autocorrelation Function (ACF) for World Population')
plt.show()
print("ACF Values for the first 35 lags:\n", acf_values)

```
### OUTPUT:

![image](https://github.com/user-attachments/assets/80ad4442-6b60-4a1b-9252-873dd4b6b439)

### RESULT:
        Thus we have successfully implemented the auto correlation function in world population.
