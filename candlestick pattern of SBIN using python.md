# Candlestick pattern

Here's a sample Python script that uses the Ta-Lib library to detect candlestick patterns for the stock prices of SBIN:

```py
import pandas as pd
import talib

# Load the data into a Pandas dataframe
data = pd.read_csv("SBIN.csv")

# Compute the candlestick patterns using Ta-Lib
data["pattern"] = talib.get_pattern_results(data["Open"], data["High"], data["Low"], data["Close"])

# Print the patterns for the last 5 days
last_5_days = data.tail(5)
print("Candlestick patterns for the last 5 days:")
print(last_5_days[["pattern"]])
```
Note that this script assumes that you have a file named SBIN.csv that contains the historical data for the stock prices of SBIN. The data should have the following columns: Date, Open, High, Low, Close, Adj Close, and Volume. The script uses the get_pattern_results function from the Ta-Lib library to compute the candlestick patterns. The function returns a code for each pattern, which can be translated into a description of the pattern using the talib.get_pattern_name function.
