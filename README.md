# Football Decision Value Analysis (xT)

A small Python project exploring on ball decision value in football using a simple Expected Threat (xT) grid.
The analysis pulls StatsBomb open event data for the Bundesliga 2023/24 season and estimates decision value for passes and carries as the change in xT from start to end location.

## What the notebook does
- Loads Bundesliga 2023/24 match list via `statsbombpy`
- Downloads event data for all matches in the season
- Filters actions to Pass and Carry events
- Extracts start and end coordinates from StatsBomb event fields
- Computes xT at start and end using a fixed 12 × 8 grid, then takes delta xT per action
- Aggregates player totals and plots involvement vs decision quality

## Output
The main output is a scatter plot saved as:
- `outputs/decision_quality_vs_involvement.png`

![Decision quality vs involvement](outputs/decision_quality_vs_involvement.png)

## How xT is computed
This project uses a predefined 12 × 8 xT grid and bins each action’s (x, y) locations into grid cells.
Decision value is:
- `xT(end) - xT(start)`

## How to run
1. Create an environment and install dependencies:
   `pip install -r requirements.txt`

2. Open and run the notebook:
   `notebooks/football_decision_value_xt.ipynb`

## Notes and limitations
- The xT grid is fixed and not learned from data in this repo
- Results depend on event definitions and coordinate quality
- The notebook downloads event data across the whole season, which can take a while

## Author
Ross Corcoran
