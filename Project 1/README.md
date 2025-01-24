# Data Science Salary Dashboard 

![Screenshot 2025-01-24 09384](https://github.com/user-attachments/assets/4f55f9dc-1af8-4386-9388-7873a8f488d0)  

## This dashboard provides insights into data science salaries, focusing on different nations. It answers questions like:  
  1. What is the median salary for data science roles?  
  2. How does salary vary across different job titles?  
  3. What is the most common work schedule?
  4. Which platforms are most used for data science job postings?
## Graphs and their interpretations:
 * Median Salary: Displays the current median salary for data science jobs in the US.
 ```
  =MEDIAN(IF((jobs[job_title_short]=A3)*(jobs[salary_year_avg]<>0)*(jobs[job_country]=country)* 
  (ISNUMBER(SEARCH(schedule,jobs[job_schedule_type]))),jobs[salary_year_avg]))  
 ```
 * Job Title: Shows the distribution of salaries across various data science job titles.
  ```
    =UNIQUE(jobs[job_title_short])
  ```
 * Schedule: Illustrates the proportion of full-time versus part-time positions.
 ```
  =FILTER(S2#,NOT(ISNUMBER(SEARCH("and",S2#)))*(S2#<>0))
 ```

 * Platform: Indicates the platform with the highest number of job postings (in this case, Indeed).
```
  =COUNT(IF((jobs[job_country]=country)*(jobs[salary_year_avg]<>0)*(jobs[job_title_short]=title)*(jobs[job_via]=AD2)* 
   (ISNUMBER(SEARCH(schedule,jobs[job_schedule_type]))),jobs[salary_year_avg]))
```
 * Job Count: Provides the total number of data science job postings analyzed.
 ```
  =COUNT(IF((jobs[job_title_short]=A2)*(jobs[salary_year_avg]<>0)*(jobs[job_country]=country)* 
   (ISNUMBER(SEARCH(schedule,jobs[job_schedule_type]))),jobs[salary_year_avg]))
 ```
## Skills used:
 * Data validation to select from different options.
 * Calculation of median salary.
 * Counting job occurrences across categories.
## Conclusion:
This dashboard offers a quick overview of the data science job market in the US. It can be used to understand salary trends, identify in-demand skills, and make informed career decisions.


