# Pewlett-Hackard-Analysis: "The Silver Tsunami"
## Overview
Pewlett-Hackard has several thousand employees that has many that are beginning to retire at a rapid rate. Bobby, the HR Analyst, and I used SQL to organize the data given into tables for analysis. This analysis looks at two things: the number of retiring employees by title and employees who would be eligible to participate in a mentorship program.


#### Resources used:
Software used: PostgreSQL as the relational databse and pgAdmin as the open source administrator for PostgreSQL

Data sources: employees.csv, depy_emp.csv, titles.csv 


## Results
There were 4 points in this analysis: Retirement Titles, Unique Titles, Retiring Titles, and Mentorship Eligibility.

- Retirement Titles

  - Using a SQL query, we joined the employee number, first name, and last name from the employee table with the title, from date, and to date out of the title table into a new "retirement_titles" table to get the titles of the employees who were born between January 1, 1952 and December 31, 1955, thereby eligible for retirement.


<img src =Resources\retirement_titles.png>

- Unique Titles

  - Due to some employees having multiple titles throughout their carrer, We then needed to filter out the duplicates, keeping only the most recent "unique" title. (This was accomplished utilizing the "DISTINCT ON" statement in SQL.)


<img src=Resources\unique_titles.png> 

<img src= Resources\DISTINCT_ON_code.png> 

- Retiring Titles

  - Once the titles were filtered, we created another query, using the "COUNT" statment,  to determine the number of retiring employees by department




<img src= Resources\retiring_titles_count.png>

<img src= Resources\COUNT_code.png>

- Mentorship Eligibility

  - As the final piece, we joined the 3 tables, employee, titles, and dept_emp, and then filtered the new table by their birth date (if during the year 1965) and if they are still employeed (the "to_date" = '9999-01-01')


<img src= Resources\mentorship_eligibility.png>

<img src= Resources\mentorship_eligibility_code.png>




## Summary
Based on the above analysis, there are 90,398 individuals eligible for retirement. AS the employees retire, the greatest impact will be in the Senior Engineer and Senior Staff areas, which will have 29,414 and 28,254 voids respectively. With only 1,549 mentorship eligible employees, based on the current qualifications, there are not enough to mentoer the next generation of employees.

To help recover from this "Silver Tsunami":
- I would recommend expanding the requirements for mentorship to a longer range of dates (1960-1965), this would give a much larger base to mentor from (93,756 mentors). This would need to be revisited annually to assure the company maintains enough in the mentorship pool.

<img src= Resources\expanded_mentorship_code.png>

- With the expanded mentorship, they will need to look into the qualifications for the titles and adjust, where necessary, to keep the ratios where they need to be. Based on the new dates, 

<img src= Resources\new_COUNT.png>