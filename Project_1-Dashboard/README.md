# 📊 Excel Data Jobs & Salary Dashboard

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## 📌 Introduction

This interactive **Excel Data Jobs Salary Dashboard** was created to help job seekers, analysts, and professionals investigate salary benchmarks across various data roles. The objective is to analyze compensation patterns and ensure professionals can evaluate salary expectations based on role, location, and employment type.

The analysis is based on real-world data science and analytics job posting data, covering key fields such as job titles, annual median salaries, geographic locations, and required technical skills.

### 📂 Dashboard File
My final dashboard is available here: [1_Salary_Dashboard.xlsx](https://1drv.ms/x/c/A6A8FE4EE3EE4694/IQB1qjC8rOzaSa1dxDGczaPuAfXArP7xvOUUz90Wm9Cgdl8?e=1umeJN).

### 🛠️ Excel Skills Used

The following advanced Excel techniques were applied throughout the project:

- **📉 Custom Charts:** Visualizing salary distributions and geographic trends.
- **🧮 Dynamic Formulas & Functions:** Dynamic array formulas for multi-criteria metrics.
- **❎ Data Validation:** Restricting user inputs to clean, automated dynamic lists.

### 📊 Data Jobs Dataset

The dataset used for this project contains real-world data science job market data from 2023. It includes detailed information on:

- **👨‍💼 Job titles:** Data Analyst, Data Engineer, Data Scientist, Machine Learning Engineer, etc.
- **💰 Salaries:** Annual median compensation metrics ($USD).
- **📍 Locations:** Regional and international job posting locations.
- **🛠️ Skills:** High-demand technical skills required per role.

---

## 🏗️ Dashboard Build

### 📉 Charts & Visualizations

#### 📊 Data Science Job Salaries - Bar Chart

<img src="/0_Resources/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features:** Utilized a horizontal bar chart with custom currency formatting ($K) for clear comparison.
- 🎨 **Design Choice:** Sorted job titles in descending order of median salary to instantly highlight top-paying roles.
- 📉 **Data Organization:** Organized roles cleanly to compare specialized engineering roles against analyst positions.
- 💡 **Insights Gained:** Senior roles, Data Engineers, and Machine Learning Engineers command significantly higher median salaries compared to general analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](/0_Resources/Images/1_Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features:** Leveraged Excel's dynamic map chart feature to display regional compensation levels globally.
- 🎨 **Design Choice:** Applied a color gradient to visually distinguish high vs. low compensation regions.
- 📊 **Data Representation:** Displays the median salary for each country present in the dataset.
- 👁️ **Visual Enhancement:** Provides an intuitive geographic view of global compensation disparities.
- 💡 **Insights Gained:** Highlights major international salary gaps and helps evaluate location-specific earnings expectations.

---

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```excel
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
  )
)
```

🎯 Conclusion & Key Findings
This dashboard successfully transforms raw data job market data into actionable compensation insights. By leveraging advanced array formulas, dynamic data validation, and interactive visuals, the dashboard enables users to make informed career decisions and understand how role specialization, geographic location, and work schedule impact earning potential.

👨‍💻 Author
Developer: Abdulnor

Tools: Microsoft Excel (Microsoft 365) & Visual Studio Cod




