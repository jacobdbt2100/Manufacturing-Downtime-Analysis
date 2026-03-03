# Manufacturing Downtime Analysis
___

## Executive Summary:
Downtime caused **36% inefficiency**, extending batch duration by **23 hours (1,388 minutes)** beyond the planned **41 hours**, increasing delivery risk. Operator-related issues drove downtime **12% higher** than non-operator causes, with **five factors accounting for 80% of total downtime**, three (**Machine adjustment, Batch change, Batch coding**) linked to operator error. Mac’s downtime is mainly driven by batch changes, while other operators struggle more with machine adjustments, leaving Mac’s efficiency slightly below the team average.

I recommend targeted operator training on high-impact error drivers, focused coaching for Mac on batch changes, strengthened preventive maintenance for high-downtime equipment, and real-time tracking to protect delivery schedules and stock levels.

## Business Problem:
For manufacturing companies, downtime directly impacts output and profitability. In this soda bottling plant, management noticed frequent production delays but lacked clear insights into the main causes.

This analysis aimed to identify key drivers of downtime and propose actionable strategies to reduce operational disruptions.

## Methodology:
1. Extracted and cleaned downtime records from the production line excel file using Power Query.
2. Replaced "No" with *Non-Operator* and "Yes" with *Operator* in the "Operator Error" column of the "Downtime factors" table to ease reading the "Legend" in visuals.
3. Modelled data and performed detailed exploratory analysis using Power BI to quantify downtime distribution and identify critical drivers.
4. Visualized downtime data in Power BI to compare downtime contribution by operators, machine failure, and inventory shortages.

## Insights & Recommendations:

<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/manufacturing downtime report.jpg" width="1000">
___

### Miscellaneous:

#### Model View
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/model view.png " width="500">

#### `Line downtime table` transformation

- **raw** `Line downtime table`
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table _ original.png" width="500">

- `Line downtime table` **after unpivoting**
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table _ unpivoted.png" width="500">

[Data set](https://mavenanalytics.io/data-playground/manufacturing-downtime)
