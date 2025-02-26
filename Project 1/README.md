# Excel Salary Dashboard
![project1header](https://github.com/user-attachments/assets/2e35e54d-c895-40a8-91a5-87da849de916)

## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated.

The data is from an Excel course, which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, location, and essnetial skills that are presented here.

### Dashboard File

My final dashboard is in [Project 1](https://github.com/martinchrast/Excel_Project-Data_Analytics/tree/main/Project%201)

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Charts**
- **Formulas nd Functions**
- **Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is avaiable via Excel course,
which provides foundation for analyzing data using Excel. It includes detailed information on:

- Job titles
- Salaries
- Locations
- Skills

## Dashboard Build

### Charts

**Data Science Job Salaries - Bar Chart**

![1](https://github.com/user-attachments/assets/e884e409-b2fe-4df4-a0f9-eccb951fa9ee)

- **Excel Features**: Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- **Design Choice**: Horizontal bar chart for visual comparison of median salaries.
- **Data organization**: Sorted titles by descending salary for improved readability.
- **Insights Gained**: This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

**Country Median Salaries - Map Chart**


![2](https://github.com/user-attachments/assets/0978d32c-cee8-4494-84f0-b0511378d6cb)

- **Excel Features**: Utilized Excel's map chart feature to plot median salaries globally.
- **Design Choice**: Color-coded map to visually differentiate salary levels across regions.
- **Data representation**: Plotted median salary for each country with available data.
- **Visual Enhancement**: Improved readability and immediate understanding of geographic salary trends.
- **Insights Gained**: Enables quick grasp of global salary disparities and highlights high/low salary regions.

### Formulas and Functions

**Median Salary by Job Titles**
```
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

