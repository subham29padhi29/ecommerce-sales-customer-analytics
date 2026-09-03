# 📊 E-Commerce Sales & Customer Analytics: Exploratory Data Analysis

## 📌 Project Overview
In modern retail, understanding purchasing behaviors, fulfillment performance, and revenue drivers is critical for strategic decision-making. This project presents a comprehensive Exploratory Data Analysis (EDA) on a transactional dataset comprising **138,116 cleaned customer orders** (processed from an initial 150,000 raw records). 

Through data cleaning, statistical summarization, bivariate/multivariate visualizations, and time-series forecasting trends, this analysis extracts actionable business insights to optimize promotional strategies, logistics SLAs, and customer retention.

---

## 🛠️ Tech Stack & Tools
* **Language:** Python
* **Data Processing & Manipulation:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Environment:** Jupyter Notebook / VS Code

---

## 📐 Dataset Architecture & Preprocessing
* **Initial Records:** 150,000 transactions
* **Cleaned Dataset:** 138,116 valid transactions
* **Preprocessing Pipeline:**
  * Removed duplicate transactions and handled invalid/missing fields.
  * Treated continuous numeric variables (`net_sales`, `gross_sales`, `profit`, `discount_amount`, `shipping_cost`).
  * Engineered log/binned features to evaluate right-skewed revenue distribution.

---

## 🔑 Key Business Findings & Numeric Results

### 1. Sales & Revenue Dynamics
* **Total Net Revenue:** **$177,134,263.74 ($177.13M)**
* **Order Skewness:** Mean order value stands at **$1,282.50**, compared to a median of **$950.76**, with a long tail of bulk orders extending up to **$16,000+**.
* **Channel Dominance:**
  * **Mobile App:** $70.81M Net Revenue | 55,246 Orders | $30.45M Profit
  * **Website:** $62.01M Net Revenue | 48,340 Orders | $26.64M Profit
  * *Takeaway:* Digital channels (App + Web) drive over **75% of bottom-line profit**.

### 2. Customer Payment Preferences
1. **Credit Card:** 30.02% (41,460 orders)
2. **Debit Card:** 20.01% (27,635 orders)
3. **PayPal:** 15.02% (20,750 orders)
4. **Digital Wallet:** 11.86% (16,382 orders)
5. **Cash on Delivery (COD):** 10.04% (13,863 orders)
6. **Buy Now Pay Later (BNPL):** 8.01% (11,061 orders)
7. **Bank Transfer:** 5.04% (6,965 orders)

### 3. Geographical Performance
* **Top Volume Region:** **South Region** ($55.59M Net Revenue | 43,990 orders)
* **Top Value Region:** **North Region** achieved the highest Average Order Value at **$1,357.39 per order**.

### 4. Correlation & Seasonality Drivers
* **Revenue vs. Profit ($r = 0.91$):** Net sales convert reliably into bottom-line earnings.
* **Discount Inefficiency ($r = 0.73$ vs $r = 0.20$):** Discounts strongly correlate with top-line gross sales ($r = 0.73$), but show weak correlation with final net profit ($r = 0.20$), indicating margin erosion from steep price cuts.
* **Holiday Seasonality:** Demand spikes every November–December (**$4.5M–$4.9M monthly revenue**), followed by a steep post-holiday trough in January–February (**$1.9M–$2.0M monthly revenue**).
* **Fulfillment Penalty:** Shipping speed directly controls customer rating:
  * **Early Delivery:** 4.02 / 5.00 Stars
  * **On-Time Delivery:** 3.73 / 5.00 Stars
  * **Delayed Delivery:** 3.22 / 5.00 Stars

---

## 🎯 Strategic Recommendations
1. **Refine Promotional Mechanics:** Transition away from blanket percentage discounts toward minimum-order thresholds (e.g., *"Spend $1,500 to save 10%"*) to protect unit margins.
2. **Overhaul Logistics SLAs:** Partner with higher-performing freight carriers in the South and East regions to reduce fulfillment delays and boost overall review scores past 4.0 stars.
3. **Optimize Digital Marketing:** Reallocate ad spend from lower-performing channels (Social Media & Marketplace) toward Mobile App loyalty notifications and high-margin conversion paths.
4. **Q4 Inventory Prep:** Build up fulfillment center inventory by mid-October to handle predictable 2.5x holiday demand surges without incurring shipping bottlenecks.

---

## 📂 Project Structure
```text
├── data/
│   ├── raw_ecommerce_data.csv
│   └── cleaned_ecommerce_data.csv
├── notebooks/
│   └── ecommerce_eda_analysis.ipynb
├── visuals/
│   ├── revenue_distribution.png
│   ├── channel_profitability.png
│   ├── correlation_heatmap.png
│   └── monthly_sales_trend.png
├── README.md
└── requirements.txt
