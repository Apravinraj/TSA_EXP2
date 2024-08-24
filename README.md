# Developed By: Pravin Raj A
# Reg No: 212222240079
# Date:

# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION

### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
Import necessary libraries (NumPy, Matplotlib)

Load the dataset

Calculate the linear trend values using least square method

Calculate the polynomial trend values using least square method

End the program

### PROGRAM:
```import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Load the CSV file
file_path = '/content/BTC-USD(1).csv'  # Replace with your file path
df = pd.read_csv(file_path)

# Convert the Date column to datetime format
df['Date'] = pd.to_datetime(df['Date'])

# Sort the data by Date just in case
df = df.sort_values('Date')

# Extract the dependent and independent variables
X = np.arange(len(df))  # Time index
Y = df['Close']  # Target variable (e.g., Close price)

# Linear Trend Estimation (1st degree polynomial)
linear_model = np.polyfit(X, Y, 1)
linear_trend = np.polyval(linear_model, X)

# Polynomial Trend Estimation (2nd degree polynomial)
poly_model = np.polyfit(X, Y, 2)
poly_trend = np.polyval(poly_model, X)

# Plotting the original data and the estimated trends
plt.figure(figsize=(12, 6))
plt.plot(df['Date'], Y, label='Original Data', color='blue')
plt.plot(df['Date'], linear_trend, label='Linear Trend', color='red')
plt.plot(df['Date'], poly_trend, label='Polynomial Trend (2nd degree)', color='green')
plt.title('Linear and Polynomial Trend Estimation')
plt.xlabel('Date')
plt.ylabel('Close Price (USD)')
plt.grid(True)
plt.legend()
plt.show()

# Print the model coefficients
print("Linear Model Coefficients (a, b):", linear_model)
print("Polynomial Model Coefficients (a, b, c):", poly_model)
```

### OUTPUT

![Screenshot 2024-08-24 221250](https://github.com/user-attachments/assets/c4780000-4c40-4f1c-a226-019132563216)


### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.
