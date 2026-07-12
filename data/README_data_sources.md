# Mumbai Local Train Deaths: A 10-Year Analysis (2015-2024)

Mumbai's suburban railway carries over 7.5 million commuters daily and has one of the highest fatality rates of any transit system in the world. This project analyzes 10 years of Government Railway Police (GRP) data to understand how death rates have changed over time, what factors are driving them, and where the risk is concentrated by line and by gender.

## What this project does

- Compiles a 10-year, cause-of-death dataset (2015-2024) from multiple public news sources reporting on RTI-obtained GRP data
- Analyzes the overall death trend and identifies a structural break caused by COVID-19 that a single linear regression would miss
- Compares death correlation across cause categories using a correlation heatmap
- Compares Central Railway vs Western Railway death totals
- Breaks down deaths by gender across cause categories

## Key findings

- Deaths declined steadily from 2015 (3,304) to 2019 (2,691). The 2020 drop was caused by COVID-19 suspending regular service, not a genuine safety improvement.
- Splitting the regression at the COVID break shows the pre-COVID decline has not resumed since 2021, deaths have plateaued around 2,500/year rather than continuing to improve.
- Falling from moving trains correlates slightly more strongly with total yearly deaths (0.94) than track crossing (0.93), despite track crossing having the higher raw count every year.
- Central Railway consistently records more deaths than Western Railway, and the gap has widened over time.
- Men account for 85-95%+ of deaths across nearly every recorded cause category.

## Data sources and limitations

All data compiled from Government Railway Police (GRP) figures obtained via RTI requests, as reported by Free Press Journal, The Indian Express, The Quint, Business Standard, and India Infra Hub between 2018 and 2025. No single official dataset exists publicly, this was assembled from multiple news reports citing the same underlying GRP source.

Known limitations:
- 10 years of data limits statistical confidence, particularly the post-COVID regression split, which relies on only 4 data points
- GRP data and Railway operational data use different definitions (GRP includes natural deaths and suicides, Railway data does not) and are not directly comparable across all years
- No ridership-by-gender baseline is available, so gender findings report raw counts only, not per-capita risk
- Pre-2015 data exists only as aggregated multi-year totals in available sources, not full cause breakdowns

Full source documentation is in `data/README_data_sources.md`.

## Tech stack

- Python (Pandas, NumPy)
- Seaborn, Matplotlib for visualization
- Jupyter Notebook / Google Colab

## Repository structure

```
mumbai-local-train-deaths/
  notebooks/
    mumbai_train_deaths_analysis.ipynb
  data/
    mumbai_railway_deaths_2015_2024.csv
    mumbai_railway_deaths_by_line_fixed.csv
    mumbai_railway_deaths_gender_split.csv
    README_data_sources.md
  README.md
```

## How to run

1. Clone this repository
2. Install dependencies: `pip install pandas numpy seaborn matplotlib`
3. Open `notebooks/mumbai_train_deaths_analysis.ipynb` in Jupyter or upload to Google Colab
4. Ensure the CSV files in `data/` are accessible from the notebook's working directory

## Author

Built as part of a self-directed data analytics learning track, following prior work on Indian stock market analysis (see [india_stock_analysis](https://github.com/AP180907/india_stock_analysis)).
