import alpaca_trade_api as tradeapi

# Replace 'YOUR_API_KEY' and 'YOUR_SECRET_KEY' with your Alpaca API key and secret
API_KEY = 'YOUR_API_KEY'
SECRET_KEY = 'YOUR_SECRET_KEY'

# Create an Alpaca API connection
api = tradeapi.REST(API_KEY, SECRET_KEY, base_url='https://paper-api.alpaca.markets')  # Use the paper trading base URL

# Function to place a market order
def place_market_order(symbol, quantity, side):
    api.submit_order(
        symbol=symbol,
        qty=quantity,
        side=side,
        type='market',
        time_in_force='gtc'
    )

# Your trading strategy goes here
def trading_strategy():
    # Replace this with your actual trading strategy logic
    # Example: Buy 10 shares of AAPL if the 10-day moving average crosses above the 50-day moving average
    symbol = 'AAPL'
    quantity = 10

    # Implement your strategy here, e.g., using technical indicators, machine learning models, etc.

    # For demonstration purposes, let's place a market order to buy
    place_market_order(symbol, quantity, 'buy')

# Execute the trading strategy
trading_strategy()
