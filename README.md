# Weather Impact on Agricultural Commodities (MScFE 690 Capstone)

Minh Tien Phung · Minh Chau Pham. WorldQuant University MScFE, Commodities track, Topic 3.

Code for our capstone on how weather affects agricultural commodities. We study:
- price relationships between corn and wheat, and between soybean oil and rapeseed oil, in the US and Europe;
- the impact of temperature and precipitation on crop yields, and from yields to prices;
- price spreads and their speed of mean reversion.

## Contents

| Path | What it is |
|---|---|
| `weather_agri_commodities.ipynb` | Main notebook: data pipeline, EDA, cointegration and error correction models, weather, yield and price regressions, US vs EU tests, preliminary results (executed, outputs included) |
| `data/raw/` | Cached downloads behind the results shown in the notebook |
| `requirements.txt` | Python dependencies |

## How to run

**Google Colab.** Open the notebook in Colab (File → Open notebook → GitHub, then paste this repository's URL, or go to
`https://colab.research.google.com/github/chaupmbn/mscfe-capstone-weather-agri/blob/master/weather_agri_commodities.ipynb`),
then choose Runtime → Run all. Missing packages install automatically, and the data downloads in under a minute.

**Locally.**

```bash
pip install -r requirements.txt
jupyter lab weather_agri_commodities.ipynb
```

The notebook reuses the CSV files in `data/raw/` (downloaded on 28 September 2026), so a re-run gives the same results. To download the latest data, set `REFRESH_DATA = True` in Section 1.

## Data sources (free, no API keys)

- Yahoo Finance: CBOT corn, wheat and soybean oil futures; EUR/USD
- European Commission Agri-food Data Portal: EU-average breadmaking wheat and feed maize prices
- World Bank Commodity Price Data (Pink Sheet): Dutch soybean oil, Rotterdam rapeseed oil, US Gulf maize and wheat
- NASA POWER: monthly temperature and precipitation
- USDA FAS PSD Online: production, area harvested and yield for the US and the EU

## Status

Milestone 4: working data pipeline and preliminary results. New since Milestone 3: adjustment for futures contract rolls, error correction models, a test of US vs EU mean-reversion speed, stability before and after 2020, and the link from weather to yields to prices. The results are preliminary.
