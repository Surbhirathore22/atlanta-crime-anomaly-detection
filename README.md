🔍 Anomaly Detection on Atlanta Crime Dataset
Tool: Kibana (Elastic Stack Machine Learning)
Internship: Appolo Computers Pvt Ltd · Jan–May 2024
Author: Surbhi Rathore · B.Tech, Banasthali Vidyapith · PGDM (2026)
---
📌 Overview:
This project performs anomaly detection on the Atlanta Crime Dataset using Kibana's built-in Machine Learning capabilities within the Elastic Stack. The goal was to automatically identify statistically significant spikes in crime activity across Atlanta's neighbourhoods — and assign each anomaly a severity score — enabling analysts to prioritise high-urgency incidents without manual data review.
---
🚨 Problem Statement:
Large urban crime datasets contain thousands of records across multiple neighbourhoods, crime types, and timeframes. Manual review is slow, inconsistent, and error-prone. This project automates the detection of unusual crime patterns and ranks them by urgency so that law enforcement and analysts can act on the most critical events first.
---
📂 Dataset:
Source: Atlanta Crime Dataset (provided during internship; originally sourced from Kaggle)
Column: Description
Crime; Type of offence (theft, burglary, assault, robbery, etc.)
Date: Date the crime occurred
Location: Street address of the incident
Beat: Police patrol zone where the crime occurred
Neighbourhood: District within Atlanta
Latitude: Geographic latitude of the crime location
Longitude: Geographic longitude of the crime location
---
⚙️ Methodology
Step 1 — Data Ingestion.
Uploaded the Atlanta Crime Dataset into Elasticsearch (the underlying data store for Kibana)
Created a Data View (Index Pattern) in Kibana to define how the data is indexed and queried.
Step 2 — Anomaly Detection Job Configuration.
Navigated to the Machine Learning section in Kibana and created a new anomaly detection job using the Multi-Metric Wizard — chosen because it allows simultaneous analysis of multiple crime metrics across the dataset.
Job settings configured:
Parameter	Choice	Reason
Job Type	Multi-Metric	Analyse multiple dimensions simultaneously
Detector	High Event Count	Detect sudden spikes in crime occurrences
Split Field	Neighbourhood	Segment analysis by neighbourhood for granular insight
Influencers	Neighbourhood, Crime	Identify which areas and crime types drive anomalies
Bucket Span	Auto-estimated	Based on data frequency and temporal granularity
Sparse Data	Enabled	Prevents false alarms from gaps in historical data
Step 3 — Anomaly Exploration
Results were analysed using Kibana's Anomaly Explorer, which visualises detected anomalies neighbourhood-by-neighbourhood.
Severity Scoring System:
Every detected anomaly is assigned an anomaly score reflecting its severity:
Score Range	Colour	Action Required
Low	🔵 Blue	Monitor — minor deviation
Medium	🟡 Yellow	Investigate — notable deviation
High	🔴 Red	Immediate action — critical spike
This colour-coded visual representation enables rapid triage without needing to read raw numbers.
Step 4 — Deep Dive Example
By clicking on a specific anomaly — a sudden crime spike in Mozley Park on September 28, 2010 — the system revealed:
Crime types involved: auto-theft, larceny (non-vehicle), aggravated assault
Normal crime rate in that area: ~1.4 incidents
Anomalous rate on that date: 5 incidents (a 3× increase)
This spike was flagged as a high-severity anomaly (red) requiring immediate attention
Step 5 — Forecasting
Using Kibana's Single Metric Viewer, forecasting was applied to predict future crime rates based on historical trends:
Generated a 2-week crime rate forecast for Mozley Park
Repeated forecasting for West End neighbourhood
The y-axis represents crime rate; the x-axis represents time
Predicted values are shown as a yellow band with hover-tooltip detail per data point
---
📊 Key Results
Successfully detected neighbourhood-level crime anomalies with severity scoring
Identified a 3× spike in Mozley Park crime activity (Sep 28, 2010) across 3 crime categories
Generated 2-week crime rate forecasts for multiple Atlanta neighbourhoods
Colour-coded severity system reduced analyst time-to-decision for high-urgency anomalies
---
💡 Key Learnings
Real-world anomaly detection requires careful configuration of bucket span and sparse data handling
Splitting by neighbourhood revealed localised crime patterns invisible in aggregate views
Visual severity scoring (blue → red) significantly accelerates analyst response prioritisation
Kibana's ML jobs are powerful for time-series and categorical data without requiring custom model code
---
🛠️ Skills Demonstrated
`Kibana` · `Elastic Stack` · `Anomaly Detection` · `Machine Learning (ML Jobs)` · `Data Visualisation` · `Time-Series Analysis` · `Risk Scoring` · `Forecasting` · `Statistical Analysis` · `Python` · `Crime Data Analysis`
---
📁 Repository Structure
```
atlanta-crime-anomaly-detection/
└── README.md
```
> 📝 \*\*Note on Screenshots:\*\* This project was executed on a private company server during my internship at Appolo Computers Pvt Ltd (Jan–May 2024). Screenshots are not included as the Kibana environment was restricted to internal company infrastructure. The complete methodology, configuration parameters, and results are fully documented above.
---
