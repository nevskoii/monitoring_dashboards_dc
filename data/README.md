# Synthetic Data for Nexus Datacom Dashboards

This folder contains synthetically generated data for portfolio demonstration purposes.

## Files

| File | Description |
|------|-------------|
| `nexus_consumption.csv` | Actual power consumption by server hall |
| `nexus_commercial.csv` | Commercial power sales by server hall |

## Schema

### nexus_consumption.csv
| Column | Type | Description |
|--------|------|-------------|
| dc | string | Data center name |
| hall | string | Server hall name |
| project_power | int | Projected capacity (kW) |
| fact_power | int | Actual power consumption (kW) |

### nexus_commercial.csv
| Column | Type | Description |
|--------|------|-------------|
| dc | string | Data center name |
| hall | string | Server hall name |
| project_power | int | Projected capacity (kW) |
| comm_power | int | Commercial power sold (kW) |

## Notes

- Data is 100% synthetic and created for portfolio purposes only
- Realistic ranges: 50-2500 kW per hall, 25 data centers, 150+ halls
- Includes edge cases (overloaded halls at Forge-2, underutilized at Apex-3/4)
