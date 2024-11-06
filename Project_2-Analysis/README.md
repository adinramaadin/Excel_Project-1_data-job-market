
# Project 2 Analysis

## Introduction

As someone who’s been on the job search myself, I was surprised by how little data exists on the best roles and skills in the data science market. This gap motivated me to analyze what skills top employers seek and how these skills impact salary potential.

### Questions to Analyze

In exploring the data science job market, I focused on these questions:

1. **Do more skills lead to better pay?**
2. **What are the salary ranges for data jobs in various regions?**
3. **Which skills are most in-demand for data professionals?**
4. **How much are the top 10 skills compensated?**

### Excel Skills Used

For this analysis, I applied several Excel skills essential to data processing and visualization:

- **Pivot Tables**
- **Pivot Charts**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Power Pivot**

### Data Jobs Dataset

The dataset used in this project contains 2023 data science job information and is sourced from
[Luke Barousse's collection, available here](Datasets). It includes detailed data on:

It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## 1. Do more skills lead to better pay?

### Skill: Power Query (ETL)

#### Extract

- Using Power Query, I extracted data from the original file (`data_salary_all.xlsx`) and set up two queries:
    - The first query contains all job information.
    - The second lists skills associated with each job ID.

#### Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
  - data_jobs_all
    
    ![image](https://github.com/user-attachments/assets/1ebb2f03-7305-4bc7-acdf-8d700899b40e)
    
  - data_job_skills

    ![image](https://github.com/user-attachments/assets/658219b4-6a26-4346-89c9-9ff235520091)


#### Load
- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
  - data_jobs_all
    ![image](https://github.com/user-attachments/assets/3cdeb533-e773-4db7-acae-470f929ac53d)

  - data_jobs_skills
    ![image](https://github.com/user-attachments/assets/5f5ee032-7f5f-4870-b30e-d5e8df6f8dc0)


### Analysis

#### Insights

- There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.
  
  ![image](https://github.com/user-attachments/assets/7bebc43c-3bcc-479d-adcc-b04f796593f3)

#### So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2. What are the salary ranges for data jobs in various regions?

### Skills: PivotTables & DAX

#### Pivot Table

- I created a PivotTable using the Data Model I created with Power Pivot.
- I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- Then I added new measure to calculate the median salary for United States jobs.
  
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

- Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    ![image](https://github.com/user-attachments/assets/0b1be758-5ba3-462a-a4d4-521dccc421e0)

#### **So What**

These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3. Which skills are most in-demand for data professionals?

### Skill: Power Pivot

#### Power Pivot

- I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### Data Model

- I created a relationship between my two tables using the `job_id` column.

  ![image](https://github.com/user-attachments/assets/583b6cb7-70ed-4217-8a2f-4e7adf837f13)

#### Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.
  
  ![image](https://github.com/user-attachments/assets/472c1ed0-7dc2-4f16-b7c8-6348e09af858)


### Analysis

#### Insights

- SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

  ![image](https://github.com/user-attachments/assets/77a40a06-c604-425b-a8c0-38cee999facb)


#### So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4. How much are the top 10 skills compensated?

### Skill: Advanced Charts (Pivot Chart)

#### PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - **Primary Axis:** Median Salary (as a Clustered Column)
    - **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### Analysis

#### Insights

- Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

  ![image](https://github.com/user-attachments/assets/9db778e2-aa8b-476d-a094-681393d747cc)

### So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion
