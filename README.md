# Understanding Earthquake Patterns in Nepal

**How often, where, and how strong?**

A research project exploring historical earthquake records to understand patterns in Nepal: changes in frequency, geographic distribution, magnitude and depth, monthly activity, and activity around the 2015 Gorkha earthquake.

The project follows the research pitch *Understanding Earthquake Patterns in Nepal*. The planned data source is the [USGS Earthquake Catalog](https://earthquake.usgs.gov/earthquakes/search/), with analysis in Python and Pandas.

## Research questions

| Question | Planned analysis | Expected output |
| --- | --- | --- |
| How has earthquake frequency changed over time? | Count recorded earthquakes by year and month. | Time-series line charts. |
| Where do earthquakes occur most, and where are the strongest? | Compare event locations, geographic concentrations, and magnitudes. | Earthquake maps with magnitude markers. |
| Are magnitude and depth related? | Plot magnitude against depth and assess the relationship. | Scatterplot and a relationship summary. |
| Do earthquakes follow monthly or seasonal patterns? | Compare monthly rates across years and check whether patterns repeat. | Monthly bar chart and, if supported, seasonal comparisons. |
| How did activity change after the 2015 Gorkha earthquake? | Compare frequency and magnitude in equal time windows before and after the event. | Before/after charts and a short interpretation. |

A magnitude histogram will also describe the distribution of earthquake sizes in the selected dataset.

## Study scope

The study period and minimum magnitude come from the filtered earthquake dataset.

- The **study period** runs from May 28, 1951, through November 11, 2026 (UTC), the dates of the oldest and newest recorded earthquakes in the filtered dataset.
- The **minimum magnitude** is 3.0, the lowest recorded magnitude in the filtered dataset.
- **Geographic boundary:** Decide whether the study covers Nepal's national boundary or a wider surrounding region. A rectangular search area may include neighboring countries.
- **2015 comparison:** Define the before/after windows and the geographic area used to examine the Gorkha sequence.
- **Season definitions:** If comparing seasons, define their months explicitly.

## Data

Download a CSV from the USGS Earthquake Catalog and preserve an unchanged copy in `data/raw/`.

Use `data/processed/cleaned.csv` as the input for the analysis notebook. Run `notebooks/datapreprocessing.ipynb` to regenerate and verify it. The `year`, `month`, `day`, and `time_of_day` columns are in UTC.

Run [the analysis notebook](notebooks/dataAnalysis.ipynb) to see the magnitude–depth scatterplot, Pearson correlation, and magnitude histogram.

| Field | Purpose |
| --- | --- |
| `id` | Identify events and detect duplicate records. |
| `time` | Group events by year and month; compare periods. |
| `latitude`, `longitude` | Locate earthquakes and apply geographic filters. |
| `mag`, `magType` | Analyze earthquake size and document magnitude types. |
| `depth` | Analyze earthquake depth in kilometers. |
| `place` | Provide descriptive location labels when available. |

Record the download date, exact search filters or query URL, source, and original row count in `docs/data-notes.md` when data is collected. Keep cleaned data in `data/processed/` and document missing values, exclusions, and row counts after cleaning.

## Project structure

```text
.
├── README.md
├── data/
│   ├── raw/            # Original catalog downloads
│   └── processed/      # Validated CSV for analysis
├── docs/               # Scope decisions, data notes, and methodology
├── notebooks/          # Python notebooks for cleaning and analysis
```
