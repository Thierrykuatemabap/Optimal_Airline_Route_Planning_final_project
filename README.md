# African Airline Route Planning with Mathematical Optimisation

An academic Python project combining aviation data, network analysis, illustrative economic proxies and mixed-integer optimisation.

## Question and implementation

Which routes should be activated, and with what weekly frequencies, when route-level revenue, cost and connectivity are combined in an optimisation objective?

The [main notebook](Optimal_Airline_Route_Planning_final_project.ipynb) implements:

1. Airport and route data import, cleaning and selection of African routes.
2. Distance calculation and graph-based features, including degree and PageRank.
3. Demand, revenue and cost proxies.
4. A PuLP model with binary route activation and integer flight frequency.
5. Network plots and Folium visualisation.

The current optimisation block links frequency to route activation, caps each route at 30 flights, and enforces a mean hub-score constraint. Its objective combines a profit proxy with connectivity and hub bonuses. A shared fleet-capacity allocation model remains a future extension.

## Inputs

| Source | Use in the notebook |
| --- | --- |
| OpenFlights airport and route files | Airport locations, route endpoints and aircraft codes. |
| FAA aircraft data | Aircraft metadata. |
| avcodes aircraft table | Equipment-code enrichment. |
| Google Sheets aircraft-seat workbook | Estimated seating capacity. |

The exact URLs remain in the notebook. Imports depend on live remote files and web-page schemas; local versioned input snapshots have not yet been added.

## Environment

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter notebook
```

Open the main notebook from the repository root. PuLP also requires an available mixed-integer solver. Record the solver name and version when reproducing the model.

## Reproduction status

The exploratory cost helper has been corrected to use a numeric fixed-cost value and explicit aircraft-code lookup. An undefined diagnostic function call has been replaced with the defined helper. The helper was checked with small synthetic input tables; the entire notebook has not been rerun against its external data sources.

The saved notebook outputs are historical outputs, rather than a newly validated optimum. A fresh reproduction should record input versions, solver status, constraint feasibility and objective components before reporting an optimised network.

## Modelling assumptions

Demand, revenue and cost are illustrative proxies, rather than observed airline accounting data. The current model is useful for studying optimisation design and network features; conclusions depend on proxy definitions, coefficients and the implemented constraints.

Further work includes cached input datasets, sensitivity analysis, shared fleet and budget constraints, and comparisons with simple route-selection baselines.

## Academic context

AIMS Senegal numerical optimisation project, maintained in [Thierry Kuate Mabap's portfolio](https://github.com/Thierrykuatemabap).
