# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 16.03.2024


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the temperature data
# Replace 'temperature_data.csv' with the path to your data file
data = pd.read_csv('/content/AirPassengers.csv')

# Assuming your data contains two columns: 'Date' and 'Temperature'
# Ensure that the 'Date' column is in datetime format
data['Month'] = pd.to_datetime(data['Month'])

# Set the 'Date' column as the index
data.set_index('Month', inplace=True)

# Perform time series decomposition
period=13
result = seasonal_decompose(data,model='multiplicative', period=period)

# Plot the original time series
plt.figure(figsize=(12, 6))
plt.subplot(4, 1, 1)
plt.plot(data['#Passengers'], label='original')
plt.title('Original Time Series')
plt.legend()

# Plot the trend component
plt.subplot(4, 1, 2)
plt.plot(result.trend, label='Trend', color='yellow')
plt.title('Trend Component')
plt.legend()

# Plot the seasonal component
plt.subplot(4, 1, 3)
plt.plot(result.seasonal, label='Seasonal', color='green')
plt.title('Seasonal Component')
plt.legend()
```

















### OUTPUT:
![image](https://github.com/vikashsenthil21/TSA_EXP5/assets/119433834/b524c010-cf3b-4f92-87b8-b39449467117)




### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
