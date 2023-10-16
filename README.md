# SQL ANALYSIS DOCUMENTATION
---
## Project Overview
### Project Name: SQL query analysis documentation
### Description: This is a sql anlysis of the emp table which has empno, ename, job, hiredate, mgr, timp_stamp, sal, commission, exitdate and deptno columns. Different insights and exploratory data analysis (EDA) was gotten from it.

## INTRODUCTION
### The dataset is an employee sample dataset which contains 2 tables, the emp table and dept table. The aim of the analysis is to understand what the employee structure of the company comprises, analyze and derive insights to answer crucial questions and to help make crucial and data driven decisions as they may arise.

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

![Dashboard](bar plot.PNG)

![BAR CHART SQL](https://github.com/Covpet/SQL-ANALYSIS/assets/148041100/2659fb5b-6daf-4be9-9027-d0731a182b4e)


#### Salary trend for employees identifying as Clerk

SELECT sal, job from emp

WHERE job= 'clerk'

![Dashboard](bar plot.PNG)



#### List the employees in the asc order of jobs of those who joined after the second half of 1981.

SELECT ename,job, hiredate from emp

WHERE hiredate > ('1981-06-30')

ORDER BY job ASC























