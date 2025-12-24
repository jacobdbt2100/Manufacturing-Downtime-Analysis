# Manufacturing Downtime Analysis
___

## Executive Summary:
I analysed soda bottling production line data and found that downtime caused 36% inefficiency, extending batch duration by 23 hours. Operator errors were the leading drivers. Five factors–mainly machine adjustments, machine failure, and inventory shortage amongst others–accounted for 80% of total downtime.

Base on these findings, I recommend targeted operator training, improved maintenance schedules, real-time inventory tracking, and high-downtime equipment upgrades to boost operational efficiency.

## Business Problem:
For manufacturing companies, downtime directly impacts output and profitability. In this soda bottling plant, management noticed frequent production delays but lacked clear insights into the main causes.

This analysis aimed to identify key drivers of downtime and propose actionable strategies to reduce operational disruptions.

## Methodology:
1. Extracted and cleaned downtime records from the production line excel file using Power Query.
2. Modelled data and performed detailed exploratory analysis using Power BI to quantify downtime distribution and identify critical drivers.
3. Visualized downtime data in Power BI to compare downtime contribution by operators, machine failure, and inventory shortages.

## Skills:
- Power Query: Data extraction & transformation, aggregation, unpivot
- Power BI: Data modelling, DAX measures, calculated columns, data visualization

## Insights & Recommendation:
### 1. Downtime causes significant delays, extending batch duration by 23 hours.
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/1_key metrics.jpg" width="800">

> 36% downtime inefficiency extended batch duration by 23 hrs (1388 minutes) from a planned batch time of 41 hrs (2470 minutes).
- *Reduce downtime to meet delivery schedules and protect customer trust and sales.*

### 2. Operator-related issues are the leading cause of downtime.
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/2_operator vs non-operator errors.jpg" width="450">

> Operators extended batch time by 12% higher than non-operator causes.
- *Provide targeted operator training and clear standard operating procedures (SOPs) to reduce errors.*

### 3. Downtime causes vary significantly across operators.
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/3_process handling.jpg" width="700">

> Mac's downtime is mainly due to batch changes, while other operators struggle with machine adjustments.
- *Prioritize batch change training for Mac and machine adjustment training for other operators.*
  
### 4. A few key factors account for most downtime.
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/4_major causes.jpg" width="750">

> Five factors caused 80% of downtime; three are linked to operator errors.
- **Machine adjustment, Batch change, and Batch coding**: *Provide targeted training for operators.*
- **Machine Failure**: *Leverage preventive maintenance schedules to minimize or predict machine failure. Additionally, Upgrade or replace aging equipment with high downtime (need more data to ascertain age of equipment).*
- **Inventory Shortage**: *Implement real-time tracking systems or forecasting methods to maintain optimal stock levels.*

### 5. Operator efficiency shows slight performance differences.
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/5_operators efficiency.jpg" width="300">

> Mac's efficiency is slightly below the overall average of all operators.
- *Provide Mac with focused coaching on batch changes to raise efficiency to peer level.*

___

### `Additional Materials`

#### `Manufacturing Downtime Report:`
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/manufacturing downtime report.jpg" width="500">

#### `Model View:`
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/model view.png " width="500">

#### `Line downtime table` Transformation:

- **`before transformation`**
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table _ original.png" width="500">

- **`after unpivoting`**
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table _ unpivoted.png" width="500">

[Data set](https://mavenanalytics.io/data-playground/manufacturing-downtime)
