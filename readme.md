# 🏥 ICU Data Warehouse – Optimizing Critical Care with MIMIC-III

This project delivers a fully functional healthcare data warehouse using the **MIMIC-III Clinical Database** to enhance **ICU resource management**, **mortality prediction**, and **medication tracking**. Built using **Snowflake**, **SQL**, and **Power BI**, the solution follows an ELT architecture with structured modeling layers and automated BI insights.

---

## 📌 Project Objectives

- Improve ICU resource allocation through centralized data warehousing.
- Analyze patient outcomes (mortality, LOS) and medication administration trends.
- Support hospital planning with data-driven insights on ICU transfers and occupancy.

---

## 🧱 Architecture Overview

**Platform**: Snowflake  
**Data Layers**:  
- `RAW` – Direct CSV ingestion  
- `STAGE` – Cleansing, type casting, and enrichment  
- `MODELED` – Star schema with fact and dimension tables

---

## 📂 Data Sources (MIMIC-III CSVs)

- `ADMISSIONS.csv` – Admission, discharge, diagnosis, and mortality
- `ICUSTAYS.csv` – ICU stay timing and units
- `PATIENTS.csv` – Demographics and expiration
- `PRESCRIPTIONS.csv` – Drug records and routes
- `TRANSFERS.csv` – Patient movement across care units
- `D_ICD_PROCEDURES.csv` – Procedure metadata

---

## 🔧 ETL Process

**Tools Used**: Snowflake SQL, COPY INTO, Views  
**Steps**:

1. **Extract**: Upload CSVs to Snowflake stages.
2. **Load**: Populate raw tables using `COPY INTO`.
3. **Transform**:
   - Clean missing values and nulls (e.g., set default dates)
   - Derive key attributes (e.g., age, ICU readmission flag)
   - Build star schema using views and tables

---

## 🌟 Star Schema Design

### Fact Tables
- `fact_icu_stay` – LOS, admission type, mortality
- `fact_medication_admin` – Drug usage and readmissions
- `fact_transfer` – Unit movement durations

### Dimension Tables
- `dim_patient` – Gender, DOB, status
- `dim_admission` – Admission details
- `dim_procedure` – ICD-9 metadata
- `dim_service` – Service transitions
- `dim_caregiver` – Care provider roles

---

## 📊 BI Dashboards (Power BI)

### 1. ICU Mortality & Length of Stay
- Analyze mortality by age group, unit type, admission type
- Identify patterns in prolonged ICU stays

![image](https://github.com/user-attachments/assets/7b33dd29-14fb-4187-87a2-011fead05ad6)


### 2. Medication Usage Trends
- Track high-risk drugs across demographics and seasons
- Filter by ICU type, route, and dosage patterns
  
![image](https://github.com/user-attachments/assets/ea96f5f3-9518-4be7-a9b0-f814ed6d06b0)

### 3. Hospital Resource Utilization
- ICU occupancy rates and care unit capacity
- Weekday vs. weekend trends, seasonal surges

![image](https://github.com/user-attachments/assets/318143b3-2306-4797-806a-ba111f34f688)

> 💡 **All dashboards are built directly on Snowflake-modeled views using live connections.**

---

## ⚙️ Technical Highlights

- Used `DATE_DIFF` and `CASE` logic for derived fields like LOS and readmission
- Applied `COUNT_IF`, `COALESCE`, and aggregation functions for data integrity
- Modeled reusable, performance-optimized views for BI connectivity
- Followed ELT best practices to ensure traceability and minimal data duplication

---

## 📈 Outcomes

- Reduced analytical overhead with a structured data model
- Enabled quick querying of ICU trends and medication risks
- Provided real-time dashboard access to clinical stakeholders

---

## 🔮 Future Work

- Add real-time ingestion for operational decisions
- Integrate ML for mortality or LOS prediction
- Build clinician-facing portal for dashboard access

---

## 👥 Team

**Project Team: Warehouse Wizards**  
Bhavesh Purohit • Simran Ghandhi • Khushal Modi  
Syracuse University – IST 722, Spring 2025

---

## 📎 Resources

- MIMIC-III Database: https://physionet.org/content/mimiciii/
- Power BI Dashboards: *[Insert dashboard links when hosted]*

---





