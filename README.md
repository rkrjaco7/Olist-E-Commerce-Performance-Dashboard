# Olist-E-Commerce-Performance-Dashboard
An industry-level e-commerce analytics dashboard using PostgreSQL and Power BI. Features real-time DirectQuery connectivity, SQL-optimized views for 1M+ rows, and advanced DAX modeling for business KPIs and logistics tracking.
# Industry-Level E-Commerce Data Analytics Dashboard 📊

## 📝 Project Overview
This project is an end-to-end, industry-standard data analytics solution built for a Brazilian E-Commerce company (Olist). The goal of this project was to process, optimize, and visualize a massive dataset containing over 100,000+ records to uncover actionable business insights regarding sales trends, logistics, customer geography, and product performance. 

By utilizing **PostgreSQL** as the backend database and connecting it to **Power BI via DirectQuery**, this project demonstrates how to handle large-scale data efficiently without compromising on dashboard performance.

---

## 🛠️ Tech Stack & Tools
* **Database Management:** PostgreSQL, pgAdmin 4
* **Business Intelligence:** Power BI Desktop
* **Query Languages:** SQL, DAX (Data Analysis Expressions)
* **Dataset:** [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (9 related tables)

---

## ⚙️ System Architecture & Workflow

### 1. Database Setup & Optimization (PostgreSQL)
Importing raw CSV files directly into a BI tool can lead to severe lag and performance bottlenecks. To prevent this, the data was processed at the database level:
* **Data Ingestion:** Created a custom database (`olist_db`) and imported 9 raw CSV files representing customers, geolocation, order items, payments, reviews, products, and sellers.
* **Schema Design:** Established Primary and Foreign Key constraints to build a robust **Star Schema** relationship model.
* **Performance Tuning (Indexing):** Implemented B-Tree indexing on heavily queried columns (e.g., `order_id`) to significantly reduce data retrieval times.
* **SQL Views (Virtual Tables):** Wrote advanced SQL joins to create optimized Views. This filtered the dataset down from 70+ raw columns to the ~20 essential columns needed for analytics, drastically reducing the load on Power BI.

### 2. Power BI Integration (DirectQuery Mode)
* **Connection Mode:** Used **DirectQuery Mode** instead of Import Mode. This ensures the dashboard queries the PostgreSQL database in near real-time, allowing for live updates without storing heavy caches locally.
* **Data Modeling:** Connected the optimized SQL Views to a custom-built `DimDate` (Date Dimension) table to enable precise time-intelligence reporting.

### 3. Advanced DAX Measures
Created over 20 dynamic DAX measures to track Key Performance Indicators (KPIs), including:
* **Base Metrics:** Total Revenue, Total Orders, Total Customers, Average Order Value (AOV), Items per Order.
* **Time-Intelligence:** Year-to-Date (YTD) Revenue, Last Year (LY) Revenue, Year-over-Year (YoY) Growth %, and 30-Day Rolling Revenue.
* **Logistics & Reviews:** Average Delivery Days, Late Delivery %, On-Time %, and Positive/Negative Review Percentages.

---

## 📈 Dashboard Pages & Insights

The final Power BI report is divided into several highly interactive pages tailored for different stakeholders:

1. **Executive Overview:** High-level KPIs, Total Revenue, Total Orders, Order Status shares (Donut chart), and state-wise revenue distribution (Map visual).
2. **Sales Trends:** Deep dive into revenue versus last year, 30-day rolling revenue tracking, and YTD performance using area and smooth line charts.
3. **Category & Product Analysis:** Treemaps showing category revenue share, scatter plots comparing AOV vs. Orders, and Top 20 categories sorted by on-time delivery percentages.
4. **Customer Geographics:** Geographic maps and matrices identifying the top 10 most profitable customer states and cities.
5. **Delivery & Logistics:** KPI tracking for late orders vs. on-time orders, and average delivery days mapped by product category.
6. **Review Sentiment:** Distribution of positive, neutral, and negative reviews correlated with delivery times (late vs. on-time).
7. **Drill-Through Capabilities:** Users can right-click any specific product category or state to "drill through" to a hidden details page, revealing highly granular performance metrics.

---



## 🚀 How to Run This Project Locally

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/Ecommerce-Data-Analytics-PowerBI.git](https://github.com/YOUR_USERNAME/Ecommerce-Data-Analytics-PowerBI.git)
