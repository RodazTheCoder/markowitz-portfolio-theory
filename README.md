# Markowitz Portfolio Optimization with B3 Stocks

Applies Modern Portfolio Theory to Brazilian stocks, then checks whether the optimized portfolio would actually have worked.

## What it does
* Downloads daily prices from Yahoo Finance, adjusted for dividends and splits
* Simulates 100,000 random portfolios, with a 40% cap per stock, and draws the efficient frontier
* Picks the portfolio with the highest Sharpe ratio, using the CDI from the Banco Central do Brasil as the risk-free rate
* Backtests it out of sample: the weights are chosen on older data and tested on a period the model never saw, against an equal weight portfolio and the Ibovespa

## Main result
With Petrobras, Vale, Itaú and WEG, the portfolio that looked best on 2020 to 2024 data returned 3.5% over the test period (October 2024 to December 2025). The same stocks split evenly returned 16.9% and the Ibovespa 22.3%. Historical average returns turned out to be a poor guide to future ones, which is the main known weakness of Markowitz optimization in practice.

## How to run
```
pip install yfinance pandas numpy matplotlib
```
Then run every cell of `cripto-markowitz.ipynb`. To analyze other stocks, change the `tickers` list in the Data Acquisition section.

The project started as a crypto analysis and was later refocused on stocks.
