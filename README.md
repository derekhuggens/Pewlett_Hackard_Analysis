# Pewlett_Hackard_Analysis
# Employee Database with SQL
## Overview of the Analysis
###
The purpose of this analysis was to answer business related questions about a company's employee database. The database was created in PostgreSQL, starting with the creation of 6 tables as seen in the below image (created from www.quickdatabasediagrams.com).


![image](https://github.com/derekhuggens/Pewlett_Hackard_Analysis/blob/e87d57b0b8e683d501e2579e3b0824ff281b3f97/EmployeeDB.png)


From these 6 tables, 12 more tables were created to answer questions such as: Who is eligible to retire and how many are going to retire? How many employees are retiring from each unique department? Other requests by management were made, leading to specific lists that became new tables:
  1. Employee information: unique employee number, last name, first name, gender, salary.
  2. Manager information: managers by department, their department number, their unique employee number, first name, last name, starting and ending employment dates.
  3. Department retiree information: a list of current employees that added what departments they are in to find out how departments will be affected by upcoming retirements.
 
From these 3 lists, 2 more requests were made:

  1. Sales department management asked for a query to obtain the Sales only employee numbers, first names, and last names.
  2. The company wants to start a mentorship program for Sales, so a query was written to create a table that contains employee numbers, first and last names, and department names where the departments can only be either Sales or Development.

Finally, 2 deliverables were requested from management.

  1. The number of retiring employees by title.
  2. The employees eligible for the mentorship program.

Below is the code for the 2 deliverables.

DELIVERABLE CODE


![image](https://github.com/derekhuggens/Pewlett_Hackard_Analysis/blob/9c4851895ab2c53fa7f20e2f0a86e4dd5d19ae24/Deliverables.png)


## Results


![image](https://github.com/derekhuggens/Pewlett_Hackard_Analysis/blob/60eb4df37e871fb9748fb24db2e15a7a0e655d29/retiring_titles.png)


The above image shows the number of employees retiring from each job title.


  * The company has a nice distribution (rounding down) of 2:1 Senior Engineers to Engineers and Senior Staff to Staff.
  * The count of 2 with the Manager title must be addressed with replacement before their departure.
  
  
![image](https://github.com/derekhuggens/Pewlett_Hackard_Analysis/blob/60eb4df37e871fb9748fb24db2e15a7a0e655d29/mentorship_eligibility.png)
  
  
The above image shows the employees that are eligible for the mentorship program.  
  * Since we ordered by employee number, we can see that some employees with a larger employee number does not mean that they necessarily started sooner than an employee with a smaller employee number (as seen in the from_date column), showing that employee numbers may be assigned arbitrarily.
  * Ordering by from_date would be able to show us which employees started earliest with the company and may be approached as senior mentors potentially.
  * There are 1549 employees eligible for the mentorship program, with a much larger sum of current employees vs. retired, leading to large mentorship class sizes.

## Summary

* How many roles will need to be filled as the "silver tsunami" begins to make an impact?

    41380 roles will need to be filled.
    
    Obtained by the query:
    
    SELECT COUNT(emp_no)
    FROM retirement_info;
    
* Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees? 
    
    There are 1549 employees in the mentorship eligibility table. 
    
    Obtained by the query:
    
    SELECT COUNT(emp_no)
    FROM mentorship_eligibility;
       
    Number of retirement-ready employees qualified to mentor: 85
    
    Obtained by the query:
    
    SELECT COUNT(emp_no)
    FROM mentorship_eligibility
	    WHERE to_date != '9999-01-01';
      
    Number of employees that could be mentored: 1464
    
    Obtained by the query:
    
    SELECT COUNT(emp_no)
    FROM mentorship_eligibility
	    WHERE to_date = '9999-01-01';

    There is a 17:1 ratio of next generation employees to qualified, retirement-ready employees.
