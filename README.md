# SQL ANALYSIS DOCUMENTATION
---
## Project Overview
### Project Name: SQL query analysis documentation
### Description: This is a sql anlysis of the emp table which has empno, ename, job, hiredate, mgr, timp_stamp, sal, commission, exitdate and deptno columns. Different insights and exploratory data analysis (EDA) was gotten from it.

## Table Of Contents
[Introduction](introduction)

[Tools Used](tools-Used)

[CREATING DATABASE SCHEMA](cREATING-DATABASE-SCHEMA)

-[Database Schema](database-Schema)

[Data Insertion](data-Insertion)

-[dept table](dept-table)

-[emp table](emp-table)

[Questions and SQL queries ](questions-and-SQL-queries)

[Data Visualization](data-Visualization)

[Contribution](contribution)

[Conclusions](conclusions)

## INTRODUCTION
### The dataset is an employee sample dataset which contains 2 tables, the emp table and dept table. The aim of the analysis is to understand what the employee structure of the company comprises, analyze and derive insights to answer crucial questions and to help make crucial and data driven decisions as they may arise.

## Tools Used
MySQL: All analysis including inserting, editing and visualization was done here.

## CREATING DATABASE SCHEMA
The table 1 is the dept table which has columns deptno, dname and location. The primary key is deptno.

**Table 1**:
|deptno|dname|loc|
|------|-----|---|
|10|ACCOUNTING|NEWYORK|
|20|RESEARCH|DALLAS|
|30|SALES|CHICAGO|
|40|OPERATIONS|BOSTON|

The table 2 is the emp table which has columns empno, ename, job, hiredate, mgr, timestamp, salary, commission, exit date, deptno. Empno is the primary key and deptno is the foreign key.

**Table 2**:
|empno|ename|job|hiredate|mgr|time_stamp|sal|commission|exitdate|deptno|
|-------|-------|---------|-----------|------|----------|-----|----------|--------|------|
|7369|SMITH|CLERK|1980-12-17|7902|2023-08-01|800|30|1984-12-12|20
|7499|ALLEN|SALESMAN|1981-02-20|7698|2023-08-01|1600|300|1988-12-10|30|
|7521|WARD|SALESMAN|1981-02-22|7698|2023-08-01|1250|500|1986-01-12|30|
|7566|JONES|MANAGER|1981-04-02|7839|2023-08-01|2975|459.4|1988-02-07|20|
|7654|MARTIN|SALESMAN|1981-09-28|7698|2023-08-01|1250|1400|1984-12-12|30|
|7698|BLAKE|MANAGER|1981-05-01|7839|2023-08-01|2850|459|1986-05-01|30|
|7782|CLARK|MANAGER|1981-06-09|7839|2023-08-01|2450|67|1985-08-22|10|
|7788|SCOTT|ANALYST|1982-12-09|7566|2023-08-01|3000|67|1988-09-23|20|
|7839|KING|PRESIDENT|1981-11-17|5686|2023-08-01|5000|76|1986-10-25|10|
|7844|TURNER|SALESMAN|1981-09-08|7698|2023-08-01|1500|0|1989-10-28|30|
|7876|ADAMS|CLERK|1983-01-12|7788|2023-08-01|1100|67|1990-12-12|20|
|7900|JAMES|CLERK|1981-12-03|7698|2023-08-01|950|65|1985-03-17|30|
|7902|FORD|ANALYST|1981-12-03|7566|2023-08-01|3000|54|1984-12-31|20|
|7934|MILLAR|CLERK|1982-01-23|7782|2023-08-01|1300|67|1983-07-29|10|

### Database Schema 
#### Creating Tables:

-emp (Employee table)
---
-empno INT PRIMARY KEY

-ename VARCHAR(30)

-job VARCHAR(30)

-hiredate DATE

-mgr INT

-time_stamp DATE

-sal INT

-commission INT

-exitdate DATE

-deptno INT FOREIGN KEY REFERENCES dept(deptno)

-dept (Department table)
---
-deptno INT PRIMARY KEY

-dname VARCHAR(30)

-loc VARCHAR(30)

## Data Insertion
### dept table
The dept table appears to be a table that stores information about departments within an organization. To insert data into this table, you can use SQL INSERT INTO statements. Below are the SQL statements used to insert data into the dept table:

INSERT INTO dept
values
('10', 'ACCOUNTING', 'NEWYORK'),
('20', 'RESEARCH', 'DALLAS'),
('30', 'SALES', 'CHICAGO'),
('40','OPERATIONS', 'BOSTON')

SELECT * FROM dept

The SQL code above inserts data into the dept table. Each INSERT INTO statement inserts a single row into the table with values for the deptno, dname (department name), and loc (department location).

### emp table
The emp table appears to be a table that stores information about employees. To insert data into this table, you can use SQL INSERT INTO statements as well. Below are the SQL statements used to insert data into the emp table:

INSERT INTO emp
values
('7369', 'SMITH', 'CLERK', '1980-12-17', '7902', '2023-08-01', '800', '30', '1984-12-12', '20'),
('7499', 'ALLEN', 'SALESMAN', '1981-02-20', '7698',	'2023-08-01','1600', '300', '1988-12-10', '30'),
('7521', 'WARD', 'SALESMAN', '1981-02-22', '7698', '2023-08-01', '1250', '500','1986-01-12', '30'),
('7566', 'JONES','MANAGER',	'1981-04-02','7839', '2023-08-01', '2975', '459','1988-02-07', '20'),
('7654', 'MARTIN', 'SALESMAN', '1981-09-28', '7698', '2023-08-01', '1250', '1400', '1984-12-12', '30'),
('7698', 'BLAKE', 'MANAGER', '1981-05-01', '7839', '2023-08-01', '2850', '459', '1986-05-01', '30'),
('7782', 'CLARK', 'MANAGER', '1981-06-09', '7839', '2023-08-01', '2450', '67', '1985-08-22', '10'),
('7788', 'SCOTT', 'ANALYST', '1982-12-09', '7566', '2023-08-01', '3000', '67', '1988-09-23', '20'),
('7839', 'KING', 'PRESIDENT', '1981-11-17',	'5686',	'2023-08-01', '5000', '76', '1986-10-25', '10'),
('7844', 'TURNER', 'SALESMAN', '1981-09-08', '7698', '2023-08-01', '1500', '0', '1989-10-28', '30'),
('7876','ADAMS', 'CLERK', '1983-01-12',	'7788',	'2023-08-01','1100', '67', '1990-12-12', '20'),
('7900', 'JAMES', 'CLERK', '1981-12-03', '7698', '2023-08-01','950', '65', '1985-03-17','30'),
('7902', 'FORD', 'ANALYST', '1981-12-03', '7566', '2023-08-01','3000', '54', '1984-12-31', '20'),
('7934', 'MILLAR', 'CLERK',	'1982-01-23', '7782', '2023-08-01', '1300', '67', '1983-07-29', '10')

Each INSERT INTO statement in the code above inserts a single row of employee data into the emp table. The columns specified in the INSERT INTO statement are filled with values for each employee.

## Questions and SQL queries
### Exploratory Data Analysis (EDA)
#### Display all the unique job in the descending order? USING DISTINCT

SELECT*FROM emp

SELECT DISTINCT job FROM emp

ORDER BY job desc

#### Display all the details of the employees whose Commission Is more than their Salary.

SELECT * FROM emp

WHERE commission > sal

#### List the employees who are either ‘CLERK’ or ‘ANALYST’ in the Desc order.

SELECT empno, ename from emp

WHERE job= 'CLERK' or job= 'ANALYST'

ORDER BY empno DESC

#### Display employees whose salary is greater than 3000? USING THE HAVING STATEMENT

SELECT ename,sal FROM emp

GROUP BY empno

HAVING sal > '3000'

#### List the Enames of those that have five characters in their Names.

SELECT ename from emp

WHERE LEN(ename)=5

#### List the Enames of those that are starting with ‘S’ and with five characters.

SELECT ename from emp

WHERE ename like 'S%' 

and LEN(ename)=5 

#### List the employees whose Salary is a four digit number ending with Zero

SELECT sal from emp

WHERE LEN(sal)=4 and sal like '%0'

### Data Visualization
#### List the employees name and salary along with their name Daily salary for those Daily salary more than Rs.100.

SELECT ename,sal from emp

WHERE sal>'100'

![Dashboard](Bar-Plot.PNG)

![BAR CHART SQL](https://github.com/Covpet/SQL-ANALYSIS/assets/148041100/2659fb5b-6daf-4be9-9027-d0731a182b4e)

#### Salary trend for employees identifying as Clerk

SELECT sal, job from emp

WHERE job= 'clerk'

![Dashboard](Trendline.PNG)
![SQL GRAPH 2](https://github.com/Covpet/SQL-ANALYSIS/assets/148041100/627a8eae-c868-49df-b5b9-8dc0b01a1f81)

#### List the employees in the asc order of jobs of those who joined after the second half of 1981.

SELECT ename,job, hiredate from emp

WHERE hiredate > ('1981-06-30')

ORDER BY job ASC

## Contribution
***Department Data Insertion (Question 1)***: The SQL analysis begins with inserting data into the dept table, which stores information about different departments. This step populates the table with department names and locations, essential for organizing employee data.

***Employee Data Insertion (Question 2)***: Data for employees is inserted into the emp table. This data includes employee numbers, names, job titles, hire dates, manager numbers, salary, commission, exit dates, and department numbers. This step sets the foundation for employee-related queries.

***Distinct Job Titles (Question 3)***: The query to retrieve distinct job titles from the emp table shows that there are various job titles in the organization, providing insight into the diversity of roles among employees.

***Employees with Commission > Salary (Question 4)***: This query identifies employees whose commission is greater than their salary. Such cases may be of interest for further analysis or adjustment of compensation structures.

***Specific Job Titles (Question 5)***: The query filters employees with job titles 'CLERK' or 'ANALYST'. It demonstrates how to extract specific subsets of employees based on their job roles.

***High-Earning Employees (Question 6)***: The query groups employees by employee number and selects those with a salary greater than 3000. This query can be useful for identifying top earners in the organization.

***Employees with 5-Character Names (Question 7)***: The query identifies employees with names that are exactly 5 characters long. It might be relevant for identifying employees with shorter names for specific purposes.

***Employees Whose Names Start with 'S' and Are 5 Characters Long (Question 8)***: This query combines two criteria, selecting employees with names starting with 'S' and having exactly 5 characters. This could be useful for a specific subset of employees.

***Salaries Ending in '0' (Question 9)***: The query identifies employees with salaries that end in '0'. This can help identify employees with round-numbered salaries.

***Employees with Salaries > 100 (Question 10)***: The query selects employees with salaries greater than 100. This is a very broad filter, as almost all employees likely have salaries above 100.

***Employees with Job Title 'Clerk' (Question 11)***: This query filters employees by their job title, specifically selecting employees with the job title 'Clerk.'

***Employees Hired After June 30, 1981 (Question 12)***: The final query selects employees hired after June 30, 1981. This could be useful for analyzing newer hires in the organization.

Overall, the analysis provides insights into the diversity of job roles, salary structures, and specific subsets of employees within the organization. Depending on the organization's needs, the findings and queries can be used for various HR and data analysis purposes.

## Conclusion

In this SQL analysis, we performed various operations on the emp and dept tables to extract valuable insights from the data. We began by populating the dept table with information about different departments within an organization and followed by inserting data about employees into the emp table. With a structured dataset in place, we posed several questions and executed SQL queries to gain insights into the employee data. The findings and insights from the analysis are as follows:

We discovered a diverse range of job titles within the organization, highlighting the variety of roles employees hold.

By identifying employees whose commission exceeds their salary, we highlighted potential areas for compensation adjustments or further analysis.

Queries allowed us to select employees with specific job titles such as 'CLERK' and 'ANALYST,' helping categorize and analyze specific subsets of employees.

We identified high-earning employees by selecting those with salaries greater than 3000, providing a glimpse of top earners.

Additional queries enabled us to select employees with specific characteristics, such as those with 5-character names or salaries ending in '0.'

We also focused on employees hired after a specific date, potentially useful for analyzing newer hires.

These findings provide valuable insights into the organization's employee data, enabling various analytical and HR-related applications.






















