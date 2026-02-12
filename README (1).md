# 📊 DataCo Supply Chain Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

> An end-to-end supply chain analytics solution analyzing 50,000+ orders to identify operational bottlenecks and drive data-driven decision making.

---

## 🎯 Project Overview

This comprehensive business intelligence project analyzes DataCo Global's supply chain operations across 3 years (2022-2024), revealing critical insights into logistics performance, financial health, and customer behavior.

### Key Highlights
- 📦 **50,000 orders** analyzed across 26,260 unique customers
- 💰 **$130.8M** in total revenue with **27.45%** profit margin
- 🚨 Identified **55% late delivery rate** as critical operational issue
- 📊 Built **4-page interactive dashboard** with 20+ advanced DAX measures

---

## 🔍 Business Problem

DataCo Global, a multi-national e-commerce company, needed to:
1. Understand supply chain performance across warehouses and shipping modes
2. Identify profitability drivers by product category and customer segment
3. Detect operational inefficiencies causing delivery delays
4. Analyze fraud patterns and customer behavior

---

## 📈 Key Findings

### 🚨 Critical Issues Identified

| Issue | Impact | Recommendation |
|-------|--------|----------------|
| **55% Late Delivery Rate** | Customer satisfaction & retention at risk | Implement predictive demand forecasting, optimize warehouse inventory |
| **1.98% Fraud Rate** | $2.7M revenue at risk | Deploy ML-based fraud detection system |
| **Low Customer Retention** | 1.9 orders per customer | Launch loyalty program, personalized marketing |
| **$10M Discount Impact** | Margin erosion | Optimize discount strategy with A/B testing |

### ✅ Success Metrics

- **Technology category:** 41.7% of revenue ($54.6M)
- **Texas market leadership:** $43.4M (33.1% of total)
- **Balanced customer segments:** Even distribution across Consumer, Corporate, Home Office
- **Geographic diversification:** 5 countries in supplier base

---

## 🛠️ Technical Stack

### Data Processing & Analysis
- **Python** (pandas, numpy, matplotlib, seaborn)
- **Power Query** for ETL transformations
- **DAX** for advanced calculations and time intelligence

### Business Intelligence
- **Power BI Desktop** for dashboard development
- **Data Modeling:** Star schema with Calendar dimension table
- **Advanced Features:** 
  - Time intelligence (YoY, MoM, YTD, MTD)
  - Dynamic filtering with synchronized slicers
  - Custom tooltips and drill-through pages

---

## 📊 Dashboard Pages

### 1. 📈 Overview
![Overview Dashboard](images/overview-page.png)

**Key Metrics:**
- Total Sales, Profit, Orders, On-Time Delivery %
- Sales trend over time
- Sales by product category and customer segment
- Top 10 cities performance

---

### 2. 🚚 Logistics Performance
![Logistics Dashboard](images/logistics-page.png)

**Analysis:**
- On-time delivery % vs Late delivery %
- Warehouse performance comparison
- Shipping mode efficiency analysis
- Delivery status breakdown

**Critical Insight:** All shipping modes show ~45% on-time performance, indicating systemic issues rather than mode-specific problems.

---

### 3. 💰 Financial Analysis
![Financial Dashboard](images/financial-page.png)

**Deep Dive:**
- Profit trend over time
- Sales vs Profit by category
- Profit margin % analysis
- Top 10 products by profitability
- YoY growth tracking

---

### 4. 👥 Customer Insights
![Customer Dashboard](images/customer-insights.png)

**Segmentation:**
- Customer distribution by segment
- Geographic sales analysis
- Payment method preferences
- Customer lifetime value metrics

---

## 🔢 Advanced DAX Measures

### Time Intelligence
```dax
YoY Growth % = 
VAR CurrentSales = [Total Sales]
VAR PreviousSales = [Previous Year Sales]
RETURN
DIVIDE(CurrentSales - PreviousSales, PreviousSales, 0) * 100
```

### Performance Metrics
```dax
On-Time Delivery % = 
VAR TotalOrders = [Total Orders]
VAR LateOrders = CALCULATE(COUNTROWS(DataCo_Enhanced), DataCo_Enhanced[Late Delivery Risk] = 1)
VAR OnTimeOrders = TotalOrders - LateOrders
RETURN
DIVIDE(OnTimeOrders, TotalOrders, 0) * 100
```

### Rolling Calculations
```dax
Rolling 3M Sales = 
CALCULATE(
    [Total Sales],
    DATESINPERIOD(Calendar[Date], LASTDATE(Calendar[Date]), -3, MONTH)
)
```

---

## 📁 Repository Structure

```
DataCo-Supply-Chain-Analytics/
│
├── README.md                          # Project documentation
├── data/
│   ├── DataCo_Supply_Chain_Dataset.csv         # Raw dataset
│   └── DataCo_Enhanced.csv                     # Processed dataset with features
│
├── images/
│   ├── overview-page.png
│   ├── logistics-page.png
│   ├── financial-page.png
│   └── customer-page.png
│
├── analysis/
│   ├── data_exploration.py                     # Python EDA script
│   ├── create_visualizations.py                # Visualization generation
│   └── visualizations/                         # 6 analytical charts
│
├── dashboard/
│   └── DataCo_Supply_Chain_Dashboard.pbix      # Power BI dashboard file
│
└── docs/
    └── DataCo_Analysis_Report.md               # Comprehensive analysis report
```

---

## 🚀 How to Use This Project

### Prerequisites
- Power BI Desktop (latest version)
- Python 3.8+ (for data analysis scripts)
- Required Python packages: `pandas`, `numpy`, `matplotlib`, `seaborn`

### Steps

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/DataCo-Supply-Chain-Analytics.git
cd DataCo-Supply-Chain-Analytics
```

2. **Explore the data**
```bash
python analysis/data_exploration.py
```

3. **Open the Power BI Dashboard**
- Open `dashboard/DataCo_Supply_Chain_Dashboard.pbix` in Power BI Desktop
- Refresh data connections if needed
- Interact with the dashboard using slicers and filters

4. **Read the detailed analysis**
- Check `docs/DataCo_Analysis_Report.md` for comprehensive insights

---

## 💡 Key Learnings & Skills Demonstrated

### Data Analysis
- ✅ Exploratory Data Analysis (EDA) on 50K+ records
- ✅ Data quality assessment and cleaning
- ✅ Statistical analysis and correlation studies
- ✅ Trend identification and pattern recognition

### Business Intelligence
- ✅ Star schema data modeling
- ✅ DAX measure development (20+ measures)
- ✅ Time intelligence calculations
- ✅ Interactive dashboard design

### Business Acumen
- ✅ Supply chain KPI identification
- ✅ Root cause analysis for operational issues
- ✅ Strategic recommendations based on data
- ✅ Stakeholder communication through visualizations

---

## 📊 Dataset Information

**Source:** DataCo Global Supply Chain Dataset (Synthetic data based on real-world structure)

**Size:** 50,000 orders

**Time Period:** January 2022 - December 2024

**Dimensions:**
- 31 columns including order details, customer information, product data, shipping logistics, and financial metrics
- 6 product categories
- 12 cities across 7 states
- 4 warehouses
- 6 suppliers from 5 countries

**Key Fields:**
- Order & shipping dates
- Customer segment & location
- Product category & pricing
- Sales & profit
- Delivery performance metrics
- Fraud indicators

---

## 🎯 Strategic Recommendations

### Immediate Actions (0-3 months)
1. **Fix Delivery Performance**
   - Root cause analysis across all warehouses
   - Implement real-time shipment tracking
   - Renegotiate carrier SLAs with performance penalties

2. **Enhance Fraud Detection**
   - Deploy ML-based fraud scoring model
   - Strengthen verification for credit card transactions

### Short-term Initiatives (3-6 months)
3. **Customer Retention Program**
   - Launch loyalty rewards
   - Personalized email campaigns
   - Win-back campaigns for dormant customers

4. **Discount Optimization**
   - A/B test discount levels
   - Implement dynamic pricing
   - Focus discounts on conversion vs. acquisition

### Long-term Strategy (6-12 months)
5. **Geographic Expansion**
   - Replicate Texas success model in similar markets
   - Targeted marketing in underperforming states

6. **Portfolio Optimization**
   - Expand Technology & Furniture offerings
   - Evaluate underperforming categories for growth or exit

---

## 📈 Expected Impact

Implementing the recommended actions could achieve:
- 📉 Reduce late deliveries from 55% to <20%
- 📈 Increase customer retention by 15%
- 💰 Improve profit margins by $2M through discount optimization
- 🚨 Reduce fraud losses by 50%
- 📊 Overall revenue growth of 18-25% over 12-24 months

---

## 🙋‍♀️ Contact & Portfolio

**Created by:** Buthainah Elfakharany

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/buthainah-elfakharany-b91563354)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:buthainah3524@icloud.com)

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 🙏 Acknowledgments

- Dataset structure inspired by real-world supply chain operations
- Dashboard design principles from Power BI best practices
- Time intelligence patterns from DAX.do and SQLBI resources

---

**⭐ If you found this project helpful, please consider giving it a star!**

---

*Last Updated: February 2026*
