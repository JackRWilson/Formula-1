# Content Navigation

- [overview](../README.md) - Project overview

- **data - All datasets used in the project**
  - [raw](../data/raw/README.md) - Unprocessed scraped data
  - [intermediate](../data/intermediate/README.md) - Merged or cleaned transitional data
  - [final](../data/final/README.md) - Final datasets used for analysis
- [docs](../docs/README.md) - Project proposal, final report, and presentation materials
- [notebooks](../notebooks/README.md) - Jupyter Notebooks for scraping, cleaning, and analysis

# Page Contents

- [Folder Overview](#Folder-Overview)
- [Data Overview](#Data-Overview)
  - [Final Analysis Data](#Final-Analysis-Data)
  - [Data Dictionary](#Data-Dictionary)

# Folder Overview

This folder contains the various stages of CSVs used in the analysis and cleaning process.

| Folder         | Description                                                                  | README                                      |
| -------------- | ---------------------------------------------------------------------------- | ------------------------------------------- |
| `raw`          | Raw files from scraping                                                      | [raw](data/raw/README.md)                   |
| `intermediate` | Files that have been altered or enriched, used later in the analysis process | [intermediate](data/intermediate/README.md) |
| `final`        | Clean and analysis ready files                                               | [final](data/final/README.md)               |

# Data Overview

- All data was scraped from the [Official F1 Results Website](https://www.formula1.com/en/results/2025/races)

- Data was scraped from all races years 1950 - 2024

- Specific scraping links can be found in the [raw folder README](data/raw/README.md)

### Final Analysis Data

- The final analysis data contains 3510 rows and 50 features. Each row represents a driver's aggregated performance across all races in a given season. Many of the features are engineered based on existing columns to improve machine learning and other analysis. 

### Data Dictionary

| Column                    | Description                                                              | Type    |
| ------------------------- | ------------------------------------------------------------------------ | ------- |
| `year`                    | The season year                                                          | Numeric |
| `driver`                  | Driver name                                                              | Text    |
| `team_name`               | Name of the constructor/team                                             | Text    |
| `continent`               | Continent of the driver                                                  | Text    |
| `season_rank`             | Driver’s final rank in the season                                        | Numeric |
| `avg_start_pos`           | Average start position across the season                                 | Numeric |
| `std_start_pos`           | Standard deviation of starting positions                                 | Numeric |
| `best_start_pos`          | Best start position                                                      | Numeric |
| `worst_start_pos`         | Worst start position                                                     | Numeric |
| `races_participated`      | Number of races competed in                                              | Numeric |
| `avg_finish_pos`          | Average finishing position                                               | Numeric |
| `std_finish_pos`          | Standard deviation of finishing positions                                | Numeric |
| `best_finish_pos`         | Best race finish                                                         | Numeric |
| `worst_finish_pos`        | Worst race finish                                                        | Numeric |
| `total_pos_gain`          | Positions gained from start to finish across all races                   | Numeric |
| `avg_pos_gain`            | Average position gain per race                                           | Numeric |
| `total_points`            | Total points scored                                                      | Numeric |
| `avg_points_per_race`     | Average points scored per race                                           | Numeric |
| `total_pct_season_points` | Percentage of total available season points earned                       | Numeric |
| `avg_pct_season_points`   | Average percentage of available season points per race                   | Numeric |
| `worst_pct_season_points` | Lowest points percentage in a race                                       | Numeric |
| `best_pct_season_points`  | Highest points percentage in a race                                      | Numeric |
| `total_laps_completed`    | Number of laps completed                                                 | Numeric |
| `total_laps`              | Total laps possible                                                      | Numeric |
| `total_fastest_laps`      | Number of fastest laps earned                                            | Numeric |
| `CLAS_total`              | Number of Classified finishes                                            | Numeric |
| `DNF_total`               | Number of Did Not Finish results                                         | Numeric |
| `DNS_total`               | Number of Did Not Start results                                          | Numeric |
| `DQ_total`                | Number of Disqualified results                                           | Numeric |
| `NC_total`                | Number of Not Classified results                                         | Numeric |
| `backmarker`              | Backmarker indication                                                    | Bool    |
| `midfield`                | Midfielder indication                                                    | Bool    |
| `podium_regular`          | Podium regular indication                                                | Bool    |
| `points_regular`          | Points regular indication                                                | Bool    |
| `years_experience`        | Number of years the driver has competed in                               | Numeric |
| `total_podium_finishes`   | Total podium finishes in the season                                      | Numeric |
| `total_points_finishes`   | Total points finishes in the season                                      | Numeric |
| `dnf_rate`                | Percentage of DNFs over races entered                                    | Numeric |
| `finish_rate`             | Percentage of races finished                                             | Numeric |
| `lap_completion_rate`     | Percentage of laps completed                                             | Numeric |
| `fastest_lap_rate`        | Fastest laps as a percentage of races entered                            | Numeric |
| `podium_rate`             | Podium finishes as a percentage of races entered                         | Numeric |
| `points_rate`             | Points finishes as a percentage of races entered                         | Numeric |
| `consistency_score`       | Consistency in finish positions                                          | Numeric |
| `qualifying_consistency`  | Consistency in start positions                                           | Numeric |
| `reliability_score`       | Measures a drivers finish rate with lap completion rate                  | Numeric |
| `qualifying_vs_race`      | Comparison of qualifying vs finishing positions                          | Numeric |
| `championship_impact`     | Strength of contribution to the championship outcome                     | Numeric |
| `race_improvement`        | Average improvement from start to finish positions                       | Numeric |
| `driver_retained`         | Driver retained indication                                               | Bool    |
