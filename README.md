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

Resolve these choices before downloading the final dataset. They are not specified in the pitch.

- **Study period:** Choose explicit start and end dates that include years before and after 2015.
- **Geographic boundary:** Decide whether the study covers Nepal's national boundary or a wider surrounding region. A rectangular search area may include neighboring countries.
- **Minimum magnitude:** Choose and document a consistent threshold, considering catalog coverage over the study period.
- **2015 comparison:** Define the before/after windows and the geographic area used to examine the Gorkha sequence.
- **Season definitions:** If comparing seasons, define their months explicitly.

## Data

Download a CSV from the USGS Earthquake Catalog and preserve an unchanged copy in `data/raw/`.

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
├── docs/               # Scope decisions, data notes, and methodology
├── notebooks/          # Python notebooks for cleaning and analysis
```
