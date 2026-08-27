# 🚕 NYC Yellow Taxi — Exploratory Data Analysis

## 📌 Project Overview

This project applies Exploratory Data Analysis (EDA) to 2023 New York City Yellow Taxi trip data to uncover patterns that can support better operational and business decisions.

The analysis focuses on **demand patterns, geographic activity, revenue, pricing, passenger behaviour, tipping and surcharge activity**, with the goal of translating data into practical recommendations for taxi operations.

The project follows an end-to-end EDA workflow covering data loading, data cleaning, exploratory analysis, visualisation, insight generation and business recommendations.

---

## 🎯 Business Objective

The analysis addresses how a taxi operation could use trip data to:

- Understand when and where demand is highest
- Improve cab positioning and dispatching
- Identify high-traffic pickup and drop-off zones
- Analyse revenue contribution across different time periods
- Compare fare behaviour across vendors and trip distances
- Understand passenger and tipping behaviour
- Identify patterns in surcharge applications
- Develop data-driven operational and pricing recommendations

---

## 🛠️ Tools & Technologies

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **GeoPandas**
- **Jupyter Notebook / Google Colab**
- **Parquet**

---

## 🔍 Analysis Performed

### 1. Data Preparation & Cleaning

The dataset was inspected and prepared for analysis, including handling data types, missing values and data-quality issues.

The analysis works with approximately **284,684 trip records** and includes variables covering vendors, pickup/drop-off timestamps, passenger counts, trip distance, taxi zones, fares, tips, tolls, taxes and other charges.

### 2. Temporal Demand Analysis

Trip activity was analysed across:

- Hours of the day
- Weekdays vs weekends
- Days of the week
- Night-time hours

### 3. Geographic Analysis

Pickup and drop-off activity was examined by NYC Taxi Zone to identify high-demand locations and operational hotspots.

### 4. Revenue & Pricing Analysis

The project analyses:

- Daytime vs nighttime revenue
- Fare per mile
- Fare behaviour by hour
- Vendor-level fare differences
- Fare per mile across distance tiers

### 5. Customer Behaviour

Passenger counts and tipping behaviour were analysed across:

- Trip distance
- Passenger count
- Pickup hour
- Day of the week

### 6. Surcharge Analysis

The frequency of different surcharge components was analysed by:

- Pickup zone
- Drop-off zone
- Pickup hour

---

# 📊 Key Findings

### ⏰ Demand Peaks

The busiest **weekday pickup hour was 18:00**, with **15,412 trips**.

The busiest **weekend pickup hour was 17:00**, with **4,835 trips**.

**Business implication:** Fleet availability should be strengthened around the late-afternoon and early-evening demand window.

---

### 🌙 Daytime vs Nighttime Revenue

| Time Period | Revenue | Revenue Share |
|---|---:|---:|
| Day | $7,196,305.45 | **87.59%** |
| Night | $1,019,946.97 | **12.41%** |

Daytime trips therefore account for the majority of the analysed revenue.

**Business implication:** The largest portion of fleet capacity should be aligned with daytime and evening demand, while nighttime deployment should remain targeted toward identified hotspots.

---

### 🌃 Night-Time Demand Hotspots

During the analysed night period of **11 PM–5 AM**, the highest pickup activity was concentrated in:

- Zone 79 — 2,478 pickups
- Zone 132 — 2,199
- Zone 249 — 2,015
- Zone 48 — 1,593
- Zone 148 — 1,548

The leading nighttime drop-off zones included **79, 48, 170, 68 and 107**.

**Business implication:** Nighttime fleet positioning can be concentrated around these recurring demand locations instead of distributing vehicles uniformly across the city.

---

### 💰 Distance & Fare Behaviour

Fare per mile decreases substantially as trip distance increases.

| Distance Tier | Vendor 1 | Vendor 2 | Vendor 6 |
|---|---:|---:|---:|
| 0–2 miles | 9.76 | 17.92 | 30.16 |
| 2–5 miles | 6.38 | 6.53 | 7.00 |
| >5 miles | 4.41 | 4.49 | 4.05 |

The strongest vendor differences occur for short trips, while fares per mile become much closer for longer journeys.

**Business implication:** Pricing decisions should consider trip distance rather than relying on a single uniform fare-per-mile assumption.

---

### 💵 Tipping Behaviour

Average tip percentage declined as trip distance increased:

| Distance | Average Tip |
|---|---:|
| 0–2 miles | **22.44%** |
| 2–5 miles | **18.61%** |
| >5 miles | **16.45%** |

Tip percentages also varied by passenger count and pickup hour. The highest hourly average in the analysis occurred around **18:00 at 22.07%**, while the lowest was around **05:00 at 16.96%**.

---

### 👥 Passenger Behaviour

Average passenger counts were higher on weekends:

- Saturday — **1.44**
- Sunday — **1.43**
- Friday — **1.38**

The lowest daily average was observed on Tuesday at **1.30**.

**Business implication:** Weekend demand may justify slightly different fleet planning because trips tend to carry more passengers on average.

---

### 🧾 Surcharge Patterns

Surcharge activity was concentrated in the afternoon and evening, with the highest frequency occurring around **6 PM**, followed by **5 PM and 7 PM**.

The highest surcharge-frequency pickup zones included **132, 161, 237, 236 and 138**, while major drop-off locations included **236, 237 and 161**.

**Business implication:** Surcharge activity provides another operational indicator for identifying periods and locations of concentrated taxi activity.

---

# 💡 Business Recommendations

### 1. Demand-Based Fleet Positioning

Increase cab availability around the **5 PM–7 PM** peak, with particular attention to the 6 PM weekday peak.

### 2. Zone-Based Dispatching

Prioritise high-demand zones such as **132, 161, 237, 236 and 138** when allocating available vehicles.

### 3. Targeted Night Operations

During nighttime hours, strategically position vehicles around zones such as **79, 132, 249, 48 and 148**.

### 4. Proactive Dispatching

Use both **time and location** when making dispatch decisions so vehicles can be moved toward areas where demand is expected to increase.

### 5. Distance-Aware Pricing

Use trip-distance patterns when evaluating pricing, particularly because short trips show considerably higher fare-per-mile values than longer trips.

### 6. Reduce Empty Trips

Use demand-based dispatching to improve vehicle utilisation and reduce unnecessary empty movement between trips.

---

# 📁 Repository Structure

```text
nyc-taxi-eda/
│
├── NYC_Taxi_EDA.ipynb
├── README.md
└── gitignore
```

---

# ▶️ Running the Notebook

The notebook was developed and tested in **Google Colab**.

The raw Parquet dataset is **not included in this repository**. When running the notebook in Google Colab, the required dataset can be supplied through Google Drive. The data-loading configuration can also be adapted for another environment.

This approach keeps the repository focused on the analytical workflow and avoids storing the raw dataset directly in GitHub.

---

# 📌 Portfolio Note

This project demonstrates an end-to-end **Exploratory Data Analysis workflow**, moving from raw taxi trip records to operational insights and business recommendations.

The emphasis is not only on statistical analysis and visualisation, but also on connecting **demand, geography, pricing, revenue and customer behaviour** to practical decisions around fleet positioning, dispatching and pricing.
