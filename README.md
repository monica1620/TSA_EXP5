# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 20-11-2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### Dataset Used: Housing dataset 

### Software Used: Jupyter Notebook

### PROGRAM:
```

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('Bengaluru_House_Data.csv')

data['price'] = pd.to_numeric(data['price'], errors='coerce')
data = data.dropna(subset=['price'])

price_data = data['price'].reset_index(drop=True)

decomposition = seasonal_decompose(price_data, model='additive', period=12)

plt.figure(figsize=(10, 12))

plt.subplot(411)
plt.plot(price_data, label='House Prices')
plt.legend(loc='upper left')
plt.title('Original Housing Data')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend Plot')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')

plt.tight_layout()
plt.show()
```

















### OUTPUT:
Original Dataset 


<img width="532" height="151" alt="image" src="https://github.com/user-attachments/assets/9dfb0c93-1476-41d3-adb4-8bbe79795a1f" />

Trend Plot


<img width="528" height="154" alt="image" src="https://github.com/user-attachments/assets/cc6300e2-461b-4dcf-90d9-7e4d4d999102" />

Seasonality Plot 


<img width="493" height="161" alt="image" src="https://github.com/user-attachments/assets/4d994c92-2414-47a0-8105-4282722dd542" />



Residual Plot


<img width="541" height="155" alt="image" src="https://github.com/user-attachments/assets/ba1bb816-93d6-40c4-9bb8-370fbe614441" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
