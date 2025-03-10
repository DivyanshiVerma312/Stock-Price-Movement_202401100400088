
 Stock Price Movement Analysis

This project fetches stock price data from Yahoo Finance, calculates short-term trends using Simple Moving Averages (SMA), and visualizes the stock's price movement.

 Features
- Fetch historical stock data using Yahoo Finance API (`yfinance`).
- Calculate **10-day** and **20-day Simple Moving Averages (SMA)**.
- Plot stock prices along with moving averages for trend analysis.
- Identify short-term stock trends to assist in trading decisions.

 Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/stock-price-movement.git
   cd stock-price-movement
   ```
2. Install the required dependencies:
   ```sh
   pip install -r requirements.txt
   ```

 Dependencies
Make sure you have the following Python libraries installed:
```sh
pip install yfinance matplotlib pandas
```

 Usage
Run the script with the following command:
```python
python stock_analysis.py
```

 Example Code Usage
```python
import yfinance as yf
import matplotlib.pyplot as plt
import pandas as pd

def plot_stock_movement(ticker, start_date, end_date):
    stock = yf.download(ticker, start=start_date, end=end_date)
    if stock.empty:
        print("No data found for the given stock ticker.")
        return
    stock['SMA_10'] = stock['Close'].rolling(window=10).mean()
    stock['SMA_20'] = stock['Close'].rolling(window=20).mean()
    plt.figure(figsize=(12,6))
    plt.plot(stock.index, stock['Close'], label='Close Price', color='blue')
    plt.plot(stock.index, stock['SMA_10'], label='10-day SMA', color='red', linestyle='dashed')
    plt.plot(stock.index, stock['SMA_20'], label='20-day SMA', color='green', linestyle='dashed')
    plt.title(f"Stock Price Movement: {ticker}")
    plt.xlabel("Date")
    plt.ylabel("Price (USD)")
    plt.legend()
    plt.grid()
    plt.show()

 Example usage
ticker_symbol = "AAPL"
start = "2024-01-01"
end = "2024-03-01"
plot_stock_movement(ticker_symbol, start, end)
```

 Example Output
The script will generate a stock price movement chart with moving averages to highlight trends.

 Contributions
Contributions are welcome! Feel free to submit issues and pull requests.

 License
This project is licensed under the MIT License.
 Author
 Divyanshi verma- [GitHub Profile](https://github.com/DivyanshiVerma312/Stock-Price-Movement_202401100400088)

