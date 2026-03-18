# Insurance Policy Analysis Report - Power BI

## 📊 Project Overview

A comprehensive **Insurance Policy Analysis Report** built in Microsoft Power BI to analyze insurance policy performance, customer demographics, and financial metrics. This interactive Report provides stakeholders with a unified view of the insurance business lifecycle, enabling data-driven decision-making across policy performance, claims analysis, maturity forecasting, and operational efficiency.

---

## 🎯 Business Goals

This project delivers a complete insurance policy lifecycle analytics solution with the following objectives:

### **Primary Objectives:**
- **Unified Business View:** Provide a single, consolidated view of the insurance business for all stakeholders
- **Policy Performance Tracking:** Monitor and analyze how different insurance policy types perform across various customer segments
- **Geographic Performance Analysis:** Understand which policy types and states are performing well or underperforming
- **Product Optimization:** Identify top-performing policy plans and flag those with low customer uptake
- **Claims Efficiency:** Monitor claim settlement performance and detect inefficiencies in the claims process
- **Operational Accountability:** Improve accountability and performance across sales, claims, and loan servicing teams
- **Real-Time Insights:** Automate report refresh to ensure stakeholders always see the latest data

---

## 📂 Data Model & Architecture

### **Data Sources:**
The Report integrates comprehensive insurance data, capturing the complete policy lifecycle including policy creation, tenure tracking, customer demographics, claims processing, loan information, and maturity calculations.

### **Data Tables:**

#### **1. Customer Detail Table**
- Customer ID → Unique identifier for each customer
- Policy Holder Name → Full name of the policyholder
- Gender → Gender of the customer (Male/Female/Other)
- Age at Entry → Age of the customer at the time of policy purchase
- Current Age → Current age of the customer
- Occupation → Profession of the customer (e.g., Doctor, Engineer)
- Smoker Status → Indicates if the customer is a smoker (Yes/No)
- Medical Exam Required → Whether a medical test was required at policy issuance
- Nationality → Nationality of the customer (e.g., India)
- State → State of residence of the customer

#### **2. Policy Type Table**
- Policy Type → Category of insurance policy (Term, Whole Life, Universal)
- Policy Type Code → Unique alphanumeric code for system identification

#### **3. Policy Name Table**
- Policy Name → Official product name (e.g., Life Growth Advantage, Smart Term Protect)
- Policy Code → Unique alphanumeric identifier for each policy product

#### **4. Sales Agent Table**
- Agent Code → Unique identifier for each sales agent (e.g., AGT-3894)
- Sales Agent → Name of the insurance sales agent (e.g., Dhanush Sarraf, Dishani Boman)
- State → Geographic region where agent operates (Maharashtra, Goa, Karnataka)

#### **5. Insurance Policy Table (Fact Table)**
- Policy Number → Unique identifier for each policy
- Policy Status → Current status (Active, Lapsed, Closed, etc.)
- Start Date → Date on which the policy started
- Last Paid Date → The last premium payment date
- Tenure (Years) → Total duration of the policy in years
- Date of Purchase → Date when customer bought the policy
- Customer ID → Links to Customer Detail Table
- Sum Assured / Coverage Amount → Guaranteed coverage offered by the policy
- Premium Amount → Recurring premium the customer must pay
- Payment Frequency → How premiums are paid (Annually, Quarterly, Monthly, etc.)
- Total Premium to be Paid by End of Tenure → Total premium outflow across policy period

---

## 🧮 Advanced Financial Calculations

### **Key Metrics Implemented:**

#### **1. Total Premium Amount**
```
Total Premium Amount = Annual Premium × Number of Years (or Payment Terms)
```
Sum of all premiums paid over the policy duration.

#### **2. Total Annual Premium**
Amount required to pay in premiums for one year based on payment frequency:

| Payment Frequency | Multiplier |
|-------------------|-----------|
| Monthly           | × 12      |
| Quarterly         | × 4       |
| Half-Yearly       | × 2       |
| Yearly            | × 1       |

Formula: `Total Annual Premium = [Premium Amount] × [Payment Frequency Multiplier]`

#### **3. Total Premium Paid**
Entire amount of money the policyholder has paid (or will pay) over the full duration of the policy.

Formula: `[Total Annual Premium] × [Premium Payment Duration]`

#### **4. Maturity Amount**
Total sum of money the policyholder receives at the end of the policy term (if all premiums paid as per agreement). Based on **Return Rate Matrix by Policy Type, Premium & Tenure**.

#### **5. Premium Payment Duration**
Number of years for which the policyholder is required to pay premiums to keep the policy active.

#### **6. Premium Amount Payable**
Amount of money the policyholder needs to pay to the insurance company per premium schedule (monthly, quarterly, half-yearly, or yearly).

#### **7. Annualized ROI (%)**
Average return per year earned on the investment (Return on Investment):

```
Annualized ROI (%) = ((Final Value / Total Invested)^(1/Years) - 1) × 100
```

**Example Calculation:**
- Initial Investment: ₹1,00,000
- Final Value: ₹2,00,000
- Time: 5 years
- Result: 14.87% per year (compounded)

#### **8. CAGR (%) - Compound Annual Growth Rate**
Measures the average annual growth rate of an investment over a period, assuming compounding:

```
CAGR = ((Final Value / Initial Value)^(1/n) - 1)
```

Where:
- Final Value = Maturity Amount or current value
- Initial Value = Total Premium Paid / Invested Amount
- n = Number of years (Tenure of the policy/investment)

---

## 🔐 Row-Level Security (RLS) Implementation

### **Security Architecture:**

Implemented **Dynamic Row-Level Security** to ensure stakeholders see only their region's data:

#### **User Roles:**
1. **Zonal Manager** → Access to specific zone
2. **Regional Manager** → Access to specific region
3. **Owners** → Access to complete data across all regions

---

## 🛠️ Technologies & Tools

**Business Intelligence:**
- **Microsoft Power BI Desktop** - Report development and data modeling
- **Power BI Service** - Publishing, sharing, and RLS deployment
- **Power Query** - Data transformation and ETL processes

**Data Analysis Expressions (DAX):**
- Advanced calculated columns and measures
- Time intelligence functions
- Security and filtering logic
- Financial calculation formulas (ROI, CAGR, Maturity calculations)

**Data Modeling:**
- Star schema with fact and dimension tables
- One-to-many relationships
- Cross-filtering and bi-directional relationships where needed

---

## 📊 Report Features

### **Interactive Visualizations:**
- **Policy Performance Metrics:** Track active, lapsed, and closed policies
- **Premium Analysis:** Monthly/quarterly/yearly premium collection trends
- **Claims Report:** Monitor claim settlement performance
- **Geographic Performance:** State-wise and region-wise policy distribution
- **Agent Performance:** Sales agent productivity and policy sales tracking
- **Maturity Forecasting:** Projected maturity amounts and timelines
- **Customer Segmentation:** Analysis by age, occupation, smoker status
- **ROI Analysis:** Investment returns and policy profitability

### **Dynamic Filtering:**
- Date range selectors
- Policy type filters
- Geographic region slicers
- Agent and customer demographic filters
- Policy status filters

### **KPI Cards:**
- Total Policies Sold
- Active Policy Count
- Total Premium Collected
- Projected Maturity Amount
- Average Policy Tenure
- Claim Settlement Rate

---

## 💡 Key Business Insights

### **Policy Performance Analysis**
- Identification of high-performing vs. underperforming policy types
- Geographic trends in policy adoption
- Customer demographic patterns in policy selection

### **Claims Efficiency**
- Claim settlement performance monitoring
- Detection of bottlenecks in the claims process
- Identification of high-risk customer segments

### **Sales Optimization**
- Top-performing sales agents and regions
- Low-uptake policy products flagged for review
- State-wise market penetration analysis

### **Financial Projections**
- Maturity amount forecasting based on Return Rate Matrix
- ROI and CAGR calculations for investment policies
- Premium collection trends and forecasting

---

## 🎓 Skills Demonstrated

✅ **Advanced Power BI Development:** Complex data modeling, DAX optimization, interactive Reports  
✅ **Row-Level Security:** Multi-role security implementation with dynamic DAX  
✅ **Financial Modeling:** ROI, CAGR, maturity calculations, premium schedules  
✅ **DAX Proficiency:** USERPRINCIPALNAME(), LOOKUPVALUE(), CONTAINSSTRING(), IF(), IN operator  
✅ **Data Governance:** Security implementation, role-based access control  
✅ **Business Intelligence:** Translating business requirements into analytical solutions  
✅ **Stakeholder Management:** Creating Reports for multiple user personas  

---

## 📁 Repository Contents

```
Insurance-PowerBI-report/
│
├── README.md                          # Project documentation (this file)
├── Insurance.pbix                     # Power BI Report file
```

---

## 👤 About the Analyst

**Darshil Dave**  
Senior Data Analyst | 6+ Years Experience in Supply Chain Analytics at Accenture  
Microsoft PL-300 Certified Power BI Data Analyst | DAX & Data Modeling Expert

📫 **Email:** darshildave2021@gmail.com  
💼 **LinkedIn:** [Connect with me](https://linkedin.com/in/darshil-d-895394193/)  
🔗 **GitHub Portfolio:** [github.com/darshildave20](https://github.com/darshildave20)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**⭐ If you find this project helpful, please consider giving it a star!**

---

*Last Updated: March 2026*  

