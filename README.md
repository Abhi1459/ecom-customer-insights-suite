## 🔍 Project Workflow & Modules

This project follows a structured, step-by-step analytical pipeline to uncover insights from raw e-commerce data. Below is the progression of analysis:

---

### 📌 1. Data Preparation
- Handled missing values and incorrect data types
- Filtered canceled transactions and outliers
- Converted `InvoiceDate` to datetime format
- Extracted temporal features: `Month`, `Quarter`, `Year`, `Week`, `Hour`

---

### 2. General Sales Analysis
- **Monthly, Quarterly, Yearly, Weekly, Hourly Trends**
- Aggregated and visualized total sales across time frames
- Identified peak and off-peak sales periods

---

### 📦 3. Product-Level Analysis
- Top & bottom-selling products
- Product returns and cancellations
- Average revenue contribution by product
- Visualized product-wise quantity and price trends

---

### 👥 4. Cohort Analysis
- Grouped users by acquisition month (first purchase)
- Tracked retention monthly to identify stickiness
- Built cohort heatmaps for customer survival curves

---

### 📉 5. Quarterly Retention & Churn Rate
- Calculated **churn rate** and **retention rate** by quarter
- Plotted trends to track customer loyalty and drop-off

---

### 💰 6. Cohort-Based Revenue Retention
- Measured revenue from each cohort over subsequent periods
- Identified high-value acquisition months
- Visualized cohort revenue decay patterns

---

### 7. Net Revenue Retention (NRR)
- Quantified expansion, contraction, and churn revenue
- NRR = (Existing + Expansion - Churn) / Prior Revenue
- Important SaaS metric applied in retail context

---

### 📊 8. Customer Revenue by Cohort
- Segmented revenue by acquisition cohort
- Highlighted how different cohorts performed over time

---

### 9. Customer Lifetime Value (CLV)
- Estimated lifetime revenue per customer
- Used average revenue per user and average lifespan
- Identified most valuable customer segments

---

Each module is implemented as a separate notebook, making the workflow clean, reproducible, and easy to interpret.

