# Content Navigation

- [overview](../../README.md) - Project overview

- [data](../../data/README.md) - All datasets used in the project
  - **raw - Unprocessed scraped data**
  - [intermediate](../../data/intermediate/README.md) - Merged or cleaned transitional data
  - [final](../../data/final/README.md) - Final datasets used for analysis
- [docs](../../docs/README.md) - Project proposal, final report, and presentation materials
- [notebooks](../../notebooks/README.md) - Jupyter Notebooks for scraping, cleaning, and analysis

# Page Contents

- [Raw CSVs](#Raw-CSVs)

# Raw CSVs

This folder contains raw CSVs directly from scraping. These files were all merged together to create a raw and unclean dataframe.

| File Name                | Description                                    | Columns                                                                                   | Source                                   |
| ------------------------ | ---------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------- |
| `drivers_info.csv`       | Code and nationality for each driver           | `year`, `driver`, `driver_code`, `nationality`                                            | [Driver Standings (2024)](https://www.formula1.com/en/results/2024/drivers)
| `races_fastest_laps.csv` | Fastest lap for each race                      | `race_url`, `driver`, `fastest_lap`                                                       | [Fastest Laps (Bahrain 2024)](https://www.formula1.com/en/results/2024/races/1229/bahrain/fastest-laps)
| `races_pits.csv`         | Total pit stop count for each driver in a race | `race_url`, `driver`, `pit_count`                                                         | [Pit Stop Summary (Bahrain 2024)](https://www.formula1.com/en/results/2024/races/1229/bahrain/pit-stop-summary)
| `races_results_raw.csv`  | Finishing data for each driver in a race       | `race_url`, `end_position`, `driver`, `team_name`, `laps_completed`, `time_gap`, `points` | [Race Result (Bahrain 2024)](https://www.formula1.com/en/results/2024/races/1229/bahrain/race-result)
| `races_start.csv`        | Starting data for each driver in a race        | `race_url`, `start_position`, `driver`, `team_name`, `qualifying_time`                   | [Starting Grid (Bahrain 2024)](https://www.formula1.com/en/results/2024/races/1229/bahrain/starting-grid)
| `races_winner.csv`       | Winning driver data for each race              | `race_url`, `year`, `race`, `round`, `date`, `winner`, `team_name`, `laps`, `total_time`  | [Results (2024)](https://www.formula1.com/en/results/2024/races)

*Scraping was done for all races years 1950 - 2024*
