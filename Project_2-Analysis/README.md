
# Project 2 Analysis

## Introduction

As someone actively navigating the job market, I noticed a lack of comprehensive data on the most valuable roles and skills within the data science industry. This gap inspired me to conduct an analysis on what skills top employers seek and how they impact salary potential.

### Questions to Analyze

This analysis addresses a notable gap in data science career insights, exploring which skills and roles are most valued by top employers, and how these skills influence salary potential. My analysis seeks to answer critical questions relevant to job-seekers, hiring managers, and organizations:

1. **Do more skills lead to better pay?**
2. **What are the salary ranges for data jobs in various regions?**
3. **Which skills are most in-demand for data professionals?**
4. **How much are the top 10 skills compensated?**

### Excel Skills Used

This project demonstrates my proficiency with the following Excel tools, essential for in-depth data analysis:

- **Pivot Tables**: For summarizing and analyzing large datasets.
- **Pivot Charts**: For visualizing salary data and skill distributions.
- **DAX (Data Analysis Expressions)**: For custom calculations on salary insights.
- **Power Query**: For extracting, transforming, and loading data (ETL) efficiently.
- **Power Pivot**: For building a data model and creating relationships across tables.
  
### Data Source

The dataset used in this project contains 2023 data science job information and is sourced from
[Luke Barousse's collection, available here](Datasets). It includes a comprehensive view of the data science job market with detailed information on:

It includes detailed information on:

- **Job titles:** Representing various data roles.
- **Salaries:** Reflecting average annual and hourly pay.
- **Locations:** Showing salary variations across regions.
- **Skills:** Listing technical competencies associated with each role.

## 1. Do more skills lead to better pay?

**Objective:** To determine if a higher number of skills correlates with increased pay for data professionals.

**Tools Used:** Power Query, PivotTables

#### Process
- **Extract**: Using Power Query, I pulled data from the original file (`data_salary_all.xlsx`) and organized it into two queries:
  - **data_jobs_all**: Comprehensive job details.
  - **data_job_skills**: Skills associated with each job ID.
  
#### Transform

- I refined the queries by adjusting column types, removing unnecessary fields, and cleaning text entries to enhance readability.
  - data_jobs_all
    
    ![image](https://github.com/user-attachments/assets/1ebb2f03-7305-4bc7-acdf-8d700899b40e)
    
  - data_job_skills

    ![image](https://github.com/user-attachments/assets/658219b4-6a26-4346-89c9-9ff235520091)

#### Load
- Finally, I loaded the transformed data into the workbook for analysis, laying the groundwork for further insights.
  - data_jobs_all
    ![image](https://github.com/user-attachments/assets/3cdeb533-e773-4db7-acae-470f929ac53d)

  - data_jobs_skills
    ![image](https://github.com/user-attachments/assets/5f5ee032-7f5f-4870-b30e-d5e8df6f8dc0)


#### Insights

- A positive correlation emerged between the number of skills listed in job postings and the median salary, particularly for roles like Senior Data Engineer and Data Scientist.
- In contrast, roles requiring fewer specialized skills, like Business Analyst, tend to offer lower salaries.
  
  ![image](https://github.com/user-attachments/assets/7bebc43c-3bcc-479d-adcc-b04f796593f3)

#### **Key Takeaways**

- This trend underscores the value of acquiring multiple relevant skills for individuals aiming to secure higher-paying roles.

## 2. What are the salary ranges for data jobs in various regions?

**Objective**: To analyze how salaries vary by region for different data roles.

**Tools Used**: PivotTables, DAX

#### Process

- Created a PivotTable and calculated the median salary by region using DAX. For instance, a measure for median US salaries was calculated as follows:
  
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### Analysis

#### Insights

-High-paying roles like Senior Data Engineer and Data Scientist command competitive salaries both within and outside the US, with a notable salary disparity between regions, particularly in high-tech roles.

    ![image](https://github.com/user-attachments/assets/0b1be758-5ba3-462a-a4d4-521dccc421e0)

#### **Key Takeaways**

These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3. Which skills are most in-demand for data professionals?

**Objective**: To identify the skills that employers prioritize in data science roles.

**Tools Used**: Power Pivot

#### Process

- Created a data model by linking `data_jobs_all` and `data_jobs_skills` through Power Pivot, establishing relationships via the `job_id` field.

#### Data Model

- I created a relationship between my two tables using the `job_id` column.

  ![image](https://github.com/user-attachments/assets/583b6cb7-70ed-4217-8a2f-4e7adf837f13)

#### Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.
  
  ![image](https://github.com/user-attachments/assets/472c1ed0-7dc2-4f16-b7c8-6348e09af858)

### Analysis

#### Insights

- SQL and Python were the most frequently listed skills, reflecting their foundational role in data processing.
- Cloud-related skills, including AWS and Azure, also ranked highly, aligning with industry trends towards cloud computing.

  ![image](https://github.com/user-attachments/assets/77a40a06-c604-425b-a8c0-38cee999facb)

#### Key Takeaway

- Understanding high-demand skills is crucial for job-seekers and helps educational institutions prioritize relevant training programs.

## 4. How much are the top 10 skills compensated?

**Objective**: To examine how different skills impact salary, focusing on the top 10 skills.

**Tools Used**: PivotCharts

#### Process

- I designed a combo PivotChart to display the median salary and likelihood (%) of each top skill
    - **Primary Axis:** Median Salary (as a Clustered Column)
    - **Secondary Axis:** Skill Likelihood (as a Line with Markers)
    
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### Analysis

#### Insights

- Skills like Python, Oracle, and SQL are associated with higher salaries, indicating their premium value in the tech sector.
- Skills with lower specialization, such as PowerPoint, tend to correlate with lower-paying roles.

  ![image](https://github.com/user-attachments/assets/9db778e2-aa8b-476d-a094-681393d747cc)

### Key Takeaway

- Investing in high-impact skills, particularly SQL and Python, is beneficial for professionals targeting well-compensated roles in data science.

## Conclusion

This project offers actionable insights into the data science job market, identifying skills, roles, and regional salary trends that can guide both job-seekers and organizations. Through this hands-on analysis, I demonstrate my ability to transform data into meaningful insights, showcasing the technical skills and analytical thinking required in data-driven roles.
