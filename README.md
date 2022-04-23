# Pewlett-Hackard-Analysis

## Overview of the analysis: 
The analysis will help the management to be able to plan ahead and prepare for the upcoming load of retirement resulting in a major staff shortage.

## Results: 
In order to help PH prepare for the silver tsunami that they are facing, we need to know the followings:


* Retiring Employees and their Titles
* Unique Retiring Employees and their most recent Job Title
* Number of Retiring Employees by Title
* Employees Eligible for Mentorship Program

#### Retiring Employees and their Titles
In this analysis we first created a data file containing the employees whose birth year was between 1952 and 1955 as these will be the employees who will be retiring in the next little while as they reach the retirement age. 

![Retirement_Titles](/images/retirement_titles.png "Retirement Titles")

#### Unique Retiring Employees and their most recent Job Title
We can see that there are some names that appear more than one time, showing all the positions ot titles they have held in PH since they were employed. In order to get a more concise restult, we will only show their latest titles in the unique_titles report:

![Unique_Titles](/images/unique_titles.png "Unique Titles")

#### Number of Retiring Employees by Title

Now, knowing their names, we also would like to find out how many of them would be retiring, but better yet, we would like to know the number of the retiring employees by their most recent job title. For this report we created the retiring_titles report:

![Retiring_Titles](/images/retiring_titles.png "Retiring Titles")

#### Employees Eligible for Mentorship Program
Having all the data, PH HR departement can better plan for future hiring/promotion to replace the outgoing employees. But the new employees need training! So, who better can train the replacing employees than the retiring employees. So Pewlett Hackard will have a mentorship program, but first let's find out which employees are eligible for the mentorship program! For this, we created another data file holding the information of the employees whose birth years are in 1965 who will be trained by the outgoing employees:

![Mentorship_Eligibility](/images/mentorship_eligibility.png "Mentorship Eligibility")


## Summary: 

In order to make sure that PH's plan for mentorship of the next generation of PH employees will be successful, we need to compare the number of mentors and mentees to be able to answer the following two questions:

#### How many roles will need to be filled as the "silver tsunami" begins to make an impact?
We look at the number of Eligible employees for the mentorship program which is 1549 eligible employees:

![total_count_mentorship_eligibles](/images/total_count_mentorship_eligibles.png "Total Count of Mentorship Eligible Employees")

~~~~
SELECT COUNT(emp_no) AS "Total count of Employees Eligible for Mentorship"
FROM mentorship_eligibility;
~~~~



#### Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?
Then we will compare it with the number of job titles that will be retiring in the near future which are much higher, we can safely say that there are enough mentors to train the next generation of employees:

![Retiring_Titles](/images/retiring_titles.png "Retiring Titles") ![Mentorship_Eligible_Titles](/images/mentorship_eligible_titles.png "Mentorship Eligible Titles")

~~~~
SELECT title, COUNT(title) AS "count"
FROM mentorship_eligibility
GROUP BY title
ORDER BY "count" DESC;
~~~~

- All the queries for getting the data is available by clicking [here](/Queries/Employee_Database_Challenge.sql "download the SQL file")
- All the csv files are available by clicking [here](/Data "See the CSV files")
