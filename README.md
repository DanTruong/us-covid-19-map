# U.S. COVID-19 Map

An interactive map of reported COVID-19 cases and deaths across the United States, built in Tableau using historical CDC data. This project adapts an earlier R Shiny application to explore Tableau's mapping, filtering, and dashboard capabilities.

## Tableau Version

The Tableau workbook displays one circle per state, sized by the total reported cases or deaths within a selected date range. Users can adjust the date range, switch between cases and deaths, and hover over states to view their totals.

Open [`tableau/us-covid-19-map.twbx`](tableau/us-covid-19-map.twbx) in Tableau. The packaged workbook includes its data, so R and a separate data download are not required to explore the map.

## Original R Shiny Version

The original application is preserved in [`r/`](r/). It uses R to retrieve and reshape CDC data, Leaflet to display the interactive map, and Shiny to provide date and metric controls alongside a searchable data table.

With the required R packages installed, run this command from the repository root:

```r
shiny::runApp("r")
```

The original API download code is retained in `r/global.R` but is commented out. The application currently uses its bundled CSV.

## Data

The bundled snapshot covers **January 22, 2020–February 9, 2021**, across the 50 states. It was sourced from the CDC's *United States COVID-19 Cases and Deaths by State over Time* dataset (`9mfq-cb36`).

Cases and deaths represent daily reported counts; the map sums these over the selected period. Cases do not represent currently active infections. Negative daily values are retained as reporting corrections, so displayed totals are net reported counts.

## Repository Contents

- `tableau/` — Tableau packaged workbook.
- `r/` — Original R Shiny application and its supporting files.
- `data/` — Shared data files.
