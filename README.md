 ## Project Description

ecom-customer-suite is a comprehensive customer and revenue analytics project built using the Online Retail II dataset. The goal is to empower e-commerce businesses with actionable insights on sales performance, customer retention, cohort behavior, and lifetime value—all derived through rigorous data wrangling, exploratory analysis, and advanced segmentation techniques.



---

###  Data Preparation

A strong analytical foundation was established through meticulous data preprocessing. Missing values were addressed, data types corrected, and canceled or erroneous transactions were removed to ensure reliability. By engineering temporal features—such as month, quarter, week, and hour—we enabled fine-grained time-series analysis. This groundwork was critical for revealing seasonal trends, customer behavior patterns, and product dynamics, setting the stage for all downstream business insights.

---

### Sales Analytics and  Trends Analytics

To understand the sales engine of the business, we explored revenue patterns across various time granularities. Trends were visualized on monthly, quarterly, weekly, and even hourly scales, helping pinpoint periods of high and low customer activity. These insights are instrumental for capacity planning, marketing campaign scheduling, and identifying underperforming periods. Knowing when customers are most likely to buy allows businesses to optimize staffing, logistics, and promotional efforts.

---

###  Product-Level  Analysis

The next layer of analysis dove into product dynamics. We identified which items were driving the bulk of sales—and which were lagging. This not only highlights bestsellers for potential bundling and upselling strategies but also flags poor performers that may require reevaluation or promotion. Return and cancellation patterns were also studied, revealing customer dissatisfaction signals or logistical issues. By calculating each product’s average revenue contribution, we provided a profitability lens critical for inventory and pricing strategies.

---

### Customer Cohort Analysis

Understanding how customer behavior evolves over time is key to sustainable growth. By grouping users by their acquisition month, we built cohorts that allowed us to track engagement and retention longitudinally. This revealed how loyal customers are, when they tend to churn, and which acquisition periods led to stronger relationships. Visual cohort heatmaps made it easy to spot which customer groups are consistently returning and which drop off early, enabling better lifecycle marketing and user nurturing strategies.

---

### Quarterly Retention & Churn Rate Analysis

Beyond monthly views, we zoomed out to assess customer retention and churn at a quarterly level. This macro view allowed us to observe long-term loyalty trends and identify inflection points where customers are most likely to disengage. These metrics inform not just retention strategies, but also help in forecasting future revenue and evaluating the effectiveness of past marketing efforts.

---

###  Cohort-Based Revenue Retention

While retention measures customer counts, revenue retention focuses on financial impact. We tracked how much revenue each acquisition cohort generated over time and how that amount decayed. This view is crucial for understanding not just who stays, but **how much they spend**—allowing businesses to invest more in acquisition channels that drive long-term value. Revenue decay curves helped illustrate when monetization efforts start to wane, guiding re-engagement campaigns and personalized outreach.

---

### Net Revenue Retention (NRR) Analysis

Borrowing from SaaS metrics, we applied Net Revenue Retention (NRR) to a retail context to quantify how well the business grows revenue from its existing customer base. By separating revenue into three components—existing revenue, expansion (increased spend), and churn—we gained a nuanced view of revenue health. A high NRR signals strong customer satisfaction and product-market fit, while a declining NRR may indicate emerging issues in retention or product value. This is a core metric for evaluating sustainable growth.

---

### Revenue Segmentation by Customer Cohort

Not all customers contribute equally to the bottom line. By segmenting total revenue by acquisition cohort, we uncovered which customer groups delivered the most financial value over time. This analysis supports targeted campaigns, loyalty programs, and personalized experiences focused on high-performing customer segments. It also helps allocate resources more effectively by investing in channels that bring in valuable, long-term users.

---

###  Customer Lifetime Value (CLV) Estimation

CLV is one of the most important metrics for any customer-centric business. We estimated the total revenue each customer is expected to generate throughout their relationship with the business using average revenue per user and estimated customer lifespan. This allowed us to identify the most valuable customer segments—those worth retaining at all costs—and supported the development of retention programs, tiered loyalty systems, and reactivation workflows. By shifting focus from short-term transactions to long-term relationships, businesses can significantly improve profitability.
###  Dataset

- **Source**: [UCI Online Retail II Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Retail+II)
- **Duration**: December 2009 to December 2011
- **Description**: This dataset contains transactional data from a UK-based online retailer. It includes over 500,000 records of customer purchases, capturing detailed invoice-level data for both domestic and international customers.

#### Key Features:
| Column         | Description                               |
|----------------|-------------------------------------------|
| `InvoiceNo`    | Unique identifier for each transaction     |
| `StockCode`    | Unique product/item code                   |
| `Description`  | Name/description of the product            |
| `Quantity`     | Number of units sold per transaction       |
| `InvoiceDate`  | Date and time of the transaction           |
| `Price`        | Unit price of the product                  |
| `Customer ID`  | Unique ID assigned to each customer        |
| `Country`      | Country of the customer                    |

###  How to Run

1. **Clone the repository**

   ```bash
   git clone https://github.com/Abhi1459/ecom-customer-suite.git
   cd ecom-customer-suite

###  Libraries Used
- pandas
- numpy
- matplotlib
- seaborn
- jupyter
### 📊 Visual Insights

#### 🛍️ Sales Performance
- **Monthly Sales Trend**
  ![Monthly Sales](Visuals/Monthly_sale_trend.png)

- **Weekly Sales Trend**
  ![Weekly Sales](Visuals/weekly_sale_trend.png)

- **Yearly Sales Trend**
  ![Yearly Sales](Visuals/Yearly_sale_trend.png)

- **Hourly Sales Trend**
  ![Hourly Sales](Visuals/Hourly_sale_trend.png)

#### 📦 Product Analysis
- **Top 10 Products by Quantity Sold**
  ![Top Quantity](Visuals/Top10product_by_qty_sold.png)

- **Top 10 Products by Revenue**
  ![Top Revenue](Visuals/Top10product_by_revenue.png)

- **Products with Highest Cancellations**
  ![Cancellations](Visuals/Product_with_higher_cancellation.png)

#### 🌍 Customer & Country Insights
- **Countries with Highest Sales and Returns**
  ![Country Sales](Visuals/Countries_with_highest_sales_and_returns.jpeg)

- **Customers with Lowest Spending**
  ![Low Spending](Visuals/CustomerID_with_lowest_spending.png)

#### 🔁 Retention & Revenue Metrics
- **Quarterly Customer Retention (Heatmap)**
  ![Customer Retention](Visuals/Quarterly_customer_retention.jpeg)

- **Quarterly Churn Rate (Heatmap)**
  ![Churn Rate](Visuals/Quarterly_churn_Rate.jpeg)

- **Cohort-Based Revenue Retention & NRR**
  ![Cohort Retention & NRR](Visuals/Cohort_based_revenue_retention_and_NRR.jpeg)

- **Customer Lifetime Value by Cohort**
  ![CLV](Visuals/CLV_by_cohort_and_lifetime_value_per_customer.jpeg)

 ##  Deep-Dive into Data Quality, Anomalies & Business Insights

While working on the Online Retail dataset, I realized that meaningful analysis requires more than just cleaning rows and columns. It involves **understanding what the data represents**, and more importantly, how certain patterns or anomalies might affect real-world business decisions.

---

###  Cancelled Orders – Understanding Negative Quantities

One of the first things I noticed was that some invoices began with the letter **'C'**. At first glance, they looked similar to other entries, but on closer inspection, almost all of them had **negative quantities**. When I investigated further, I discovered that these were actually **cancelled orders or customer returns**.

This insight was important — over **90% of the negative quantity rows** in the entire dataset came from these invoices. Including them in sales metrics like total revenue, CLV (Customer Lifetime Value), or retention could completely distort the results. So, I designed my filters to exclude or net them off against actual sales, which gave me much more **realistic business KPIs**.

It was a reminder that not every row of data means money in the bank — context matters.

---

###  Adjusted Bad Debt – The Quiet Distorters

Another unexpected pattern came from invoices labeled as **“A”**. These rows typically had **negative prices**, and often zero quantity. They weren’t returns or refunds — they appeared to be **accounting adjustments** or **financial write-offs** made internally.

From a financial reporting standpoint, these shouldn’t be mixed with genuine transactions. Including them would result in misleading trends — for example, a sudden drop in average selling price, or artificially negative revenue.

To avoid this, I excluded these entries from metrics like **average unit price**, **product profitability**, and **monthly revenue trends**. It reinforced how important it is to ask: *“Is this a real sale, or just a backend adjustment?”*

---

###  Real Sales Invoices – Recognizing Genuine Patterns

Something that helped me separate clean data from noise was a small but consistent pattern: **real sales invoices always started with a number**, typically **4** or **5**. These invoices showed typical retail behavior, such as positive quantities, reasonable prices, and customer details.

This turned into a reliable rule for me. Whenever I was generating dashboards or running customer segmentation, I used this prefix logic to focus only on **authentic sales activity**. It saved a lot of time, especially when performing cohort or churn analysis, where including false positives (like returns or bad debt entries) would’ve led to incorrect insights.

---

###  Outliers in Product Pricing – The Strange and the Surprising

While analyzing pricing patterns, I discovered a few interesting outliers that taught me a lot about product-level behavior.

#### The Most Expensive Product

One product titled `'Manual'` stood out immediately. It was priced at a staggering **£38,970.00**, with a quantity of **-1**. There were no other transactions for this product.

At first, I thought this might be a premium item — but a deeper look suggested it could be a **manual data entry error**, a placeholder, or maybe a test case someone forgot to remove.

Rather than removing it blindly, I flagged it as a **data anomaly** and kept it excluded from all financial calculations. This ensured that one odd entry didn’t distort metrics like highest product revenue or average order value.

####  The Cheapest Product

On the other end of the spectrum was a product called `'PADS TO MATCH ALL CUSHIONS'`, priced at just **£0.001 per unit**. Effectively, you could get 100 items for a penny.

This clearly wasn’t intended to generate profit. It seemed like a **giveaway item**, part of a bundle, or something used for marketing purposes.

Again, I didn’t delete it — but I marked it as a **non-revenue driver**. That way, my pricing and profitability analysis remained clean, while still acknowledging the presence of low-value items that may play a role in customer experience or packaging strategy.

---

###  Largest Order – A Closer Look at Bulk Buyers

When reviewing the highest-value transactions, one sale stood out:

- **Product**: `PAPER CRAFT , LITTLE BIRDIE`  
- **Quantity**: 80,995 units  
- **Unit Price**: £2.08  
- **Total Order Value**: **£168,467.60**  
- **Customer ID**: 16446  
- **Invoice Date**: December 9, 2011

This was no ordinary purchase — it was likely made by a **corporate buyer, wholesaler, or reseller**, especially considering the size and timing (just before the holiday season).

From a business angle, this highlighted that the platform wasn’t only catering to B2C customers. These kinds of buyers have a huge impact on revenue and fulfillment, and I made sure to **segment them separately** from regular customers during my CLV and retention analysis. Treating them the same would’ve distorted per-customer averages and skewed trends unfairly.



By spending time understanding not just what was wrong, but **why** it looked that way, I was able to:

- Build stronger logic for identifying valid sales.
- Make smarter decisions on what to include or exclude in KPIs.
- Extract deeper business meaning from what at first seemed like “bad data”.

  

 

 




