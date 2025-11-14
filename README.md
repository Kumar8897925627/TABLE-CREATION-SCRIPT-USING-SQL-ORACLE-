# TABLE-CREATION-SCRIPT-USING-SQL-ORACLE-
EMP–DEPT SQL Schema Setup (Oracle Database)
This project contains the SQL script used to create and populate two classic Oracle database tables: DEPT and EMP. These tables are widely used for learning relational database concepts, performing SQL queries, and understanding joins, constraints, and data relationships.

The project includes:

1. Table Creation Scripts

DEPT

Columns: DEPTNO, DNAME, LOC

Primary key: DEPTNO

EMP

Columns: EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO

Primary key: EMPNO

Foreign key: DEPTNO references DEPT(DEPTNO)

2. Sample Data Inserts

Preloaded department records (Accounting, Research, Sales, Operations)

Preloaded employee records including:

Managers

Clerks

Analysts

Salesmen

President

These records help in testing:

✔ Joins
✔ Aggregations
✔ Subqueries
✔ Grouping
✔ Integrity constraints
✔ Analytical SQL

3. Use Case

This dataset is perfect for:

SQL practice

Learning PL/SQL

Demo for interviews

Database teaching

Data analysis exercises

Creating dashboards or reports

📘 README.md (Full GitHub File)
# EMP–DEPT Schema Setup (Oracle SQL)

This repository contains SQL scripts to create and populate the classic **EMP** and **DEPT** tables used for learning SQL and database concepts. These scripts are fully compatible with **Oracle Database**.

---

## 📂 Repository Contents
- **create_tables.sql** → Creates DEPT and EMP tables with constraints  
- **insert_data.sql** → Inserts sample department and employee data  
- **README.md** → Project documentation  

---

## 🏗 Database Structure

### 🔹 DEPT Table
| Column  | Data Type     | Description           |
|---------|---------------|-----------------------|
| DEPTNO  | NUMBER(2)     | Department number (PK) |
| DNAME   | VARCHAR2(14)  | Department name        |
| LOC     | VARCHAR2(13)  | Location               |

**Primary Key:** DEPTNO

---

### 🔹 EMP Table
| Column   | Data Type       | Description                 |
|----------|------------------|-----------------------------|
| EMPNO    | NUMBER(4)        | Employee Number (PK)        |
| ENAME    | VARCHAR2(10)     | Employee Name               |
| JOB      | VARCHAR2(9)      | Job Role                    |
| MGR      | NUMBER(4)        | Manager EMPNO               |
| HIREDATE | DATE             | Date of joining             |
| SAL      | NUMBER(7,2)      | Salary                      |
| COMM     | NUMBER(7,2)      | Commission                  |
| DEPTNO   | NUMBER(2)        | Department Number (FK)      |

**Primary Key:** EMPNO  
**Foreign Key:** DEPTNO → DEPT(DEPTNO)

---

## 🧩 Features

- Demonstrates usage of:
  - Primary key & foreign key constraints  
  - Referential integrity  
  - Typical employee–department relationships  
  - Historical employee dataset for query practice  

- Useful for:
  - SQL learning and practice  
  - PL/SQL triggers, procedures, functions  
  - Data analysis exercises  
  - Teaching DBMS concepts  
  - Interview preparation  

---

## 📝 How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/emp-dept-oracle-schema.git


Connect to Oracle SQL*Plus / SQL Developer.

Run the scripts in order:

@create_tables.sql
@insert_data.sql


Start querying:

SELECT * FROM emp;
SELECT * FROM dept;

🧠 Example Queries
-- Employees with their department names
SELECT e.ename, e.job, d.dname
FROM emp e
JOIN dept d ON e.deptno = d.deptno;

-- Department-wise salary total
SELECT deptno, SUM(sal) AS total_salary
FROM emp
GROUP BY deptno;
