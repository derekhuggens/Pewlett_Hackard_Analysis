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
From these 3 lists, two more requests were made:
  1. Sales department management asked for a query to obtain the Sales only employee numbers, first names, and last names.
  2. The company wants to start a mentorship program for Sales, so a query was written to create a table that contains employee numbers, first and last names, and department names where the departments can only be either Sales or Development.

## Results



DELIVERABLE CODE

![image](https://github.com/derekhuggens/Pewlett_Hackard_Analysis/blob/9c4851895ab2c53fa7f20e2f0a86e4dd5d19ae24/Deliverables.png)

## Summary
