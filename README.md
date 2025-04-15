
# Stocex 🧠📈  
**AI-Powered Intraday Trading Assistant using News + TimeGPT**

---

## 🧩 What is Stocex?

**Stocex** is a lightweight yet powerful Python script that scans daily financial headlines, scores their sentiment using FinBERT, detects affected stocks, fetches intraday price data, forecasts future prices using TimeGPT, and generates actionable trade signals.

---

## ⚙️ How It Works

> 🧠 Just run one script and everything happens automatically.

### 🔁 Pipeline Overview

1. **Fetch News (via NewsAPI):**  
   Get yesterday’s market headlines from Bloomberg, WSJ, CNBC, etc.

2. **Sentiment Scoring (FinBERT):**  
   Use HuggingFace FinBERT to score each headline (positive, neutral, negative)

3. **Company Detection (spaCy):**  
   Extract mentioned companies using Named Entity Recognition (NER)

4. **Ticker Mapping:**  
   Match company names to real stock tickers (e.g., Apple → AAPL)

5. **Intraday Price Data (yfinance):**  
   Download 5-minute historical data for last 30 days for each ticker

6. **Forecasting (TimeGPT-1):**  
   Forecast next 12 bars (1 hour) using Nixtla’s TimeGPT-1 API

7. **Signal Generation:**  
   Combine sentiment and forecast direction:
   - ✅ BUY = positive sentiment & forecast up
   - ❌ SELL = negative sentiment & forecast down
   - 🤝 HOLD = neutral or conflicting signals

8. **Output:**  
   Prints signal for each ticker (e.g., `AAPL: BUY`, `TSLA: HOLD`)

---

## 📦 Dependencies

Install everything using:

```bash
pip install -r requirements.txt
```

Typical dependencies include:
- `yfinance`
- `transformers`
- `spacy`
- `requests`
- `pandas`
- `torch`

Also run:

```bash
python -m spacy download en_core_web_sm
```

---

## ▶️ Usage

```bash
# Just run the script
python stocex.py
```

That’s it — the script handles:
- News → Sentiment → Forecast → Signal

---

## 🖥️ Sample Output

```
📅 News fetched for 2025-04-10
🔍 Tickers mentioned: ['AAPL', 'TSLA', 'NCLH']
📈 Forecasted next 12 bars with TimeGPT
✅ AAPL: BUY (positive news + price ↑)
❌ TSLA: SELL (negative news + price ↓)
🤝 NCLH: HOLD (neutral news or mixed forecast)
```

---

## 📜 License

MIT License – free to use, modify, and share!

---

## 📬 Contact

For queries or collaborations:  
📧 **stocex.team@gmail.com**

> _“Let the AI read the news, so you can read the profits.”_ 💹
