# Weather Impact on Agricultural Commodities (MScFE 690 Capstone)

Minh Tien Phung · Minh Chau Pham. WorldQuant University MScFE, Commodities track, Topic 3.

Code for our capstone on how weather affects agricultural commodities. We study:
- price relationships between corn and wheat, and between soybean oil and rapeseed oil, in the US and Europe;
- the impact of temperature and precipitation on crop yields;
- price spreads and their speed of mean reversion.

## Contents

| Path | What it is |
|---|---|
| `weather_agri_commodities.ipynb` | Main notebook: code outline, data pipeline, EDA and initial results (executed, outputs included) |
| `data/raw/` | Cached downloads behind the results shown in the notebook |
| `requirements.txt` | Python dependencies |

## How to run

**Google Colab.** Open the notebook in Colab (File → Open notebook → GitHub, then paste this repository's URL, or go to
`https://colab.research.google.com/github/<github-user>/<repo>/blob/main/weather_agri_commodities.ipynb`),
then choose Runtime → Run all. Missing packages install automatically, and the data downloads in under a minute.

**Locally.**

```bash
pip install -r requirements.txt
jupyter lab weather_agri_commodities.ipynb
```

The notebook reuses the CSV files in `data/raw/`. To download the latest data, set `REFRESH_DATA = True` in Section 1.

## Data sources (free, no API keys)

- Yahoo Finance: CBOT corn, wheat and soybean oil futures; EUR/USD
- European Commission Agri-food Data Portal: EU-average breadmaking wheat and feed maize prices
- World Bank Commodity Price Data (Pink Sheet): Dutch soybean oil, Rotterdam rapeseed oil
- NASA POWER: monthly temperature and precipitation
- USDA FAS PSD Online: production, area harvested and yield for the US and the EU

## Status

Milestone 3: code outline with a working data pipeline and first-pass models. The results are preliminary.