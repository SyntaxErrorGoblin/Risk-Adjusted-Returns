# Risk-Adjusted Returns: Emerging vs Frontier vs Developed Markets


## Hypothesis

**Null Hypothesis (Hâ‚€):** *There is no statistically significant difference in risk-adjusted returns between ETFs tracking high-risk and low-risk country indices.*

## Data & Setup

### Data Sources
`yfinance` — downloads:
- `^IRX` (3-month Treasury bill) — risk-free rate
- `SPY` (US large cap ETF)
- `EEM` (Emerging markets ETF)
- `FM` (Frontier markets ETF)

Time period: 2013-12-31 to 2023-12-31 (monthly data)

Data processing: Monthly returns calculated from adjusted close prices

## Observed Results

**Performance Metrics (2014-2023)**
<img width="1001" height="547" alt="output" src="https://github.com/user-attachments/assets/5acf64aa-b85f-4e6a-b7e8-84f7675fd438" />

| ETF | Description | Ann. Return | Ann. Volatility | Sharpe | Sortino |
|-----|-------------|-------------|-----------------|--------|---------|
| SPY | US large cap | 12.46% | 15.16% | 0.74 | 1.07 |
| EEM | Emerging | 3.33% | 17.51% | 0.12 | 0.19 |
| FM | Frontier | 2.66% | 16.70% | 0.08 | 0.11 |

SPY outperformed by ~10% annually while maintaining lower volatility. The cumulative return chart shows SPY's consistent growth versus prolonged drawdowns in EEM and FM with limited recovery.

## Statistical Interpretation

SPY's Sharpe ratio (0.74) significantly exceeds EEM (0.12) and FM (0.08), with the gap large enough to be statistically significant over the 10-year period. Sortino ratios confirm the same pattern. T-tests show SPY's excess returns are significantly positive (p < 0.01), while EEM and FM returns are not significantly different from zero after adjusting for the risk-free rate.

## Exploring the Differences

**Correlation**: SPY-EEM (0.70) and SPY-FM (0.61) suggest moderate diversification potential, but this breaks down in downturns.

**Downside Beta**: FM's downside beta of 1.1 means it amplifies SPY's losses despite lower overall correlation. EEM's 0.70 is better but still substantial—both ETFs fail to provide tail-risk protection.

**Conditional VaR**: During SPY's 10 worst months, EEM and FM averaged 0.91x and 0.85x of SPY's losses respectively, showing some (limited) decoupling during extreme events.

## Key Takeaways

- SPY dominated on both absolute and risk-adjusted returns during 2014-2023
- EEM and FM provided minimal diversification benefits and poor downside protection
- The ~10% annualized return gap represents a steep opportunity cost for international diversification
- Downside beta analysis reveals asymmetric risk: markets move together during crashes despite moderate overall correlation
- Any allocation to EEM/FM requires conviction that future conditions will differ from this historical period

## Limitations

- 10-year period may not capture full market cycles(10 year period chosen as FM ETF launched 2012)
- All analysis is done on a macro level
- Doesn't account for differing industries, market cap etc of average company within these ETFs
- 2014-2023 has been generally bullish market so this doesn't account for how the different funds would react under far more stress
## How to Run / Reproduce

### Prerequisites
``bash
pip install -r requirements.txt
`` 

### Running the Analysis
Just run all cells and take a look at the notes

## Further Work / Notes
- Time period could be increased
- Indivdual countries could be looked instead of taking funds that look at multiple continents
- More granular analysis such as industry specific statistics, returns, beta etc.

---

**Note:** This is a research analysis project. Results are based on historical data and should not be construed as investment advice.

