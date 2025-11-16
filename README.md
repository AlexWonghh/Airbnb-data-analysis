# Airbnb-data-analysis

## Project Title and Overview

**Project Title:** *Unlocking the Secrets of Singapore Airbnb Market for GoTrip*  
**Team:** Group Eggplant (Alex Ng, Alex Wong, Camen Ho, Yuki Chow)

This project is a final project for Junior Data Analyst Programme organized by Generation Hong Kong, which analyzes **Singapore’s short-term rental market** using **June 2025 Airbnb public data (~3,600 listings)** and **11.62 million inbound tourist arrivals (Jan–Aug 2025)**. The goal is to support **GoTrip**, an Online Travel Agent (OTA), in:

1. Identifying **market gaps** for strategic entry into Singapore.
2. **Maximizing revenue** through optimized pricing, positioning, and host partnerships.

> The **Junior Data Analyst Programme Final Project** by *Generation: You Employed, Inc.*

---

## Problem Statement / Business Question

GoTrip seeks to compete with Airbnb in Singapore. Key business questions addressed:

1. **Demand & Supply Trends** – *Which neighborhoods and property types are most in demand?*
2. **Pricing Optimization** – *How should hosts price listings to maximize occupancy and revenue?*
3. **Competitive Positioning** – *Where are the gaps in the market that GoTrip can exploit?*

---

## Data Sources

| Source | Description |
|-------|-------------|
| **[Inside Airbnb – Singapore (June 2025)](http://insideairbnb.com/get-the-data.html)** | Core dataset: ~3,600 listings with details on price, room type, location, occupancy, reviews |
| **Singapore Tourism Board (STB)** | Inbound tourist arrivals: **11.62M (Jan–Aug 2025)** |
| **Google Maps API** | Calculated **distance from listings to major attractions** (e.g., Chinatown, Gardens by the Bay) |
| **HDB Resale Price Index (2024)** | Contextual housing cost data for neighborhood pricing benchmarks |

---

## Tools and Technologies

| Category | Tools |
|---------|-------|
| **Programming** | Python 3.11 |
| **Libraries** | `pandas`, `numpy`,`matplotlib.pyplot`, `seaborn` |
| **Database** | PostgreSQL |
| **Data Pipeline** | Python scripts + SQL ETL |
| **Visualization** | **Power BI** (GeoJSON maps, slicers, forecasting) |
| **Modeling** | Linear Regression, KNN, Random Forest, XGBoost |
| **Presentation** | Microsoft PowerPoint (34 slides) |

---

## Methodology / Analysis Steps

### 1. **Data Cleaning and Preprocessing**
- Removed duplicates and irrelevant columns
- Handled missing/inconsistent values in `bedrooms`, `bathrooms`, `price`
- Converted `price` to numeric (removed `$`, commas)
- Standardized `room_type` and `neighbourhood_cleansed`
- Calculated **distance to nearest attraction** using Google Maps API

### 2. **Exploratory Data Analysis (EDA)**
- Analyzed **supply-demand ratio** by neighborhood
- Explored **proximity impact** on price and occupancy
- Segmented listings by **room type**, **price tier**, and **tourist footfall**
- Calculated **Herfindahl-Hirschman Index (HHI)** to assess host market concentration

### 3. **Modeling**
- **Objective:** Predict optimal listing price
- **Target Variable:** `price`
- **Features:** `room_type`, `bedrooms`, `bathrooms`, `accommodates`, `neighbourhood`, `distance_to_attraction`
- **Models Compared:**
  - Linear Regression
  - KNN Regressor
  - Random Forest Regressor
  - **XGBoost Regressor** (Best: **R² = 0.87**)

### 4. **Data Analysis**
- **Supply-Demand Imbalance:** Marina South (13.9%), Singapore River (8.8%)
- **Proximity Effect:** Listings **<1 km from Chinatown** → **+37.2% occupancy**
- **Revenue Leaders:** Entire Home/Apt = **66.2% of total revenue**

---

## Results and Insights

### Key Findings

| Insight | Data Point |
|-------|------------|
| **Top Demand Areas** | Marina South, Singapore River, Punggol |
| **Proximity Premium** | <1 km to Chinatown → **+37.2% occupancy**, **+6.95% price** |
| **Room Type Dominance** | **Entire Home/Apt**: 66.2% revenue, 48.5% bookings |
| **Price Sensitivity** | **50% of high-price bookings ($271+)**, but has relatively low supply ratio |
| **Market Concentration** | High HHI in Marina South → opportunity for **monopoly host partnerships** |

### Visualizations (Power BI Dashboard)

- **Supply-Demand bar chart** by neighborhood  
   <img width="1266" height="695" alt="image" src="https://github.com/user-attachments/assets/88d97f26-2eb9-4139-86f0-c473e2c02a57" />

  
- **Price distribution in Singapore**  
  <img width="1275" height="712" alt="image" src="https://github.com/user-attachments/assets/16c8341e-5aad-4c31-ab95-95c1b1f36137" />

- **Price Optimization**  
  <img width="1251" height="614" alt="image" src="https://github.com/user-attachments/assets/c577076d-aacf-46e6-b0a6-b6e4154f165d" />






---

## Recommendations

| Recommendation | Action |
|---------------|--------|
| **1. Value Stay Labels** | Tag listings **1–2 km from new attractions** (e.g., Punggol Digital District) for search filters and themed pages |
| **2. Target Listing Criteria** | Prioritize **Entire Home/Apt**, **medium high pricing($157-270), high-range pricing ($271 above)**, target to **high HHI location** |
| **3. Partnership Strategy** | <br>• **High HHI hosts**: Co-marketing, guaranteed supply <br>• **Low HHI hosts**: Competitive pricing, bulk onboarding |

---

## Future Work / Improvements

- Integrate **real-time booking data** from GoTrip platform
- Build **dynamic pricing engine** using XGBoost model
- Expand to **Bangkok, Hong Kong, Tokyo** using same framework
- Add **sentiment analysis** on guest reviews
- Develop **seasonal supply and demand observation** (If dataset includes booking days)

---

## Acknowledgments / References

- **[Inside Airbnb](http://insideairbnb.com/)** – Open dataset provider
- **Singapore Tourism Board** – Official visitor statistics
- **Google Maps Platform** – Distance calculations
- **Power BI Community** – GeoJSON, forecasting, and text mining guides
- **Generation: You Employed, Inc.** – Project framework and structure
- **Team Members:** Alex Ng, Alex Wong, Camen Ho, Yuki Chow

---

> **"Lower price + strategic location = higher booking rate"**  
> — *GoTrip Singapore Market Insight, June 2025*
