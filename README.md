# Momentum Trading Strategy using NIFTY 50 Stocks

## 📌 Overview
This project implements a momentum-based trading strategy over NIFTY 50 stocks using Python. The strategy leverages technical indicators like RSI, ROC, VWAP, and volatility to dynamically identify long and short positions and simulate a long-short equity portfolio over the year 2021.

## 🚀 Objectives
- Backtest a momentum strategy on top NIFTY 50 stocks.
- Dynamically select stocks with highest and lowest momentum scores for long and short trades respectively.
- Use technical indicators and volatility-adjusted scoring for better signal reliability.

## ⚙️ Methodology
1. **Stock Universe**: NIFTY 50 constituents as of 2021.
2. **Indicators Used**:
   - RSI (Relative Strength Index)
   - ROC (Rate of Change)
   - VWAP (Volume Weighted Average Price)
   - Annualized Volatility (based on 21-day rolling returns)
3. **Momentum Score Formula**:
   - If ROC > 0:
     ```
     score = normalized_RSI * normalized_ROC * dampened_volatility * log(VWAP + 1)
     ```
   - If ROC <= 0:
     ```
     score = (1 - normalized_RSI) * normalized_ROC * dampened_volatility * log(VWAP + 1)
     ```
4. **Backtesting Logic**:
   - Portfolio is initialized with INR 10,00,000 split equally between long and short.
   - Top-ranked stock is bought (long), bottom-ranked is shorted.
   - Exit conditions:
     - Long stock drops out of top 5
     - Short stock climbs above bottom 5
   - Positions are rebalanced and profits tracked.

## 💻 Technologies Used
- Python (pandas, NumPy, matplotlib, seaborn)
- Yahoo Finance (`yfinance`) for historical stock data
- `pandas_ta` for technical indicators

## 📊 Results
- Final Portfolio Value printed at end of simulation
- Logged all trades, exits, and rebalancing actions

## 📁 Files
- `momentum_strategy.ipynb` – Jupyter notebook with full code

## 📎 How to Run
1. Install dependencies:
   ```bash
   pip install yfinance pandas_ta seaborn matplotlib
   ```
2. Run the notebook in Google Colab or locally using Jupyter Notebook.

## 📈 Example Output (Excerpt)
```
Initial Long Position: HDFCBANK.NS at 1291.0
Initial Short Position: TATAMOTORS.NS at 168.5
...
Final Portfolio Value: ₹1,13,456.78
Final Long Position: INFY.NS at 1345.0
Final Short Position: COALINDIA.NS at 138.2
```

---

## 🤝 Contributing
This was a personal quant research experiment. Feedback and suggestions are welcome.

## 🔗 License
MIT License
