# NYC Yellow Taxi — Exploratory Data Analysis

## Project Overview

This project applies Exploratory Data Analysis (EDA) to a sample of 2023 New York City Yellow Taxi trip records. The objective is to uncover patterns that can help a taxi operation improve demand planning, cab positioning, dispatching, revenue generation and customer experience.

The analysis follows a business-oriented EDA workflow covering data preparation, data cleaning, temporal and financial analysis, geographic analysis, operational efficiency, pricing, tipping behaviour, passenger trends and surcharge patterns.

## Business Objective

The project aims to answer questions such as:

- When is taxi demand highest?
- Which pickup and drop-off zones have the greatest traffic?
- Where are potential pickup/drop-off imbalances?
- How does revenue vary across time?
- How does fare per mile change with trip distance?
- How do vendors differ in fare-per-mile performance?
- What factors are associated with tipping behaviour?
- How does passenger occupancy vary across time and zones?
- Where and when are surcharges applied most frequently?

## Dataset

The notebook uses a sample of NYC Yellow Taxi trip records supplied for the assignment.

The original sample loaded in the notebook contains **284,684 trip records and 22 columns**.

Important fields include:

- `VendorID` — technology provider
- `tpep_pickup_datetime` / `tpep_dropoff_datetime` — pickup and drop-off timestamps
- `passenger_count` — number of passengers
- `trip_distance` — trip distance in miles
- `PULocationID` / `DOLocationID` — pickup and drop-off taxi zones
- `payment_type` — payment method
- `fare_amount` — metered fare
- `tip_amount` — recorded tip
- `total_amount` — total passenger charge
- surcharge-related fields such as `extra`, `tolls_amount`, `improvement_surcharge`, `mta_tax`, `congestion_surcharge` and `airport_fee`

## Analysis Workflow

### 1. Data Preparation
- Imported the required Python libraries.
- Loaded the Parquet dataset.
- Inspected the dataset structure and variables.
- Distinguished categorical and numerical variables.

### 2. Data Cleaning
The notebook investigates missing values and potential outliers/inconsistencies, including:

- Missing passenger counts and other fields
- Invalid payment type values
- Passenger counts outside the expected range
- Extremely long trips
- Near-zero-distance trips with unusually high fares
- Zero-distance/zero-fare records with different pickup and drop-off zones

### 3. General EDA
The analysis explores:

- Pickup patterns by hour, day and month
- Revenue trends
- Quarterly revenue contribution
- Distance versus fare
- Fare and tips versus trip/passenger characteristics
- Payment-type distribution
- Taxi-zone geography and trip volumes

### 4. Detailed EDA
The notebook further analyses:

- Slow routes using average speed
- Hourly demand and peak periods
- Weekday versus weekend traffic
- High-traffic pickup and drop-off zones
- Pickup/drop-off ratios
- Night-time demand
- Day versus night revenue share
- Fare per mile by passenger count
- Fare per mile by hour and day
- Vendor-level fare performance
- Vendor pricing across distance tiers
- Tip percentages
- Passenger-count trends
- Passenger counts across zones
- Surcharge frequency by zone and time

## Selected Findings

### Peak Demand
The busiest overall pickup hour in the analysed sample is **6 PM**, with **20,222 sampled trips**.

For the weekday/weekend comparison:

- **Weekday peak:** 6 PM — 15,412 trips
- **Weekend peak:** 5 PM — 4,835 trips

This indicates that evening demand should receive particular attention when planning supply and dispatching.

### High-Traffic Zones
The highest-volume pickup zones include:

- Zone 132
- Zone 237
- Zone 161
- Zone 236
- Zone 162
- Zone 138

The highest-volume drop-off zones include:

- Zone 236
- Zone 237
- Zone 161
- Zone 230
- Zone 170

### Night-Time Demand
During the defined night window of 11 PM–5 AM, Zone 79 has the highest pickup count in the notebook's analysis, followed by Zones 132 and 249.

### Revenue: Day vs Night
The notebook reports:

- **Day revenue share:** 87.59%
- **Night revenue share:** 12.41%

This shows that most sampled revenue is generated during daytime/non-night hours, although night demand remains operationally important.

### Fare per Mile
Fare per mile is substantially higher for shorter trips and declines as trip distance increases.

For the distance-tier analysis:

| Distance Tier | Vendor 1 | Vendor 2 | Vendor 6 |
|---|---:|---:|---:|
| 0–2 miles | 9.76 | 17.93 | 30.16 |
| 2–5 miles | 6.38 | 6.53 | 7.00 |
| >5 miles | 4.41 | 4.49 | 4.05 |

### Tipping Behaviour
Average tip percentage decreases as trip distance increases:

- **0–2 miles:** 22.43%
- **2–5 miles:** 18.61%
- **>5 miles:** 16.45%

The notebook's low-tip/high-tip comparison also suggests that shorter trips are associated with higher tip percentages, while passenger count and average pickup hour are relatively similar between the two groups.

### Passenger Trends
Average passenger count is generally close to 1–2 passengers per trip.

Weekend averages are higher than weekday averages in the notebook:

- Saturday: **1.44**
- Sunday: **1.43**
- Tuesday: **1.30**

### Surcharges
Surcharge applications are concentrated in higher-traffic periods and zones. The notebook identifies **6 PM** as the peak hour for surcharge frequency and Zone **132** as the highest-frequency pickup zone.

## Business Recommendations

### Routing & Dispatching
1. Increase cab availability around the evening peak, particularly 5–7 PM.
2. Prioritize high-demand pickup zones when dispatching available vehicles.
3. Use separate positioning strategies for daytime peaks and night-time demand.
4. Use demand-based dispatching to reduce empty trips and improve vehicle utilization.
5. Combine time and location patterns when repositioning idle vehicles.

### Strategic Cab Positioning
1. Concentrate supply in consistently high-traffic zones during peak periods.
2. Shift availability toward high-demand night zones during 11 PM–5 AM.
3. Plan additional weekend capacity because average passenger counts are higher.
4. Use hourly and day-specific demand patterns instead of a single fixed positioning strategy.
5. Incorporate real-time demand signals where available.

### Pricing Strategy
1. Monitor short-trip pricing closely because fare-per-mile differs considerably between vendors.
2. Maintain competitive rates in the 2–5 mile segment, where vendor averages are relatively close.
3. Use competitive long-distance pricing because fare per mile falls substantially for longer trips.
4. Consider distance, demand, time and competitor pricing together when designing pricing policies.
5. Avoid excessive price increases when customers have readily available alternatives.

## Tools & Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly

## Repository Contents

```text
NYC_Taxi_EDA/
├── NYC_Taxi_EDA.ipynb
├── README.md
└── .gitignore
```

## Running the Notebook

The notebook was developed in Google Colab and currently loads the Parquet dataset from Google Drive.

The dataset itself is **not included in this repository**. To reproduce the analysis, place the required Parquet file in the expected Google Drive location or update the data-loading path in the notebook for your own environment.

## Portfolio Note

This project demonstrates an end-to-end EDA workflow: transforming raw trip records into operational insights and business recommendations. The emphasis is not only on producing charts and statistics, but on connecting demand, geography, pricing and customer behaviour to practical taxi-operations decisions.
