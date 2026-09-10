# 🔄 Advanced Data Analytics & Market Intelligence Project

## 📌 Introduction

As a data analytics professional, I designed this project to address key strategic questions regarding the modern data science job market. Understanding how skill accumulation impacts compensation, how regional pay benchmarks differ globally, and which technical skills drive maximum market value is essential for both job seekers and hiring entities.

This project delivers an end-to-end data pipeline transformation, relational data modeling, DAX measure creation, and multi-variable analytical reporting using Microsoft Excel's advanced data engine (**Power Query**, **Power Pivot**, and **DAX**).

---

### ❓ Core Business Questions Analyzed

1. **Skill Breadth vs. Pay:** Does acquiring a higher volume of core skills correlate with increased compensation?
2. **Geographic Pay Benchmarks:** How do US median salaries compare against international markets across data roles?
3. **Skill Market Demand:** What are the most frequently requested technical skills across data job postings?
4. **Skill Valuation & ROI:** What is the median financial payoff associated with the top requested skills?

---

### 🛠️ Advanced Excel Architecture Applied

- **🔍 Power Query (ETL):** Multi-table extraction, structural transformation, text cleaning, and data type standardization.
- **💪 Power Pivot & Data Modeling:** Relational star-schema modeling via explicit primary/foreign key relationships (`job_id`).
- **🧮 DAX (Data Analysis Expressions):** Building dynamic measures, filtering contexts (`CALCULATE`), and statistical aggregations (`MEDIAN`).
- **📊 Pivot Tables & Combo Visuals:** Dual-axis chart configurations to plot salary vs. skill frequency.

---

### 📊 Dataset Overview

The underlying dataset captures real-world data science job posting metrics from 2023, comprising millions of data points structured around:

- **👨‍💼 Job Roles:** Standardized classifications (Data Analyst, Data Scientist, Senior Data Engineer, etc.).
- **💰 Salaries:** Annualized median compensation values ($USD).
- **📍 Geographic Footprint:** Country and regional job posting metadata.
- **🛠️ Skill Requirements:** Itemized skill tags mapped to specific job postings.

---

## 1️⃣ Do More Skills Command Higher Compensation?

### 🔍 Technical Execution: Power Query (ETL Pipeline)

#### 📥 Extraction
- Ingested the raw dataset (`data_salary_all.xlsx`) via Power Query, staging two isolated queries:
    - 🗃️ `data_jobs_all`: Primary transactional entity containing salary, role, and location data.
    - 🔧 `data_job_skills`: Relational bridge table mapping skill tags to unique job identifiers.

#### 🔄 Transformation
- Applied structural transformations: updated column data types, trimmed whitespace, removed null entries, and filtered out non-analytical job classifications.
    - 📊 `data_jobs_all` Transformation View:

        ![2_Project_Analysis_Screenshot1.png](/0_Resources/Images/2_Project_Analysis_Screenshot1.png)

    - 🛠️ `data_job_skills` Transformation View:

        ![2_Project_Analysis_Screenshot2.png](/0_Resources/Images/2_Project_Analysis_Screenshot2.png)

#### 🔗 Loading
- Loaded transformed queries directly into the Excel Data Model as clean relational tables.
    - 📊 `data_jobs_all` Staging:

        ![2_Project_Analysis_Screenshot3.png](/0_Resources/Images/2_Project_Analysis_Screenshot3.png)

    - 🛠️ `data_job_skills` Staging:

        ![2_Project_Analysis_Screenshot4.png](/0_Resources/Images/2_Project_Analysis_Screenshot4.png)

---

### 📊 Analytical Findings

#### 💡 Key Insights
- **Positive Correlation:** A strong positive relationship exists between skill count requirements and median compensation, most notably within Senior Data Engineering and Machine Learning roles.
- **Specialization Premium:** Roles requiring narrower, baseline skill sets (e.g., Business Analyst) report lower median pay, proving that specialized, multi-tool proficiencies command a clear market premium.

    ![2_Project_Analysis_Chart1.png](/0_Resources/Images/2_Project_Analysis_Chart1.png)

#### 🎯 Strategic Implication
- Professionals aiming to transition into higher compensation tiers must focus on acquiring complementary advanced skills rather than relying on a single foundational tool.

---

## 2️⃣ Regional Salary Disparities: US vs. International

### 🧮 Technical Execution: Power Pivot & DAX Measures

#### 📈 Dynamic Pivot Table Construction
- Engineered a Pivot Table powered by the underlying Data Model.
- Formatted `job_title_short` across rows and mapped `salary_year_avg` to calculate regional benchmarks.
- Created an explicit DAX measure to isolate US-specific median compensation:
    ```dax
    US Median Salary := CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States"
    )
    ```

#### 🧮 Global Baseline DAX Measure
- Formulated the baseline global median salary measure:
    ```dax
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

---

### 📊 Analytical Findings

#### 💡 Key Insights
- **Global Role Hierarchy:** Senior Data Engineers and Data Scientists maintain dominant median compensation levels across both US and international markets.
- **Geographic Pay Gap:** A substantial pay premium exists in US-based roles across all technical titles, driven by the concentration of enterprise technology firms and capital allocation.

    ![2_Project_Analysis_Chart2.png](/0_Resources/Images/2_Project_Analysis_Chart2.png)

#### 🎯 Strategic Implication
- Geographic variations must be factored into compensation benchmarking, remote work evaluations, and international talent sourcing strategies.

---

## 3️⃣ Market Demand: Most Requested Technical Skills

### 🔧 Technical Execution: Data Modeling in Power Pivot

#### 💪 Relational Data Modeling
- Connected discrete data tables into a cohesive Data Model within Power Pivot using the primary/foreign key `job_id`.

#### 🔗 Model Architecture
- Established a **1-to-Many (1:*)** relationship between `data_jobs_all` and `data_jobs_skills`.

    ![2_Project_Analysis_Screenshot5.png](/0_Resources/Images/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Management
- Used the Power Pivot management interface to define explicit measures and structure relational metadata.

    ![2_Project_Analysis_Screenshot6.png](/0_Resources/Images/2_Project_Analysis_Screenshot6.png)

---

### 📊 Analytical Findings

#### 💡 Key Insights
- **Core Market Pillars:** `SQL` and `Python` dominate global job postings as mandatory core proficiencies across data engineering, analytics, and data science.
- **Cloud Expansion:** Enterprise cloud platforms (`AWS`, `Azure`) exhibit significant demand growth, highlighting the industry-wide migration toward scalable cloud infrastructure.

    ![2_Project_Analysis_Chart3.png](/0_Resources/Images/2_Project_Analysis_Chart3.png)

#### 🎯 Strategic Implication
- Mastering SQL and Python remains non-negotiable for entering the analytics space, while cloud infrastructure proficiencies serve as key differentiators for career advancement.

---

## 4️⃣ Financial Valuation of Top Requested Skills

### 📊 Technical Execution: Dual-Axis Combo Pivot Charts

#### 📈 Advanced Chart Architecture
- Constructed a Combo Pivot Chart integrating financial returns and demand frequency:
    - 🪙 **Primary Axis (Clustered Column):** Median Salary ($USD)
    - 👍 **Secondary Axis (Line with Diamond Markers):** Skill Likelihood (%)
- Formatted chart elements by stripping gridlines, applying distinct data callouts, and refining visual contrast for executive readability.

---

### 📊 Analytical Findings

#### 💡 Key Insights
- **High-Value Returns:** Proficiencies in `Python`, `SQL`, and enterprise database technologies (`Oracle`) directly correlate with the highest median salary brackets.
- **Utility Skills vs. High Compensation:** Standard office productivity tools (`PowerPoint`, `Word`) register low demand likelihood and significantly lower median compensation.

    ![2_Project_Analysis_Chart4.png](/0_Resources/Images/2_Project_Analysis_Chart4.png)

#### 🎯 Strategic Implication
- To maximize career ROI, professionals should prioritize high-value programmatic and database management skills over general administrative software.

---

## 🎯 Conclusion

This project successfully demonstrates the power of Excel's modern data analytics stack (**Power Query**, **Power Pivot**, and **DAX**) in solving complex, multi-dimensional business queries. By transforming raw job posting records into a structured relational model, the analysis provides clear, actionable market insights: specialized skills, US market proximity, and core programmatic competencies (`Python`, `SQL`, Cloud) are the definitive drivers of premium compensation in the data industry.

---

## 👨‍💻 Author & Credits

**Abdulkhadir Salah Nor (Abdulnor)**
- 🌐 **GitHub:** [Abdulnor97](https://github.com/Abdulnor97)
- 💼 **Role:** Data Analytics & Financial Dashboarding Specialist
- 🛠️ **Technologies:** Microsoft Excel (Power Query, Power Pivot, DAX, Dynamic Modeling), VS Code, Git & GitHub
