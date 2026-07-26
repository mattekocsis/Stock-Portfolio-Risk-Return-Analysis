# Stock Portfolio Risk & Return Analysis

Purpose: Given a set of stocks across different sectors, what is the historical risk-return profile of each and what portfolio allocation would have minimized risk for an expected return over the past 5 year period?
The project is built as a research analyst producing a brief of portfolio construction for a retail investment advisory firm. The audience requests risk-adjusted comparisons and a data backed allocation recommendation.

Data Source: Historical price data from Yahoo Finance using 'yfinance'

Data Size: 5 years of stock history for 10 different stocks across a variety of industries for diversification purposes.

Tools used:
  - Jupyter Notebook (via Anaconda)
  - Python 3.10 (via Jupyter Notebook)
  - yfinance (data procurement)
  - Pandas, Numpy (ETL & calculations)
  - Matplotlib, Seaborn (visuals for dashboard)
  - scipy (portfolio optimization)
  - Git / GitHub (portfolio hosting)
  - Claude Sonnet 5 (brainstorming and ideation, code / spell check, review of deliverables to ensure consistency across project)

Methodology:
  - Use yfinance to webscrape 5 years of stock history for 10 different stocks across a variety of industries (save to .csv).
  - Check for missing values (0 missing values found).
  - Calculate Daily and Cumulative returns (save to .csv).
  - EDA to find:
      - Growth of $1 Invested ("current" value of $1 invested on day one of analysis).
      - Risk vs. Return (Scatter Plot to visualize the best return per unit of risk taken).
      - Daily Return Correlation Matrix (Correlation Heatmap to visualize correlation between stocks).
      - Rolling 30 day Annualized Volatility (Check for risk spike around known market stress events).
      - Max Drawdown per Ticker (The worst peak to trough loss on each asset to capture a worst case scenario).

Key Visuals:

  - Fig.1 - Growth of $1 Invested
  <img width="1800" height="900" alt="fig_growth_of_1" src="https://github.com/user-attachments/assets/538e681f-51cf-46de-a965-ab079c62fc5a" />

  - Fig. 2 - Rolling 30 Day Annualized Volatility
  <img width="1800" height="900" alt="fig_rolling_volatility" src="https://github.com/user-attachments/assets/5ba4199f-beec-4610-ac15-c3793094ecad" />

  - Fig. 3 - Risk vs. Return
  <img width="1350" height="1050" alt="fig_risk_return_scatter" src="https://github.com/user-attachments/assets/188193d1-8dcd-407a-80a0-43f7ff9b61f3" />

Key Findings:
  - Over the 2020 to 2025 period, NVDA delivered the highest risk-adjusted return while also carrying the highest volatility relative to its return.
  - The correlation heatmap showed energy stocks were highly correlated with each other (0.86+ correlation), while technology/growth stocks (NVDA in particular) provided the most diversification benefit, showing near-zero correlation with defensive names like JNJ, KO, and PG.
  - The optimal simulated portfolio allocated 33.9% to NVDA and 27.6% to JNJ with an expected annualized return of 32.9% at 24.1% volatility, compared to the equal-weighted portfolio's 13.0% return at 17.1% volatility.
  - The maximum drawdown analysis showed NVDA experienced the steepest peak-to-trough decline of 66%.

Business Recommendation: An investor prioritizing risk-adjusted return over the analysis period would have been better off by tilting allocation toward NVDA and JNJ, based on the above stated Sharpe ratio and correlation results.

Limitations: This analysis uses historical returns as a proxy for future expected returns, which is a known limitation of mean-variance optimization. It also excludes transaction costs, taxes, and assumes a risk-free rate of 0% for simplicity. A production version would use a proper risk-free rate and consider regime-dependent volatility.


