# Price Verification Sources

Use these sources to confirm any market price, index level, or financial data point
before including it in a blog post or social post. Always confirm across at least
2 independent sources before accepting any figure. For any quoted price level, reference
the last market close and state the date alongside the number.

---

## Equities and Indices (S&P 500, Nasdaq, Dow, Russell 2000)

| Source | URL | Notes |
|---|---|---|
| Yahoo Finance | `https://finance.yahoo.com/quote/^GSPC/` | Replace ^GSPC with ^IXIC (Nasdaq), ^DJI (Dow), ^RUT (Russell 2000) |
| Investing.com | `https://www.investing.com/indices/us-spx-500-historical-data` | Historical daily closes with open/high/low/volume |
| TheStreet live blog | `https://www.thestreet.com/stock-market-today` | Session narratives, confirmed closes, movers |
| Trading Economics | `https://tradingeconomics.com/united-states/stock-market` | Daily summaries with confirmed percentage moves |
| CNBC live updates | `https://www.cnbc.com/stock-market-today-live-updates` | Intraday and close data with context |

**How to confirm:** Search `"S&P 500 close [date]"` and cross-check the percentage and closing price across at least Yahoo Finance and one other source. Minor decimal variance between providers is normal (e.g. 7,511.35 vs 7,511.56). The percentage change is the primary figure to confirm.

---

## VIX (CBOE Volatility Index)

| Source | URL | Notes |
|---|---|---|
| Yahoo Finance | `https://finance.yahoo.com/quote/^VIX/` | Shows current, previous close, day range |
| CNBC | `https://www.cnbc.com/quotes/.VIX` | Confirmed daily close with prev close reference |
| Cboe official | `https://www.cboe.com/tradable-products/vix/` | Primary source, delayed data |
| Investing.com | `https://www.investing.com/indices/volatility-s-p-500` | Historical data and daily close |

**Important:** VIX spot and VIX futures trade at different levels. Always specify which you are quoting. Spot VIX (^VIX) is the standard reference for market commentary.

---

## Individual Stocks

| Source | URL | Notes |
|---|---|---|
| Yahoo Finance | `https://finance.yahoo.com/quote/[TICKER]/` | Current price, % change, day range, prev close |
| Investing.com | `https://www.investing.com/equities/[company-name]` | Historical closes |
| MacroTrends | `https://www.macrotrends.net/stocks/charts/[TICKER]/[company]/stock-price-history` | Historical daily closes going back years |
| Robinhood | `https://robinhood.com/us/en/stocks/[TICKER]/` | Intraday range and close with volume |

---

## Commodities (Oil, Gold, Silver)

| Source | URL | Notes |
|---|---|---|
| Investing.com WTI | `https://www.investing.com/commodities/crude-oil` | WTI futures close and % change |
| Investing.com Brent | `https://www.investing.com/commodities/brent-oil` | Brent futures close and % change |
| Investing.com Gold | `https://www.investing.com/commodities/gold` | Gold spot and futures |
| Yahoo Finance Oil | `https://finance.yahoo.com/quote/CL=F/` | WTI crude futures |
| Yahoo Finance Gold | `https://finance.yahoo.com/quote/GC=F/` | Gold futures |
| Trading Economics | `https://tradingeconomics.com/commodity/crude-oil` | Daily price with context |

**Note for gold in 2026:** Gold is trading in the $4,000-4,500 range as of June 2026. Any figure near $2,300 is stale data from 2024. Always verify current price before publishing.

---

## Forex (Major Pairs)

| Source | URL | Notes |
|---|---|---|
| Investing.com | `https://www.investing.com/currencies/[pair]-historical-data` e.g. `eur-usd-historical-data` | Daily OHLC |
| Yahoo Finance | `https://finance.yahoo.com/quote/EURUSD=X/` | Live and historical quotes |
| Trading Economics | `https://tradingeconomics.com/[country]/currency` | Central bank context alongside price |
| Baystreet | Search `"[pair] June [date] 2026"` | Often surfaces in news search results with exact levels |

---

## Crypto (BTC, ETH, Fear & Greed)

| Source | URL | Notes |
|---|---|---|
| Yahoo Finance BTC | `https://finance.yahoo.com/quote/BTC-USD/` | BTC/USD close and % change |
| Robinhood | `https://robinhood.com/us/en/stocks/BTC/` | Intraday range and close |
| Alternative.me | `https://alternative.me/crypto/fear-and-greed-index/` | Crypto Fear and Greed Index current and historical |
| SoSoValue | `https://sosovalue.com/assets/etf/us-bitcoin-spot` | Bitcoin and Ethereum ETF daily flow data |
| Trading Economics | `https://tradingeconomics.com/crypto` | Macro context alongside price |

---

## Economic Data Releases (CPI, PPI, NFP, GDP, Retail Sales)

| Data | Primary source | URL |
|---|---|---|
| CPI | BLS | `https://www.bls.gov/cpi/` |
| PPI | BLS | `https://www.bls.gov/ppi/` |
| NFP / Jobs | BLS | `https://www.bls.gov/news.release/empsit.nr0.htm` |
| GDP | BEA | `https://www.bea.gov/data/gdp/gross-domestic-product` |
| Retail Sales | Census Bureau | `https://www.census.gov/retail/` |
| PCE | BEA | `https://www.bea.gov/data/personal-consumption-expenditures-price-index` |
| PMI (ISM) | ISM | `https://www.ismworld.org/supply-management-news-and-reports/reports/ism-report-on-business/` |
| JOLTS | BLS | `https://www.bls.gov/jlt/` |

**Rule:** Always check the primary government source for economic releases. Secondary sources (Reuters, Bloomberg, CNBC) are acceptable for confirmation but the BLS/BEA figure is definitive.

---

## Fed / FOMC Data

| Data | Source | URL |
|---|---|---|
| Rate decision and statement | Federal Reserve | `https://www.federalreserve.gov/monetarypolicy/fomccalendars.htm` |
| Dot plot (SEP) | Federal Reserve | `https://www.federalreserve.gov/monetarypolicy/fomcprojtabl[year].htm` |
| CME FedWatch (rate probabilities) | CME Group | `https://www.cmegroup.com/markets/interest-rates/cme-fedwatch-tool.html` |
| Current Fed Funds rate | FRED | `https://fred.stlouisfed.org/series/FEDFUNDS` |

---

## Treasury Yields

| Source | URL | Notes |
|---|---|---|
| CNBC | `https://www.cnbc.com/bonds/` | 2Y, 10Y, 30Y with daily change |
| Yahoo Finance 10Y | `https://finance.yahoo.com/quote/^TNX/` | 10-year yield |
| Investing.com | `https://www.investing.com/rates-bonds/usa-government-bonds` | Full yield curve |
| FRED | `https://fred.stlouisfed.org/series/DGS10` | Historical 10-year daily closes |

---

## Bitcoin ETF Flows

| Source | URL | Notes |
|---|---|---|
| SoSoValue | `https://sosovalue.com/assets/etf/us-bitcoin-spot` | Daily net flows per fund, cumulative totals |
| Farside Investors | `https://farside.co.uk/bitcoin-etf-flow-all-data-table/` | Historical daily flow table |

---

## Untrusted Auxiliary Sources (use with hard constraints, not for verification)

These are NOT verification sources — they don't satisfy the "2+ independent sources" rule and
never substitute for the sources above. Listed here because they're pulled by an automated routine
with no human in the loop, so their trust boundary needs to be documented somewhere durable, not
left as freestanding caveats inside one step of one routine file where they're easy to lose on the
next edit.

| Source | URL pattern | Used by | Constraints |
|---|---|---|---|
| everyticker.com | `https://everyticker.com/api/quote/{TICKER}/financial-analysis` | Ticker Pulse (`private/box-instructions-ticker-pulse.md` Step 3.5) | Cached article, not live (`article_date` field, `cached: true`). Verified live failure: served TEAM at a 3-month-stale $85/share with a negative P/E days after the real print put it at ~$150 with positive GAAP EPS. Hard rules: discard if `article_date` >45 days old; discard any qualitative claim that overlaps the same subject as that day's verified catalyst (moats/competitive position/pipeline dependency go stale exactly as fast as numbers do when a legal/regulatory/competitive event flips them); any surviving qualitative claim needs one independent confirming search before use, never taken as-is (likely LLM-generated, single-source, `cached: true`); never use any numeric field, ever, regardless of date; never name it in published text. |

**If adding another auxiliary source to any routine:** document it here with the same shape
(source, used by, constraints) rather than only inline in the routine file.

---

## General Verification Protocol

1. **Search first:** Run `"[index/asset] close [date]"` in web search to surface multiple sources simultaneously
2. **Check two sources minimum:** Yahoo Finance and Investing.com cover most needs. For economic data, use primary government sources
3. **Confirm the date:** Data providers sometimes show the most recent close which may be a different session. Check the "at close: [date]" label on Yahoo Finance
4. **Percentage vs price:** Confirm both the closing price and the percentage change. If they conflict between sources, the percentage change from a confirmed prior close is more reliable
5. **Futures vs spot:** For commodities and volatility, specify whether you are quoting futures or spot. They trade at different levels
6. **Stale data flag:** If a price looks inconsistent with the broader market narrative (e.g. gold at $2,300 when recent context suggests $4,000+), treat it as a red flag and verify immediately
