# House Price Prediction using Linear Regression

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression


data = pd.read_csv("/content/data.csv")

df = pd.DataFrame(data)



model = LinearRegression()
model.fit(X, y)



area_to_predict = np.array([[1250]]) 
predicted_price = model.predict(area_to_predict)

print("Predicted House Price for 1250 sqft:", predicted_price[0], "Lakhs")


plt.scatter(X, y, color='blue', label='Actual Prices')
plt.plot(X, model.predict(X), color='red', label='Regression Line')
plt.xlabel("House Size (sqft)")
plt.ylabel("House Price (Lakhs)")
plt.title("House Price Prediction using linear regression")
plt.legend()
plt.show()
