# Weather Impact on Agricultural Commodities (MScFE 690 Capstone)

Minh Tien Phung · Minh Chau Pham. WorldQuant University MScFE, Commodities track, Topic 3.

Code for our capstone on how weather affects agricultural commodities. We study:
- price relationships between corn and wheat, and between soybean oil and rapeseed oil, in the US and Europe;
- the impact of temperature and precipitation on crop yields, and from yields to prices;
- price spreads and their speed of mean reversion.

## Contents

| Path | What it is |
|---|---|
| `weather_agri_commodities.ipynb` | Main notebook: data pipeline, EDA, cointegration and error correction models, weather, yield and price regressions, US vs EU tests, key results (executed, outputs included) |
| `bloomberg_daily_analysis.ipynb` | Companion notebook on daily Bloomberg data (1990–2026) supplied by our instructor: serial correlation, mean reversion, ARIMA, GARCH, seasonality, corn and wheat over 36 years, a US vs EU comparison with cash prices on both sides, and the basis (executed, outputs included) |
| `data/raw/` | Cached downloads behind the results shown in the main notebook |
| `requirements.txt` | Python dependencies |

## How to run

**Google Colab.** Open the notebook in Colab (File → Open notebook → GitHub, then paste this repository's URL, or go to
`https://colab.research.google.com/github/chaupmbn/mscfe-capstone-weather-agri/blob/master/weather_agri_commodities.ipynb`),
then choose Runtime → Run all. Missing packages install automatically, and the notebook loads the cached data from this repository (commit `9c1db45`), so the results match the report.

**Locally.**

```bash
pip install -r requirements.txt
jupyter lab weather_agri_commodities.ipynb
```

The main notebook reuses the CSV files in `data/raw/` (downloaded on 28 September 2026), so a re-run gives the same results. A missing file is copied from commit `9c1db45` of this repository. To download the latest data, set `REFRESH_DATA = True` in Section 1.

The companion notebook needs `data/raw/Ags.xlsx`, a Bloomberg extract supplied by our instructor. Bloomberg data may not be redistributed, so the file is not in this repository (see `.gitignore`). The saved outputs show the results.

Tested with Python 3.10.14, numpy 1.26.4, pandas 2.3.0, scipy 1.15.3, statsmodels 0.14.4, arch 7.0.0 and matplotlib 3.8.3.

## Data sources

Free, no API keys (main notebook):
- Yahoo Finance: CBOT corn, wheat and soybean oil futures; EUR/USD
- European Commission Agri-food Data Portal: EU-average breadmaking wheat and feed maize prices
- World Bank Commodity Price Data (Pink Sheet): Dutch soybean oil, Rotterdam rapeseed oil, US Gulf maize and wheat
- NASA POWER: monthly temperature and precipitation
- USDA FAS PSD Online: production, area harvested and yield for the US and the EU

Not included (companion notebook): Bloomberg daily CBOT corn, wheat and soybean futures and USDA cash prices, 1990–2026.

## Status

Draft Project: both notebooks run end to end. New since Milestone 4: the companion notebook on daily Bloomberg data; a decision rule when the cointegration tests disagree; HAC and Driscoll–Kraay standard errors; system half-lives; a direct test of hedge-ratio stability; weak-instrument checks for the weather-to-price link; the effect of monthly averaging on ARMA results; and a data snapshot pinned to a commit. The results are discussed in the Draft Project report.
