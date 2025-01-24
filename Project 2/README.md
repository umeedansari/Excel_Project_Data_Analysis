# Project 2 Analysis

## Introduction

As a former job seeker, I’ve always been surprised by the lack of data exploring the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how to land more pay.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

-  Pivot Tables
-  Pivot Charts
-  DAX (Data Analysis Expressions)
-  Power Query
-  Power Pivot
## 1. Do more skills get you better pay?

###  Skill: Power Query (ETL)

####  Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
      
      ![Screenshot 2025-01-24 102914](https://github.com/user-attachments/assets/4d0f1d99-dc39-44a5-a668-e1b488ee1522)  

   - 🔧 The second listing the skills for each job ID.
     
       ![Screenshot 2025-01-24 102938](https://github.com/user-attachments/assets/b7a6f849-9538-4322-b4de-7de013843830)

###  Analysis

####  Insights

-  There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
-  Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    ![Screenshot 2025-01-24 101124](https://github.com/user-attachments/assets/77bb6ad5-d28b-4180-abcc-b0070a4f2d20)


####  So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️. What’s the salary for data jobs in different regions?

###  Skills: PivotTables & DAX

#### Pivot Table

-  I created a PivotTable using the Data Model I created with Power Pivot.
-  I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
-  Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```
####  DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

###  Analysis

####  Insights

-  Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
-  The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    ![Screenshot 2025-01-24 101155](https://github.com/user-attachments/assets/b0472748-5f9c-4ab1-9c93-9bc5e153e7fa)


#### ** So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️. What are the top skills of data professionals?

###  Skill: Power Pivot

####  Power Pivot

-  I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
-  Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

####  Data Model

- I created a relationship between my two tables using the `job_id` column.

    ![Screenshot 2025-01-24 104046](https://github.com/user-attachments/assets/80a516a4-70a1-49a8-afb7-85dd831cc626)


####  Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    ![Screenshot 2025-01-24 104257](https://github.com/user-attachments/assets/4d75c004-a44b-4fc8-999b-47259f00b588)


### Analysis

#### Insights

-  SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
-  Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    ![Screenshot 2025-01-24 101045](https://github.com/user-attachments/assets/a3c6d227-76ea-452b-ac0a-25ed7409ff41)


#### So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️. What’s the pay of the top 10 skills?

###  Skill: Advanced Charts (Pivot Chart)

####  PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    -  **Primary Axis:** Median Salary (as a Clustered Column)
    -  **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

###  Analysis

#### Insights

-  Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
-  Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    ![Screenshot 2025-01-24 101228](https://github.com/user-attachments/assets/8bfaeb06-7b25-43fa-9e6c-e23ef0e44fac)


### So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

As a data enthusiast and former job seeker, I embarked on this Excel-based project to uncover valuable insights about the data science job market. Using a dataset I've curated from real-world job postings, I analyzed job titles, salaries, locations, and essential skills. By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies. 

I hope this project serves as a practical guide for data professionals and provides an overview of the skills needed for higher-paying roles.


