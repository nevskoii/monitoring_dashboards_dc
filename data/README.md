# Synthetic Data for Nexus Datacom Dashboards

This folder contains synthetically generated data for portfolio demonstration purposes. The data simulates real-world power consumption and commercial sales metrics across a large data center operator's infrastructure.

## Data Source

All data is generated programmatically using Python and loaded into a SQLite database (`nexus_datacom.db`). The raw CSV files are provided for reference and manual inspection.

## Files

| File | Description |
|------|-------------|
| `nexus_consumption.csv` | Actual power consumption by server hall |
| `nexus_commercial.csv` | Commercial power sales by server hall |

## Schema

### `nexus_consumption.csv`

| Column | Type | Description |
|--------|------|-------------|
| `dc` | string | Data center name (e.g., Apex-1, Forge-2, Core-3) |
| `hall` | string | Server hall name (e.g., Hall-01, Hall-02) |
| `project_power` | int | Projected / installed capacity (kW) |
| `fact_power` | int | Actual power consumption (kW) |

### `nexus_commercial.csv`

| Column | Type | Description |
|--------|------|-------------|
| `dc` | string | Data center name |
| `hall` | string | Server hall name |
| `project_power` | int | Projected / installed capacity (kW) |
| `comm_power` | int | Commercial power sold to customers (kW) |

## Key Metrics (from synthetic data)

| Metric | Value |
|--------|-------|
| Total data centers | 27 |
| Total server halls | 113 |
| Total projected capacity | 130 MW |
| Average utilization (fact/project) | 60% |
| Average sell-through (comm/project) | 108% |

## Data Characteristics

The data is designed to highlight realistic infrastructure patterns:

| Data Center Type | Load Range | Sales Range | Examples |
|------------------|------------|-------------|----------|
| **New DCs** | 15-35% | 25-45% | Apex-3, Apex-4 |
| **Medium DCs** | 50-75% | 75-100% | Apex-1, Apex-2 |
| **Moderate DCs** | 45-55% | 110-120% | Core, Cascade, Gateway, Harbor |
| **Legacy DCs** | 70-90% | 115-135% | Delta, Eclipse, Forge-1, Forge-3, Forge-4 |
| **Critical DC** | 85-220% | 170-220% | Forge-2 (unique overloaded location) |

## Edge Cases Included

- **Forge-2** (Anvil-02, Anvil-03, Anvil-05): Extreme overload (180-220% load, 200-240% sold)
- **Apex-3 / Apex-4**: New facilities with very low utilization (waiting for clients)
- **Mixed behavior**: Some legacy halls have normal load but high oversubscription

## Usage

### Load with Pandas

```python
import pandas as pd

# Load consumption data
df_consumption = pd.read_csv('data/nexus_consumption.csv')

# Load commercial data
df_commercial = pd.read_csv('data/nexus_commercial.csv')

# Calculate load percentage
df_consumption['load_pct'] = df_consumption['fact_power'] / df_consumption['project_power'] * 100

# Calculate sell-through percentage
df_commercial['sell_pct'] = df_commercial['comm_power'] / df_commercial['project_power'] * 100
