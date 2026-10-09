# Content Navigation

- [overview](../../README.md) - Project overview

- [data](../../data/README.md) - All datasets used in the project
  - [raw](../../data/raw/README.md) - Unprocessed scraped data
  - [intermediate](../../data/intermediate/README.md) - Merged or cleaned transitional data
  - **final - Final datasets used for analysis**
- [docs](../../docs/README.md) - Project proposal, final report, and presentation materials
- [notebooks](../../notebooks/README.md) - Jupyter Notebooks for scraping, cleaning, and analysis

# Page Contents

- [Final CSVs](#Final-CSVs)

# Final CSVs

This folder contains the clean and anlysis ready dataframes.

| File Name            | Description                                                                   | Columns                                      |
| -------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------|
| `f1_final.csv`       | Analysis ready dataframe, aggregated results for each driver in a year, includes engineered features and prediction columns | `year`, `driver`, `team_name`, `continent`, `season_rank`, `avg_start_pos`, `std_start_pos`, `best_start_pos`, `worst_start_pos`, `races_participated`, `avg_finish_pos`, `std_finish_pos`, `best_finish_pos`, `worst_finish_pos`, `total_pos_gain`, `avg_pos_gain`, `total_points`, `avg_points_per_race`, `total_pct_season_points`, `avg_pct_season_points`, `worst_pct_season_points`, `best_pct_season_points`, `total_laps_completed`, `total_laps`, `total_fastest_laps`, `CLAS_total`, `DNF_total`, `DNS_total`, `DQ_total`, `NC_total`, `backmarker`, `midfield`, `podium_regular`, `points_regular`, `years_experience`, `total_podium_finishes`, `total_points_finishes`, `dnf_rate`, `finish_rate`, `lap_completion_rate`, `fastest_lap_rate`, `podium_rate`, `points_rate`, `pct_season_points_per_race`, `consistency_score`, `qualifying_consistency`, `reliability_score`, `overtaking_efficiency`, `qualifying_vs_race`, `championship_impact`, `race_improvement`, `driver_retained` |
| `f1_races_clean.csv` | Clean dataframe that could be used for initial analysis, data on driver performance in each race, contains columns unnecessary for machine learning but necessary for manual use and ease of understanding | `year`, `date`, `round`, `race`, `driver`, `driver_code`, `nationality`, `continent`, `team_name`, `points`, `pct_season_points`, `raw_end_position`, `end_position`, `position_status`, `start_position`, `place_differential`, `qualifying_time`, `time_gap`, `laps_completed`, `pit_count`, `fastest_lap`, `winner`, `winner_team_name`, `laps`, `total_time`, `race_url` |

