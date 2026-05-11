# Gas Production Downtime Analysis

![](https://github.com/oluwagbemiga01/Gas-production-downtime-analysis/blob/main/gas%20industry.png)

This project analyzes upstream gas production performance across multiple oil and gas fields, focusing on operational uptime, production trends, deferred production losses, and shutdown causes.  The dashboard was developed to support operational decision making.

## Business Problem
Production interruptions and operational downtime can significantly reduce gas output and affect field reliability.

This project aims to identify the primary causes of downtime, measure production deferment impact, and monitor production performance across wells and assets.

## Objectives
- Monitor total gas production performance
- Analyze downtime trends and uptime efficiency
- Identify major shutdown causes
- Track deferred production losses
- Evaluate best-performing wells
- Support operational optimization decisions

## Dataset Description
| Variables        | Description |
|:----------------:| :------------:|
| Oil Fields       | Producing gas fields |
| Wells            | Individual production wells |
| Production Volume| Gas output in MMSCFD |
| Downtime Hours   | Operational downtime duration |
| Shutdown Cause   | Cause of operational interruption |
Deferred Production| Lost production volume |

## Key KPIs
| KPI             | Value    |
|:--------------: |:---------|
|Total Production	| 2.32M MMSCFD |
|Avg Uptime Rate	| 70% |
|Deferred Production|	0.69M MMSCFD|
|Total Downtime	|217,365 Hours |

## Key Insights
### Operational Insights
- Production performance fluctuated significantly across the analysis period.
- Maintenance-related shutdowns were the largest contributor to downtime events.
- Deferred production accounted for 23% of potential output.
- A small group of wells contributed most of the total production volume.
- Uptime performance remained below optimal operational targets.

## Business Recommendations
- Increase preventive maintenance scheduling to reduce reactive shutdowns.
- Prioritize monitoring of high-producing wells.
- Improve root-cause tracking for unspecified shutdown events.
- Investigate recurring pipeline leak incidents.
- Implement downtime reduction initiatives to improve uptime reliability.

## Data Cleaning and Transformation
- I handled missing values of numerical values like : production volume, water cut etc. using Median Imputation
- Some numerical values had categorical values in them (e.g 1080bopd), i had to remove them to ensure consistency of the data
- Some categorical values from *Downtime cause* variable had missing values, I renamed those values as "Unspecified" because I was not sure of the main cause of downtime.

## Data Modelling
- A star schema data model was implemented to improve dashboard performance, maintain data integrity, and support scalable analytical reporting.

The model consists of a central fact table containing production and downtime metrics, connected to multiple dimension tables describing well unit type, and date table.

This modelling approach enabled efficient filtering, simplified DAX calculations, and improved overall report usability.

### Fact Table
The central fact table stores measurable operational data, including:

- Gas Production Volume (MMSCFD)
- Downtime Hours
- Deferred Production
- Uptime Metrics

### Relationship Structure

One to many relationships were established between dimension tables and the fact table to ensure accurate aggregation and filtering across the dashboard.

![Data Model Diagram](https://github.com/oluwagbemiga01/Gas-production-downtime-analysis/blob/main/Model%20screenshot.png)
