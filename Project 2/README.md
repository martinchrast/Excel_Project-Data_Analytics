# Project 2 Analysis
## Introduction

As a job seeker, I’ve always been intrigued by the scarcity of data on the best job opportunities and most in-demand skills in the data science field. I wanted to explore what top employers look for and how to maximize earning potential.

### Question to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**


### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Pivot Tables**
- **Pivot Charts**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023.

It includes detailed information on:

- **Job Titles**
- **Salaries**
- **Locations**
- **Skills**

## 1. **Do more skills get you better pay?**

### **Skill: Power Query (ETL)**

**Extract**
- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
  - First one with all the data jobs information.
  - The second listing the skills for each job ID.
 
**Transform**
- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
  - **data_jobs_all**
 

  ![image](https://github.com/user-attachments/assets/ad99a40c-5f75-4925-9171-0f5b8e3092d3)

  - **data_job_skills**
 
    
  ![image](https://github.com/user-attachments/assets/7c26e57d-487f-4ddf-a4c8-bb515bf7415f)

**Load**

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
   - **data_jobs_all**
     
   ![image](https://github.com/user-attachments/assets/cd252d59-ec63-4dab-b62e-811d124f5f39)

   - **data_job_skills**
     
![image](https://github.com/user-attachments/assets/61a3be08-390a-4a49-95d1-e46cc76d6a52)

  ### Analysis

  **Insight**
  - There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
 
  - Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

![image](https://github.com/user-attachments/assets/a484f100-8e59-4c2a-9b74-c2905acabcfd)

**So What ?**

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2. **What’s the salary for data jobs in different regions?**

### Skills: PivotTables & DAX

**Pivot Table**

- I created a PivotTable using the Data Model I created with Power Pivot.
- I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- Then I added new measure to calculate the median salary for United States jobs.
```
=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States")
```

**DAX**

- To calculate the median year salary I used DAX.
```
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
```

### Analysis

**Insights**
- Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

![image](https://github.com/user-attachments/assets/2f527c97-78ad-423f-be77-8bbaff75a27f)


**So What ?**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3. **What are the top skills of data professionals?**

### **Skill: Power Pivot**

**Power Pivot**
- I created a data model by integrating the `data_jobs_all` and `data_jobs_skills`tables into one model.
- Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

**Data Model**
- I created a relationship between my two tables using the `job_id` column.

![image](https://github.com/user-attachments/assets/05963f8a-5edb-4ba1-97b3-3d43436b177b)

**Power Pivot Menu**
- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

![image](https://github.com/user-attachments/assets/7bfcdb2c-aee7-47e8-8841-1cbb6faab068)

### Analysis

**Insights**
- SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

![image](https://github.com/user-attachments/assets/e4f6e29f-18a7-49cc-ab74-07036762b19b)


**So What ?**
- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4. **What’s the pay of the top 10 skills?**

### **Skill: Advanced Charts (Pivot Chart)**

**PivotChart**

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
  - **Primary Axis:** Median Salary (as a Clustered Column
  - **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

![image](https://github.com/user-attachments/assets/cd274a8d-27bd-44fd-9ee7-9e60c8ffb2a9)


**So What ?**
- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

### **Conclusion**

As part of this Excel-based project, I analyzed real-world job postings to uncover key insights into salary trends and skill demand in the data science job market. By examining job titles, salaries, locations, and essential skills, I identified patterns that shed light on industry expectations and earning potential. 

Utilizing Excel features such as Power Query, PivotTables, DAX, and data visualization, I discovered strong correlations between higher salaries and proficiency in Python, SQL, and cloud technologies.

I hope this analysis provides valuable insights for data professionals looking to understand market trends and make informed career decisions.




