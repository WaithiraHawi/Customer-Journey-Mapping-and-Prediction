# Customer Journey & Retention Analysis

## Overview

This project analyzes the **customer journey** from first interaction to purchase, and measures **retention** over time using cohort tracking.
The dataset (`TravelData.csv`) contains \~2.45 million user interactions, including device type, timestamps, and purchase activity.

<img width="1024" height="1536" alt="Customer retention" src="https://github.com/user-attachments/assets/bc79312f-a4a7-4ec4-bdd3-5a8610f2bbb6" />

The analysis focuses on:

1. Understanding **user behavior patterns** across devices and time.
2. Mapping the **conversion funnel** from engagement → purchase.
3. Measuring **customer retention** using monthly cohorts.
4. Visualizing retention trends for different **device types**.


## Dataset

| Column         | Description                                    |
| -------------- | ---------------------------------------------- |
| `UserID`       | Unique identifier for each user                |
| `PurchaseID`   | Unique identifier for each purchase event      |
| `TIMESPSS`     | Timestamp of the event                         |
| `Duration`     | Session duration (minutes)                     |
| `DEVICE_TYPE`  | Device used (`MOBILE` or `FIXED`)              |
| `type_touch`   | Interaction type code                          |
| `purchase_own` | Purchase of user’s own travel package (binary) |
| `purchase_any` | Any purchase (binary)                          |
| `MobilePanel`  | Mobile panel interaction flag                  |
| `FixedPanel`   | Fixed panel interaction flag                   |


## Analysis Steps

### Data Preprocessing

* Converted timestamps to `datetime`.
* Extracted **date**, **hour**, **day of week**, and **month** for time-based insights.
* Cleaned missing values and standardized formats.

### Descriptive Statistics

* **Total Users:** 9,678
* **Total Purchases:** 29,012
* **Total Interactions:** 2.45M
* **Avg Session Duration:** \~56 min
* **Device Usage:** \~81% FIXED, 19% MOBILE
* **Any Purchase Rate:** \~34.6%
* **Own Purchase Rate:** \~3.3%

### Customer Journey Funnel

Stages:

1. **Interactions** – Any recorded activity.
2. **Any Purchase** – At least one purchase made.
3. **Own Purchase** – Purchase of the user’s own travel package.

**Insight:**
While over a third of interactions lead to *any* purchase, only \~3% convert to *own purchase*.

### Behavioral Trends

* **Device Patterns:** FIXED devices dominate interaction volume, but MOBILE users show slightly higher purchase rates.
* **Weekly Cycle:** Engagement peaks mid-week and dips on weekends.
* **Session Duration:** Longer sessions are slightly more likely to end in purchase.

### Retention & Cohort Tracking

I created **monthly cohorts** based on each user’s **first activity month**.

**Steps:**

* Assigned each user to a **Cohort Month**.
* Calculated **Cohort Index** = months since first activity.
* Measured the % of cohort users returning in subsequent months.

### Retention Heatmap

* Rows = Cohort Month (first activity)
* Columns = Months since signup
* Values = % of users active in that month

**Observation:**
Typical drop-off is **>50% after the first month**. Retention stabilizes after Month 3.

### Device-Specific Retention

* **MOBILE** users have higher short-term retention but steeper decline later.
* **FIXED** users churn faster initially but have steadier long-term engagement.

### Cohort Size Tracking

Visualized **new user acquisition** over time:
Growth spikes in certain months likely tied to campaigns or seasonal trends.

## Visuals

* **Device Usage Distribution**
* **Interactions by Day of Week**
* **Funnel Conversion Chart**
* **Retention Heatmap**
* **Average Retention Curve**
* **Device-Specific Retention Curves**
* **Cohort Size Chart**

## Tools Used

* **Python**: Data analysis & visualization
* **Pandas**: Data manipulation
* **Matplotlib & Seaborn**: Charting
* **Cohort Analysis Techniques**: Retention tracking & funnel analysis

## Recommendations

1. **Improve Onboarding:** Steep drop-off after Month 1 suggests weak early engagement.
2. **Mobile Optimization:** High short-term retention could be leveraged with push campaigns.
3. **Conversion Funnel Focus:** Address the big drop from *any purchase* to *own purchase*.
4. **Seasonal Promotions:** Target months with historically low cohort sizes to smooth growth.
