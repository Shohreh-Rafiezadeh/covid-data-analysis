# COVID-19 Global Data Analysis
### From Raw Data to Insights

An exploratory data analysis of historical COVID-19 reports using Python, pandas, NumPy, and Matplotlib.

## Project Overview

This project investigates how reported COVID-19 cases, deaths, and recoveries developed over time and how reported counts varied across geographic reporting entities. It demonstrates a practical data-analysis workflow, from raw data inspection and cleaning to feature engineering, visualization, and statistical interpretation.
- The dataset was downloaded from Kaggle: https://www.kaggle.com/

## Research Questions

- How did reported confirmed cases change over time?
- When did the largest daily increase in reported cases occur?
- Which reporting entities recorded the highest confirmed cases and deaths?
- How did reported recoveries and active cases vary?
- How strongly were reported confirmed cases associated with reported deaths?

## Dataset and Methodology

The dataset contains date-stamped reports with information on observation dates, provinces/states, countries/regions, confirmed cases, deaths, and recoveries.

Data preparation included:
- Checking missing values and duplicate records.
- Removing an empty column and standardizing column names.
- Converting date fields to datetime.
- Creating active-case, reported death-rate, and reported recovery-rate variables.
- Aggregating observations and analyzing changes over time.

**Derived measures**

- Active cases = Confirmed − Deaths − Recovered
- Reported death rate = Deaths / Confirmed × 100
- Reported recovery rate = Recovered / Confirmed × 100

## Key Findings

- Reported confirmed cases increased substantially during the period covered by the dataset.
- The largest one-day increase in the calculated reported series was **15,148 cases on 13 February 2020**.
- Mainland China had the highest reported confirmed-case and death counts in the reporting-entity summary.
- The Pearson correlation between reported confirmed cases and deaths was approximately **0.995**, indicating a very strong positive association. **Correlation does not establish causation.**
- Death and recovery rates require careful interpretation, particularly for entities with small numbers of confirmed cases.

## Visualizations

The `figures/` directory contains five main figures:

1. `global_confirmed_cases.png` — reported confirmed cases over time.
2. `daily_new_cases.png` — daily changes in reported confirmed cases.
3. `top_confirmed_cases.png` — top reporting entities by confirmed cases.
4. `top_deaths.png` — top reporting entities by deaths.
5. `confirmed_vs_deaths.png` — confirmed cases versus deaths on logarithmic axes.

## Tools:

Python · pandas · NumPy · Matplotlib · Jupyter Notebook · LaTeX · Git/GitHub

## Project Structure

```text
covid-data-analysis/
├── data/
│   └── covid_19_data.csv
├── figures/
│   ├── confirmed_vs_deaths.png
│   ├── daily_new_cases.png
│   ├── global_confirmed_cases.png
│   ├── top_confirmed_cases.png
│   └── top_deaths.png
├── notebooks/
│   ├── covid_analysis_cleaned.ipynb
│   └── exploratory_files/
│       └── covid_analysis_exploratory.ipynb
├── report/
│   ├── covid_analysis_report.pdf
│   └── covid_analysis_report.tex
├── requirements.txt
└── README.md
```

## How to Run

1. Clone or download this repository.
2. Install the required Python packages:

   ```bash
   pip install -r requirements.txt
   ```

3. Open `notebooks/covid_analysis_cleaned.ipynb` in Jupyter.
4. Run the notebook cells from top to bottom OR run run all cells at once.

Keep the repository folder structure intact. The notebook expects the dataset at `data/covid_19_data.csv`.

## Limitations

The dataset combines country-level and province/state-level reporting, so totals may not represent perfectly standardized global epidemiological estimates. Reported values can also be affected by testing, case definitions, reporting practices, revisions, and timing.

Death and recovery rates are descriptive snapshots rather than final clinical outcomes. Absolute counts are not population-adjusted, and small denominators can produce unstable percentages. The findings should therefore be interpreted as patterns in the supplied dataset, not definitive epidemiological estimates.

## Report

The detailed report is available in `report/covid_analysis_report.pdf`, with the LaTeX source in `report/covid_analysis_report.tex`.

## Author

**[Shohreh Rafiezadeh]** — Data Analytics Portfolio Project
