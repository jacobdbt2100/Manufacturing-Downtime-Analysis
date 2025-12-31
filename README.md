# Manufacturing Downtime Analysis
___

## Executive Summary:
Downtime caused 36% inefficiency, extending batch duration by 23 hours. Operator errors were the leading drivers. Five factors–mainly machine adjustments, machine failure, and inventory shortage amongst others–accounted for 80% of total downtime.

Based on these findings, I recommend targeted operator training, improved maintenance schedules, real-time inventory tracking, and high-downtime equipment upgrades to boost operational efficiency.

## Business Problem:
For manufacturing companies, downtime directly impacts output and profitability. In this soda bottling plant, management noticed frequent production delays but lacked clear insights into the main causes.

This analysis aimed to identify key drivers of downtime and propose actionable strategies to reduce operational disruptions.

## Methodology:
1. Extracted and cleaned downtime records from the production line excel file using Power Query.
2. Replaced "No" with *Non-Operator* and "Yes" with *Operator* in the "Operator Error" column of the "Downtime factors" table to ease reading the "Legend" in visuals.
3. Modelled data and performed detailed exploratory analysis using Power BI to quantify downtime distribution and identify critical drivers.
4. Visualized downtime data in Power BI to compare downtime contribution by operators, machine failure, and inventory shortages.

## Skills:
- Power Query: Data extraction & transformation, aggregation, unpivot
- Power BI: Data modelling, DAX measures, calculated columns, data visualization

## Insights & Recommendation:

1. **36% downtime inefficiency** extended batch duration by **23 hrs** (1,388 minutes) from a planned batch time of 41 hrs (2,470 minutes).
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/1_key metrics.jpg" width="800">

> - Reduce downtime to meet delivery schedules and protect customer trust and sales.

2. **Operators** extended batch time by **12% higher** than non-operator causes.
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/2_operator vs non-operator errors.jpg" width="450">

> - Provide **targeted operator training** and clear standard operating procedures (SOPs) to reduce errors.

3. Mac's downtime is mainly due to **batch changes**, while other operators struggle with **machine adjustments**.
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/3_process handling.jpg" width="700">

> - Prioritise batch change training for Mac and machine adjustment training for other operators.
  
4. Five factors caused **80% of downtime**; three (Machine adjustment, Batch change, and Batch coding) are linked to operator errors.
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/4_major causes.jpg" width="750">

> - Provide targeted training for operators on **Machine adjustment, Batch change, and Batch coding**.
> - Leverage preventive maintenance schedules to **minimize or predict machine failure**. Additionally, Upgrade or replace aging equipment with high downtime (need more data to ascertain age of equipment).
> - Implement real-time tracking systems or forecasting methods to maintain **optimal stock levels**.

5. **Mac's efficiency** is slightly **below the overall average** of all operators.
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/5_operators efficiency.jpg" width="300">

> - Provide Mac with focused coaching on batch changes to raise efficiency to peer level.

___

### `Additional Materials`

#### `Manufacturing Downtime Report:`
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/manufacturing downtime report.jpg" width="500">
[test]()

#### `Model View:`
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/model view.png " width="500">

#### `Line downtime table` transformation:

- **`before transformation`**
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table _ original.png" width="500">

- **`after unpivoting`**
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table _ unpivoted.png" width="500">

[Data set](https://mavenanalytics.io/data-playground/manufacturing-downtime)
