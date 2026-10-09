# Content Navigation

- **overview - Project overview**

- [data](data/README.md) - All datasets used in the project
  - [raw](data/raw/README.md) - Unprocessed scraped data
  - [intermediate](data/intermediate/README.md) - Merged or cleaned transitional data
  - [final](data/final/README.md) - Final datasets used for analysis
- [docs](docs/README.md) - Project proposal, final report, and presentation materials
- [notebooks](notebooks/README.md) - Jupyter Notebooks for scraping, cleaning, and analysis

# Page Contents

- [Project Overview](#Project-Overview)
- [Repository Contents](#Repository-Contents)
- [Data Overview](#Data-Overview)

# Project Overview

Formula 1 (F1) is a motorsport competition in which ten teams (constructors), each with two drivers, compete against each other in a series of races to earn points that determine individual and team standings.

The race winner receives the highest number of points while decreasing exponentially for lower finishing positions. These points are added to the driver’s individual total and their team’s total. After all the races are completed (~20), the driver with the most points wins the Drivers’ Championship, and the constructor with the most points wins the Constructors’ Championship.

Formula 1 is very dynamic. Drivers are constantly switching between teams, and old constructors are constantly being replaced by new ones. The competitive nature of F1 makes data analysis crucial for understanding performance trends, driver consistency, and team dominance. 

This project aims to compile and analyze historical F1 data to uncover performance trends among drivers and teams. By integrating data from multiple sources, this analysis will provide a comprehensive look at how driver and constructor performance has evolved.

# Repository Contents

This repository contains 3 main folders: data, docs, and notebooks.

| Folder      | Description                                                                                      | README                           |
| ----------- | ------------------------------------------------------------------------------------------------ | -------------------------------- |
| `data`      | Contains all raw, intermediate, and final CSV files used for machine learning and other analysis | [data](data/README.md)           |
| `docs`      | Contains proposal, check-in, and final report documents                                          | [docs](docs/README.md)           |
| `notebooks` | Contains the Jupyter Notebooks used for scraping, cleaning, and analysis                          | [notebooks](notebooks/README.md) |

# Data Overview

This project uses data scraped from the [Official Formula 1 Results Website](https://www.formula1.com/en/results/2025/races) for years 1950-2024. It combines race results, starting grid, fastest laps, pit stop summary, and driver information to create a comprehensive dataset. This is then cleaned and aggregated to yield a [final analysis dataset](data/final/f1_final.csv).

***Data dictionary** and other data information can be found in the the [data folder README](data/README.md)*
