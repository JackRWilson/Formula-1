# Formula 1 Data Engineering and Analysis

This repository brings together Formula 1 race-data ingestion and prediction code with a separate driver-retention analysis. The long-term goal is to build a shared, repeatable data pipeline so that both analyses can use the same collected and standardized data.

The project is being reorganized. Some existing scripts still use import paths from the earlier layout, and dependency installation and Airflow orchestration are not fully configured yet. Treat the structure and run instructions below as a guide to the current project, not a claim that every workflow is production-ready.

## Project goals

- Collect Formula 1 race, driver, team, and session data from external sources.
- Clean and combine collected data into reusable datasets.
- Predict race outcomes and driver positions.
- Analyze driver retention across seasons.
- In the future, orchestrate repeatable pipeline runs with Apache Airflow.

## Repository layout

```text
.
├── archive/                 # Historical project material retained for reference
├── artifacts/               # Legacy reports, datasets, and notebooks; currently ignored by Git
├── configs/                 # Local configuration; do not commit secrets
├── dags/                    # Intended location for Airflow DAGs
├── data/
│   ├── raw/                 # Collected source data
│   ├── clean/               # Cleaned datasets
│   ├── intermediate/        # Joined or transitional datasets
│   ├── final/               # Analysis-ready prediction datasets
│   ├── successful/          # Scraper checkpoint/status files
│   └── cache/               # Local source-library cache
├── docker/airflow/          # Airflow image customization
├── docs/
│   ├── data-dictionary/     # Dataset and feature documentation
│   └── dev/                 # Working notes and development references
├── notebooks/               # Exploration, cleaning, and analysis notebooks
├── sql/                     # Database schema definitions
└── src/f1/
    ├── common/              # Helpers shared across project modules
    ├── ingestion/           # Source-specific data collection
    ├── pipeline/            # Pipeline entry point and run outputs/state
    ├── predictions/         # Race prediction code and model inputs
    ├── retention/           # Driver-retention analysis
    └── transformations/     # Cleaning, standardization, and joins
```

The existing data directories retain their current names for now. The `raw` → `clean` / `intermediate` → `final` flow is conceptually similar to the bronze/silver/gold pattern; a rename is not required to use that pattern.

## Data flow

The intended flow is:

1. **Ingest:** collect source data with modules in `src/f1/ingestion/`.
2. **Transform:** clean and join it with modules in `src/f1/transformations/`.
3. **Analyze:** build prediction and retention datasets and results for their respective use cases.

Today, the existing prediction workflow writes generated result CSV files and run state under `src/f1/pipeline/`. Those outputs are in a source-code directory and should eventually move to a dedicated output location. The retention analysis is still being integrated; shared ingestion and transformations for both use cases are a future goal.

The `data/` directory contains local datasets and may include large generated files. Check `.gitignore` and Git status before committing data; use external storage or a data-versioning solution for large datasets that need to be shared.

## Getting started

### Prerequisites

- Python installed locally.
- Git to clone the repository.
- Docker Desktop only if you plan to work on the future Airflow setup.

Python dependencies are not yet defined in a `requirements.txt` or `pyproject.toml`, so a fresh environment cannot currently install the complete project dependencies from a repository-managed manifest. Add and validate a dependency manifest before relying on these setup steps for a reproducible installation.

### Create a local virtual environment

From the repository root, on Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

On macOS or Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

The local `.venv/` is ignored by Git. Once a dependency manifest is added, install project dependencies from it (for example, `python -m pip install -r requirements.txt`).

## Running the project

The prediction pipeline entry point is `src/f1/pipeline/run_full_pipeline.py`. The existing scripts are still being adapted to the new package layout, so verify and update their imports before relying on a full run. Some prediction utilities also depend on Windows-specific Excel/COM packages, which will need consideration before those paths can run in Linux-based Airflow containers.

There is not yet a documented, automated test suite. Add tests for ingestion, transformations, and analysis logic as those modules are made independently runnable.

## Configuration and secrets

Use `.env.example` as a template for local environment variables. Copy it to a local `.env` file only when needed, set appropriate local values, and never commit credentials. The project currently has database-related example settings, but the database connection and deployment workflow are still being developed.

## SQL and database

SQL schema definitions belong under `sql/`, separate from the Python package. The current schema file is `sql/formula_1_schema.sql`. Keep database files and local database state outside version control; for a local SQLite database, use an ignored local-data directory rather than storing the database beside the schema.

## Airflow and Docker

`dags/` is reserved for Airflow DAG definitions, and `docker/airflow/Dockerfile` is the place to customize an Airflow image when project dependencies need to be installed in it. `compose.yaml` is a starting point, not yet a complete runnable Airflow environment. The intended design is for DAGs to invoke reusable functions from `src/f1/`, not to contain the scraping or analysis implementation themselves.

## Documentation

- [Retention analysis feature notes](docs/data-dictionary/retention-analysis.md) — descriptions of the fields documented for the earlier retention-analysis dataset. These need to be checked against the future shared data model.
- `artifacts/` currently contains legacy reports, datasets, and notebooks and is ignored by Git. Review its contents and decide which files should be retained in Git under `docs/`, `notebooks/`, or another appropriate location before relying on it as an archive.
