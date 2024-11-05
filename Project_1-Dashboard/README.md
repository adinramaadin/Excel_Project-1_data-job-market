# Excel Salary Dashboard
![Screenshot 2024-11-05 210809](https://github.com/user-attachments/assets/51401d48-3590-4b49-b9f9-b715323f6a12)

## Introduction
This project is a hands-on demonstration of my Excel capabilities, focusing on data analysis and visualization to explore salary trends in data jobs. 
As a final-year Economics student aiming to enter the job market, I built this dashboard to better understand compensation standards across different roles, skills, and regions. 
My goal is to showcase practical, in-demand skills that can help hiring managers see beyond certificates and into the value I can bring to data-centric roles.

### Dashboard File
My final dashboard is in [Salary_Dashboard.xlsx](Salary_Dashboard.xlsx)

### Excel Skills Used
In building this dashboard, I applied a wide range of Excel skills essential for data analysis, visualization, and insights presentation. 
This breakdown of skills highlights my proficiency in core Excel functions valued in data-driven roles:
- **Charts**: For visualizing data effectively and making insights more accessible.
- **Formulas and Functions**:  For organizing, filtering, and calculating key metrics.
- **Data Validation**: To ensure accuracy and consistency within the dataset.
  
### Data Jobs Dataset
The dataset used in this project contains 2023 data science job information and is sourced from
[Luke Barousse's collection, available here](Datasets). It includes detailed data on:
- **Job titles**: Covering a range of positions in the data science field.
- **Salaries**: Annual averages based on country and job type
- **Location**: Regional data, providing insight into geographic salary differences.
- **Skills**: Popular skills associated with specific job titles.

## Dashboard Build
### Charts
#### Data Science Job Salaries - Bar Chart

![image](https://github.com/user-attachments/assets/58008170-833a-4130-ad17-41c2f9d8ce27)

- **Excel Features:** Leveraged the bar chart functionality with custom salary formatting and optimized layout.
- **Design Choice:** Horizontal bar chart format for easy comparison of salaries across job titles.
- **Data Organization:** Sorted by descending salary to improve readability and highlight high-paying roles.
- **Insights Gained:** This visualization allows for a quick understanding of salary trends, revealing that senior positions and engineering roles generally offer higher salaries than analyst positions.

#### Country Median Salaries - Map Chart
  
![image](https://github.com/user-attachments/assets/4eb31159-450f-4e92-9123-2b9900d38497)

- **Excel Features:** Used Excel's map chart for geographic visualization.
- **Design Choice:** Color-coded to display salary levels by region, making geographic disparities more visible.
- **Data Representation:** Median salary per country, where data was available.
- **Visual Enhancement:** Improved readability for instant understanding of salary trends across regions.
- **Insights Gained:** The chart highlights salary disparities globally, helping identify which regions offer the most competitive pay.

### Formulas and Functions

#### Median Salary by Job Titles

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

- **Multi-Criteria Filtering:** This array formula filters by job title, country, schedule type, and excludes blank values.
- **Array Formula:** Utilizes MEDIAN() within an IF() statement to calculate the median based on multiple conditions.
- **Formula Purpose:** Provides specific salary information based on the selected job title, region, and schedule type, enhancing the dashboard’s customizability.

Background Table

![image](https://github.com/user-attachments/assets/4b577554-936d-4458-812f-7e9653af4431)

Dashboard Implementation

![image](https://github.com/user-attachments/assets/32d3ec7a-13c4-4ac8-b2a3-79269e79a1b3)

#### Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- **Unique List Generation:** Uses FILTER() to remove entries with “and” or commas and exclude zero values.
- **Formula Purpose:** Creates a list of unique job schedule types, adding specificity to the analysis.

Background Table

![image](https://github.com/user-attachments/assets/1bb5f660-caac-4425-91f8-4eb292da7938)

Dashboard Implementation:

![image](https://github.com/user-attachments/assets/6ee67c92-63a5-4a7c-b203-c8831dc28f8c)

### Data Validation

#### Filtered List

- **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - User input is restricted to predefined, validated schedule types
    - Incorrect or inconsistent entries are prevented
    - Overall usability of the dashboard is enhanced

![image](https://github.com/user-attachments/assets/0fcfcc0c-f754-4fef-b396-44fd2e0b016e) ![image](https://github.com/user-attachments/assets/9931f74b-edb2-43e2-833a-8dc8acc018a4)

## Conclusion
This project serves as a practical application of my data analysis and Excel skills, developed to meet the needs of job-seekers interested in data roles. 
By visualizing and analyzing salary trends, I’ve gained valuable insights into market expectations, compensation trends, and high-demand roles in data fields.

This project reflects my dedication to learning and provides a strong foundation for my professional aspirations in data and analysis roles.
