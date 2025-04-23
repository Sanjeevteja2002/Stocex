# Weekly/Bi-Weekly Log

## Prompts
Following the [Rose/Bud/Thorn](https://www.panoramaed.com/blog/rose-bud-thorn-activity-and-worksheet#:~:text=%22Rose%2C%20Bud%2C%20Thorn%22%20is%20a%20mindful%20design%2D,day%2C%20week%2C%20or%20month.) model:

🗓 Date:
Week 1 – April 14, 2025

⏱ Number of hours:
~18–20 hours
(News fetching, ticker extraction, FinBERT sentiment analysis, yfinance integration for historical price data)

🌹 Rose – Highlight of the week:
Successfully created an automated pipeline to fetch financial news from NewsAPI, extract S&P 500 stock tickers using NLP (SpaCy), and analyze sentiment using FinBERT. The pipeline produced a meaningful output showing dominant sentiment and sentiment score per mentioned stock ticker — a huge milestone for the Stocex project!

🌱 Bud – Looking forward to:
Integrating forecasting with Chronos or TimeGPT, and combining those forecasts with sentiment scores to build real-time trading signals. There's a strong potential here to generate actionable insights based on news-driven movement, and this will be crucial in moving towards the live signal dashboard.

🥀 Thorn – Challenges:
Slight ambiguity in matching company names from the headlines with tickers (string matching wasn’t always perfect).

Loading chronos-ts failed locally — had to revert to TimeGPT for now.

Fetching intraday data from yfinance is slightly slow and sometimes flaky for certain tickers.

💭 Additional thought:
Make sure to modularize the functions and package the full Steps 1–4 logic cleanly, so this pipeline can run automatically every morning. Also consider caching or saving results (e.g., yesterday’s news and sentiment_df) locally or in S3 to avoid reprocessing. This will help scale better when moving toward the alert and visualization stages.
---

