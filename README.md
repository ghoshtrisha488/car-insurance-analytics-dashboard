# 🚗 Car Insurance Analytics & Performance Dashboard

![Dashboard Preview]
<img width="1911" height="1010" alt="Screenshot 2026-11-02 115016" src="https://github.com/user-attachments/assets/18f3f6db-b91d-47fd-a0c1-28dcc26d63b5" />
<img width="1912" height="1011" alt="image" src="https://github.com/user-attachments/assets/e5715d3d-3c5f-4227-887c-b79d9430f24a" />


## 📌 Project Overview
This repository contains an end-to-end Power BI analytics project focused on analyzing **Car Insurance Claims, Customer Risk Profiles, and Demographics**. The goal of this dashboard is to help insurance underwriters, risk managers, and business stakeholders monitor claims performance, identify high-risk customer segments, track loss ratios, and optimize portfolio profitability.

---

## 📊 Key Business Questions Answered
* **Claims Performance:** What is the total claim amount, average claim payout, and overall claim frequency?
* **Risk Identification:** Which age groups, vehicle types, or driving history profiles carry the highest risk of filing a claim?
* **Financial Impact:** What is the relationship between policy premiums collected versus claim payouts (Loss Ratio)?
* **Customer Segmentation:** How do claim trends vary by demographic factors such as marital status, income group, location, and vehicle usage (Private vs. Commercial)?

---

## 🛠️ Data Architecture & Pipeline
1. **Data Source:** Cleaned tabular dataset containing policyholder attributes, claim records, vehicle details, and coverage metrics.
2. **Data Cleaning & Transformation (Power Query):**
   * Imputed missing values in customer demographic attributes.
   * Standardized date fields, policy tenure durations, and categorical labels.
   * Created custom conditional columns for age groups (e.g., *<25*, *25-45*, *46+*) and claim severity tiers.
3. **Data Modeling:**
   * Structured a **Star Schema** with a centralized `Fact_Claims` table connected to dimension tables (`Dim_Customer`, `Dim_Vehicle`, `Dim_Date`, `Dim_Policy`).
   * Configured 1-to-many single-direction relationships to maintain fast filtering and accurate calculations.

---

## 📐 Key DAX Measures & Metrics

Here are some of the key custom DAX calculations implemented in the model:

* **Total Claims Count:**
  ```dax
  Total Claims = COUNTROWS('Fact_Claims')
