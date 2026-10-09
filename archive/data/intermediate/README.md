# Content Navigation

- [overview](../../README.md) - Project overview

- [data](../../data/README.md) - All datasets used in the project
  - [raw](../../data/raw/README.md) - Unprocessed scraped data
  - **intermediate - Merged or cleaned transitional data**
  - [final](../../data/final/README.md) - Final datasets used for analysis
- [docs](../../docs/README.md) - Project proposal, final report, and presentation materials
- [notebooks](../../notebooks/README.md) - Jupyter Notebooks for scraping, cleaning, and analysis

# Page Contents

- [Intermediate CSVs](#Intermediate-CSVs)

# Intermediate CSVs

This folder contains intermediate CSVs generated during the data processing phase — these files are typically cleaned, combined, or enriched versions of the raw data, used as inputs to further analysis.

| File Name                   | Description                                                                                                   | Columns                                      |
| --------------------------- | ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------|
| `drivers_info_with_pos.csv` | Driver ranks for each season, used to merge into the final analysis dataset                                   | `year`, `season_rank`, `driver`              |
| `races_results.csv`         | Raw end position split into end position and position status, used to merge into raw dataset                  | `race_url`, `raw_end_position`, `end_position`, `position_status`, `driver`, `team_name`, `laps_completed`, `time_gap`, `points` |
| `f1_races_raw.csv`          | Fully merged but unclean dataframe, merging winners, results, starts, fastest laps, pit info, and driver info | `race_url`, `raw_end_position`, `end_position`, `position_status`, `driver`, `team_name`, `laps_completed`, `time_gap`, `points`, `start_position`, `qualifying_time`, `pit_count`, `year`, `race`, `round`, `date`, `winner`, `winner_team_name`, `total_time`, `fastest_lap`, `driver_code`, `nationality` | 
