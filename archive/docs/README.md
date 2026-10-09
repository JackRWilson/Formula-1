# Content Navigation

- [overview](../README.md) - Project overview

- [data](../data/README.md) - All datasets used in the project
  - [raw](../data/raw/README.md) - Unprocessed scraped data
  - [intermediate](../data/intermediate/README.md) - Merged or cleaned transitional data
  - [final](../data/final/README.md) - Final datasets used for analysis
- **docs - Project proposal, final report, and presentation materials**
- [notebooks](../notebooks/README.md) - Jupyter Notebooks for scraping, cleaning, and analysis

# Page Contents

- [Docs Overview](#Docs-Overview)
- [Proposal / Check-in Challenges](#Proposal--Check-in-Challenges)

# Docs Overview

This folder contains the various documents used in the project.

| Folder                 | Description                                                                                                      |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `proposal.docx`        | Project proposal, scraping and data collection was changed following project check-in                            |
| `check_in_slides.pptx` | Slides used for project check-in, contains initial analysis, obsolete because data collection method was changed |
| `final_report.docx`    | Final project report                                                                                             |

# Proposal / Check-in Challenges

- The initial data collection approach involved scraping season-level results (i.e., final standings for all drivers in a season) and merging that data with a downloaded dataset containing driver nationalities and birthdates. However, the downloaded dataset was incomplete, resulting in many missing values after the merge.

- Because only final standings were scraped, the dataset included limited numerical features (driver position, driver points, team position, and team points). This restricted analysis and led to weak insights.

- To address these issues, results from individual races were scraped instead. This provided more numerical variables that could later be aggregated by season. Since nationality could also be scraped and years of experience could be calculated, the downloaded dataset was ultimately unnecessary, and all data collection was done solely through scraping.
