
# NOT YET FINISHED....
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

- asd
  
  ![image](https://github.com/user-attachments/assets/cf2b4ed2-9314-4410-9bcc-d636548e070f)

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


#### **So What**

## 3. Which skills are most in-demand for data professionals?

### Skill: Power Pivot

#### Power Pivot

#### Data Model

#### Power Pivot Menu

### Analysis

#### Insights

#### So What

## 4. How much are the top 10 skills compensated?

### Skill: Advanced Charts (Pivot Chart)

#### PivotChart

### Analysis

#### Insights

### So What

## Conclusion
