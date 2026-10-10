# Retention Analysis Feature Notes

This documents the fields described for the earlier driver-retention analysis dataset. It is a starting point for an eventual data dictionary, not yet a verified schema for the current project or a specification of the future shared data model.

The legacy dataset was described as one row per driver-season, with aggregated season performance and an indicator of whether the driver was retained. Confirm the row grain, field definitions, null handling, and formulas against the dataset and analysis code before treating these definitions as authoritative.

| Column | Description | Type |
| --- | --- | --- |
| `year` | Season year | Numeric |
| `driver` | Driver name | Text |
| `team_name` | Constructor/team name | Text |
| `continent` | Driver's continent | Text |
| `season_rank` | Driver's final rank in the season | Numeric |
| `avg_start_pos` | Average starting position across the season | Numeric |
| `std_start_pos` | Standard deviation of starting positions | Numeric |
| `best_start_pos` | Best starting position | Numeric |
| `worst_start_pos` | Worst starting position | Numeric |
| `races_participated` | Number of races competed in | Numeric |
| `avg_finish_pos` | Average finishing position | Numeric |
| `std_finish_pos` | Standard deviation of finishing positions | Numeric |
| `best_finish_pos` | Best race finish | Numeric |
| `worst_finish_pos` | Worst race finish | Numeric |
| `total_pos_gain` | Total positions gained from start to finish across races | Numeric |
| `avg_pos_gain` | Average positions gained per race | Numeric |
| `total_points` | Total points scored | Numeric |
| `avg_points_per_race` | Average points scored per race | Numeric |
| `total_pct_season_points` | Percentage of available season points earned | Numeric |
| `avg_pct_season_points` | Average percentage of available points earned per race | Numeric |
| `worst_pct_season_points` | Lowest points percentage in a race | Numeric |
| `best_pct_season_points` | Highest points percentage in a race | Numeric |
| `total_laps_completed` | Number of laps completed | Numeric |
| `total_laps` | Total laps possible | Numeric |
| `total_fastest_laps` | Number of fastest laps earned | Numeric |
| `CLAS_total` | Number of classified finishes | Numeric |
| `DNF_total` | Number of did-not-finish results | Numeric |
| `DNS_total` | Number of did-not-start results | Numeric |
| `DQ_total` | Number of disqualifications | Numeric |
| `NC_total` | Number of not-classified results | Numeric |
| `backmarker` | Backmarker classification | Boolean |
| `midfield` | Midfield classification | Boolean |
| `podium_regular` | Podium-regular classification | Boolean |
| `points_regular` | Points-regular classification | Boolean |
| `years_experience` | Number of years the driver has competed | Numeric |
| `total_podium_finishes` | Number of podium finishes in the season | Numeric |
| `total_points_finishes` | Number of points finishes in the season | Numeric |
| `dnf_rate` | DNFs as a proportion of races entered | Numeric |
| `finish_rate` | Races finished as a proportion of races entered | Numeric |
| `lap_completion_rate` | Laps completed as a proportion of laps possible | Numeric |
| `fastest_lap_rate` | Fastest laps as a proportion of races entered | Numeric |
| `podium_rate` | Podium finishes as a proportion of races entered | Numeric |
| `points_rate` | Points finishes as a proportion of races entered | Numeric |
| `consistency_score` | Consistency in finish positions | Numeric |
| `qualifying_consistency` | Consistency in starting positions | Numeric |
| `reliability_score` | Measure based on finish rate and lap-completion rate | Numeric |
| `qualifying_vs_race` | Comparison of qualifying and finishing positions | Numeric |
| `championship_impact` | Measure of contribution to the championship outcome | Numeric |
| `race_improvement` | Average improvement from starting to finishing position | Numeric |
| `driver_retained` | Whether the driver was retained | Boolean |
