# Retail Intelligence System: End-to-End Data Science Project

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Library](https://img.shields.io/badge/Library-Pandas%20|%20Scikit--Learn%20|%20Statsmodels-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)
##  Executive Summary
* **Goal:** Transform raw transactional data (500,000+ rows) into actionable business strategies using Machine Learning and Time Series Analysis.
* **Context:** Analysis of a UK-based online retailer's transaction dataset (UCI Machine Learning Repository). The project moves beyond simple reporting to provide predictive insights on customer behavior, inventory planning, and product bundling.
* **Key Achievements:**
* **Identified VIP Customers** driving 80% of revenue using **K-Means Clustering**.
* **Forecasted 16 Weeks of Revenue** with **Holt-Winters Exponential Smoothing**.
* **Discovered Hidden Product Bundles** (e.g., *Green & Red Alarm Clocks*) using the **Apriori Algorithm**.

---
##  Tech Stack & Tools
* **Data Engineering:** `Pandas`, `NumPy` (Cleaning & Feature Engineering)
* **Visualization:** `Matplotlib`, `Seaborn`, `Plotly` (Interactive Dashboards)
* **Machine Learning:** `Scikit-Learn` (K-Means Clustering)
* **Statistical Modeling:** `Statsmodels` (Time Series Forecasting)
* **Association Mining:** `Mlxtend` (Market Basket Analysis)

# Project Phases & Insights

### Phase 1: Data Engineering (The Foundation)
* **Challenge:** Raw data contained ~135,000 missing customer records and ~9,000 cancelled orders (negative quantity).
* **Solution:** Built a rigorous cleaning pipeline to remove nulls, filter cancellations, and parse dates.
* **Result:** A clean "Golden Dataset" of **397,924** high-quality transactions ready for ML.

### Phase 2: Exploratory Data Analysis (EDA)
* **Top Products:** The "Pareto Principle" was confirmed. The item **"REGENCY CAKESTAND 3 TIER"** is a primary volume driver, while **"DOTCOM POSTAGE"** is the highest revenue generator.
* **Seasonality:** Identified a massive sales spike in **November**, indicating the need for Q4 inventory "safety stock."

### Phase 3: Customer Segmentation (K-Means Clustering)
We used **RFM Analysis (Recency, Frequency, Monetary)** to map customers into 3 distinct personas:

| Cluster | Label | Profile | Strategy |
| :--- | :--- | :--- | :--- |
| **0** |  **The VIPs** | High Spend (£7,900+), Frequent Visits. | **Loyalty Program:** Early access to new items. |
| **1** |  **Hibernating** | Visited once long ago (~6 months). | **Win-Back:** Send "We Miss You" coupons. |
| **2** |  **Regulars** | Steady monthly visitors. | **Upsell:** Recommend higher-margin items. |

### Phase 4: Sales Forecasting (Time Series)
* **Model:** Holt-Winters Exponential Smoothing (Additive Trend & Seasonality).
* **Performance:** The model successfully captured the annual seasonality (December peaks) and predicted a post-holiday dip in January/February.
* **Impact:** Enables precise cash flow management for the slow Q1 period.

### Phase 5: Market Basket Analysis (Apriori)
* **Goal:** Find "Frequently Bought Together" items for recommendation engines.
* **Discovery:** Strong association between color variants.
    * *Rule:* If Customer buys **Green Alarm Clock** → **70%** chance they buy **Red Alarm Clock**.
* **Action:** Create "Collector Bundles" to increase Average Order Value (AOV).

##  Business Recommendations
1.  **Inventory:** Stock up on "Regency Cakestands" and "Paper Buntings" by **October 1st** to prepare for the November rush.
2.  **Marketing:** Stop spending ad money on "Hibernating" customers; focus budget on converting "Regulars" into "VIPs."
3.  **Website Optimization:** Implement a "Complete the Set" pop-up for customers buying specific color variants (e.g., Alarm Clocks, Lunch Boxes).

## How to Run This Project
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/retail-intelligence.git](https://github.com/yourusername/retail-intelligence.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas numpy matplotlib seaborn plotly scikit-learn statsmodels mlxtend
    ```
3.  **Run the Notebook:**
    Launch Jupyter and open `Retail_Analysis_Main.ipynb`.

**Author:** John
**Role:** Data Analyst / Data Scientist
