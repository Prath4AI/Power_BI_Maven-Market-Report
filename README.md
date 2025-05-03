# Power_BI_Maven-Market-Report
The objective of this project was to design a dynamic and insightful Power BI dashboard for the AdventureWorks dataset, focused on tracking Orders, Revenue, Profit, and Return Rates over multiple years (2020–2022). The dashboard aims to help stakeholders monitor performance against targets and compare metrics across periods.


![Image](https://github.com/user-attachments/assets/6a97e462-f423-42da-993c-6a94b4450b3f)

---

##  Power BI Project Report: AdventureWorks Orders & Performance Dashboard

###  Project Overview:

The objective of this project was to design a dynamic and insightful Power BI dashboard for the AdventureWorks dataset, focused on tracking **Orders, Revenue, Profit, and Return Rates** over multiple years (2020–2022). The dashboard aims to help stakeholders monitor performance against targets and compare metrics across periods.

---

##  Data Sources:

* **AdventureWorks Orders Data**
* **Calendar Lookup Table**
* **Order Targets**
* Derived and calculated tables for **Revenue**, **Profit**, **Orders**, and **Returns**

---

## 📊 Key Metrics and KPIs:

* **Total Revenue:** \$24.91M
* **Total Profit:** \$10.04M
* **Total Orders:** 25,164
* **Return Rate:** 2.17%

---

## 📋 Key Visuals and Insights:

### **Yearly Orders Breakdown**

| Year | Total Orders |
| :--- | :----------- |
| 2022 | 11,839       |
| 2021 | 10,695       |
| 2020 | 2,630        |

* **Observation:** 2022 had the highest order volume, growing consistently from 2020.

---

### **Order Target Comparison**

* **Yearly Order Target (e.g. 2022):** 2,893
* **Monthly Orders vs. Target:** Visualized via a gauge chart
* Issue identified: the gauge was initially showing incorrect values due to misaligned date context in the measure filter. Corrected by adjusting date filter logic.

---

### 🕓 **Previous Year Orders Calculation**

**DAX Measure Used:**

```DAX
Previous Year Orders =
CALCULATE(
   [Total Orders],
   DATEADD('Calendar Lookup'[Date], -1, YEAR)
)
```

**Fix Applied:**
Initial issue occurred because either:

* The 'Calendar Lookup' table wasn’t correctly marked as a date table
* Or slicer/filter context wasn't correctly affecting the measure

Corrected by ensuring:

* 'Calendar Lookup' marked as Date Table in Power BI
* Proper relationship established between Date and Orders

---

### **Revenue, Profit, and Returns Overview**

* **Total Revenue:** \$24.91M
* **Total Profit:** \$10.04M
* **Total Returns:** 1,809
* **Monthly Revenue Trend:** Steady growth with minor seasonal dips
* **Top Product:** *Water Bottle - 30 oz* with 3,983 orders generating \$39.75K revenue

---

##  Customer Insights:

* **17K unique customers**
* **Average Revenue per Customer:** \$1,431
* **Top Customer:** *Mr. Maurice Shan* — 6 orders, \$12.41K revenue
* Segmented customer analysis by **income level** and **occupation**

---

## 📊 Orders by Product Category:

| Category    | Orders |
| :---------- | :----- |
| Accessories | 17,000 |
| Bikes       | 13,900 |
| Clothing    | 7,000  |

---

## 📝 Challenges Faced:

* **Incorrect Previous Year Value**: Due to missing date context or improperly marked date table
* **Gauge Value Issue**: Measure not properly scoped to slicer selection, fixed by refining DAX measure to respect current year selection context

---

##  Key Learnings:

* Always mark date tables explicitly in Power BI models
* Ensure proper slicer interaction and filter context for time-intelligence DAX functions like `DATEADD()`
* Gauge charts require careful alignment of actual vs. target values within the same filter context

---

##  Conclusion:

This Power BI project successfully delivered an interactive and insightful dashboard, enabling AdventureWorks stakeholders to:

* Track orders, revenue, and profit trends
* Compare current and previous year’s performance
* Monitor targets and identify underperforming months
* Analyze customer segmentation and product category performance

---


