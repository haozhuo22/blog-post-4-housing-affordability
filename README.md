# Priced Out Twice

This repository contains the complete, reproducible project for Blog Post 4 in AEDS 6400. It studies how U.S. new-home prices, 30-year mortgage rates, and median household income changed an illustrative homebuyer's mortgage-payment burden.

## Repository contents

- `index.qmd`: article with three substantive visualizations and a summary table.
- `R/01_download_data.R`: downloads five public FRED CSV series without an API key.
- `R/02_analysis.R`: cleans and merges the data, constructs the affordability measures, validates the results, and exports all figures and processed tables.
- `data/raw/`: downloaded source series.
- `data/processed/housing_affordability_quarterly.csv`: analysis-ready quarterly dataframe.
- `data/processed/scenario_decomposition.csv`: 2019–2025 sequential counterfactual.
- `data/processed/key_years.csv`: selected observations used in the article table.
- `data/source_metadata.csv`: source agencies, units, frequencies, URLs, and retrieval date.
- `figures/`: three publication-ready PNG charts.

## Reproduce the project

Open `blog-post-4-housing-affordability.Rproj` in RStudio, set the project as the working directory, and run:

```r
source("R/01_download_data.R")
source("R/02_analysis.R")
```

Then render `index.qmd`. Required R packages are `dplyr`, `readr`, `lubridate`, `tidyr`, `ggplot2`, `scales`, and `knitr`.

## Method

The illustrative buyer makes a 20% down payment and finances the balance with a 30-year fixed-rate mortgage. Annual principal and interest are divided by annual median household income. The measure excludes taxes, insurance, maintenance, fees, and regional differences; it is descriptive and is not an underwriting standard.

## Data sources

All series are obtained from the Federal Reserve Bank of St. Louis FRED graph CSV endpoint. The original providers are the U.S. Census Bureau, U.S. Department of Housing and Urban Development, Freddie Mac, U.S. Bureau of Labor Statistics, and National Bureau of Economic Research recession dates as represented by FRED. Exact series links appear in `data/source_metadata.csv` and the article.
