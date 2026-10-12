# Data Centre Power & Sales Monitoring

**Interactive analytics project** — Python, Pandas, SQLite and Plotly.

**[View the live project](https://nevskoii.github.io/monitoring_dashboards_dc/)** · [Power Consumption Treemap](https://nevskoii.github.io/monitoring_dashboards_dc/heatmap_consumption.html) · [Sales Risk Treemap](https://nevskoii.github.io/monitoring_dashboards_dc/heatmap_sales.html)

## Business objective

Monitor data centre power consumption and commercial sales commitments at the server-hall level. Present operational and commercial capacity indicators in a consistent hierarchy so that overloaded and underutilised locations can be identified without manually reviewing each hall.

## Scope

| Metric | Value |
|---|---:|
| Data centres | 27 |
| Server halls | 113 |
| Projected capacity | 130 MW |
| Actual consumption | 78 MW |
| Average power utilisation | 60% |
| Sold power commitments | 140 MW |
| Average sell-through | 108% |

## Dashboards

### 1. Power Consumption

Interactive Plotly treemap of actual versus projected power capacity. Users can drill down from data centre to server hall and compare consumption ratios. Colour thresholds distinguish normal operation, attention, high load and overload.

**[Open Power Consumption](https://nevskoii.github.io/monitoring_dashboards_dc/heatmap_consumption.html)**

### 2. Colocation Sales Risk

Interactive Plotly treemap of sold power commitments relative to available capacity. The view highlights capacity overselling, elevated sales exposure and underutilised facilities.

**[Open Sales Risk](https://nevskoii.github.io/monitoring_dashboards_dc/heatmap_sales.html)**

## Selected findings

- Some facilities have hall-level consumption or sold commitments above nominal capacity, indicating locations for targeted review.
- Other halls show low utilisation, highlighting potential commercial capacity for further analysis.
- Treemap drill-down connects a network-wide view with individual hall indicators.

These are observations from the demonstration dataset, not claims about a named employer's current infrastructure.

## Implementation

- **Python / Pandas:** data processing and preparation
- **SQLite:** structured project dataset
- **Plotly:** interactive hierarchical treemaps
- **Jupyter Notebook:** reproducible dashboard generation
- **GitHub Pages:** static hosting of exported interactive HTML

## Repository contents

| File | Purpose |
|---|---|
| [index.html](index.html) | Portfolio-ready project landing page |
| [heatmap_consumption.html](heatmap_consumption.html) | Original interactive consumption treemap |
| [heatmap_sales.html](heatmap_sales.html) | Original interactive sales treemap |
| [Power_Monitoring_Dashboard.ipynb](Power_Monitoring_Dashboard.ipynb) | Python analysis and visualisation notebook |
| [data/](data/) | Demonstration data and data notes |

## Author

Aleksandr Korshunov · [Professional portfolio](https://nevskoii.github.io/career-portfolio/) · [LinkedIn](https://www.linkedin.com/in/askorshunovv)
