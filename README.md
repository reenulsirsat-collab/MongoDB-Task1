# SQL Database Assignment

## Overview
This project contains a relational database schema and a collection of SQL queries designed to demonstrate database concepts such as:

- Table relationships
- Primary and foreign keys
- SQL joins
- Aggregate functions
- Subqueries
- Window functions
- Common Table Expressions (CTEs)
- MySQL-specific functions

The assignment models a company environment with departments, employees, projects, and employee assignments.

---

# Database Schema

## 1. Departments (D)
Stores department-related information.

| Column Name | Data Type | Constraint | Description |
|---|---|---|---|
| dept_id | INT | PRIMARY KEY | Unique ID for the department |
| dept_name | VARCHAR(50) | NOT NULL | Name of the department |
| location_id | VARCHAR(50) | NOT NULL | Geographic location |

### Sample Data

| dept_id | dept_name | location_id |
|---|---|---|
| 10 | Consulting | NYC |
| 20 | Engineering | SF |
| 30 | R&D | London |
| 40 | Sales | NYC |
| 50 | HR | SF |
| 60 | Admin | London |

---

## 2. Employees (E)
Stores employee information.

| Column Name | Data Type | Constraint | Description |
|---|---|---|---|
| employee_id | INT | PRIMARY KEY | Unique ID for the employee |
| employee_name | VARCHAR(50) | NOT NULL | Employee full name |
| manager_id | INT | FOREIGN KEY | ID of the manager |
| dept_id | INT | FOREIGN KEY | Department ID |
| salary | DECIMAL(10,2) | NOT NULL | Annual salary |

### Sample Data

| employee_id | employee_name | manager_id | dept_id | salary |
|---|---|---|---|---|
| 100 | Alice Smith (CEO) | NULL | 10 | 180000.00 |
| 101 | Bob Johnson | 100 | 20 | 120000.00 |
| 102 | Charlie Brown | 101 | 20 | 95000.00 |
| 103 | Diana Prince | 100 | 30 | 110000.00 |
| 104 | Evan Clark | 103 | 30 | 85000.00 |
| 105 | Fiona Glen | 101 | 20 | 90000.00 |
| 106 | George King | 100 | 40 | 75000.00 |
| 107 | Hannah Lee | 103 | 30 | 88000.00 |
| 108 | Ivan Rossi | 100 | 50 | 60000.00 |
| 109 | Jane Doe | 101 | 20 | 125000.00 |
| 110 | Kevin Blue | 104 | 30 | 86000.00 |

---

## 3. Projects (P)
Stores project-related details.

| Column Name | Data Type | Constraint | Description |
|---|---|---|---|
| project_id | INT | PRIMARY KEY | Unique ID for the project |
| project_name | VARCHAR(50) | NOT NULL | Project name |
| client_name | VARCHAR(50) | NOT NULL | Client name |
| start_date | DATE | NOT NULL | Project start date |
| dept_id | INT | FOREIGN KEY | Department responsible |

### Sample Data

| project_id | project_name | client_name | start_date | dept_id |
|---|---|---|---|---|
| 5001 | Aurora Migration | GlobalTech Solutions | 2023-01-15 | 20 |
| 5002 | Synergy App Dev | Zenith Corp | 2023-05-20 | 30 |
| 5003 | Q4 Sales Strategy | Apex Industries | 2024-01-01 | 40 |
| 5004 | Global Expansion | GlobalTech Solutions | 2024-03-10 | 10 |
| 5005 | Internal HR Tool | Internal | 2024-02-01 | 50 |
| 5006 | Data Analytics | Zenith Corp | 2022-11-01 | 20 |
| 5007 | Future Tech R&D | R&D Dept | 2024-06-01 | 30 |

---

## 4. Assignments (A)
Links employees with projects.

| Column Name | Data Type | Constraint | Description |
|---|---|---|---|
| assignment_id | INT | PRIMARY KEY | Unique assignment ID |
| employee_id | INT | FOREIGN KEY | Employee assigned |
| project_id | INT | FOREIGN KEY | Project assigned |
| hours_worked | INT | NOT NULL | Hours worked |
| start_date | DATE | NOT NULL | Assignment start date |

### Sample Data

| assignment_id | employee_id | project_id | hours_worked | start_date |
|---|---|---|---|---|
| 1 | 101 | 5001 | 150 | 2023-01-15 |
| 2 | 102 | 5001 | 160 | 2023-01-15 |
| 3 | 105 | 5001 | 140 | 2023-02-01 |
| 4 | 103 | 5002 | 80 | 2023-05-20 |
| 5 | 104 | 5002 | 70 | 2023-06-01 |
| 6 | 106 | 5003 | 5 | 2024-01-01 |
| 7 | 100 | 5004 | 20 | 2024-03-10 |
| 8 | 107 | 5002 | 75 | 2023-05-25 |
| 9 | 109 | 5006 | 200 | 2022-11-01 |
| 10 | 101 | 5006 | 250 | 2022-11-01 |
| 11 | 102 | 5006 | 180 | 2022-12-01 |
| 12 | 110 | 5007 | 10 | 2024-06-01 |

---

# Database Schema Structure

| Table Name | Purpose | Key Columns |
|---|---|---|
| Employees (E) | Stores employee information | employee_id (PK), manager_id (FK), dept_id (FK) |
| Departments (D) | Stores department details | dept_id (PK), location_id |
| Projects (P) | Stores project details | project_id (PK), client_name |
| Assignments (A) | Links employees to projects | assignment_id (PK), employee_id (FK), project_id (FK) |

---

# Concepts Covered

- INNER JOIN
- LEFT JOIN
- Aggregate Functions
- GROUP BY and HAVING
- Subqueries
- Correlated Subqueries
- Window Functions
- CASE Statements
- Common Table Expressions (CTEs)
- MySQL Functions
- Relational Database Design

---

# Technologies Used

- SQL
- MySQL
- Relational Database Management System (RDBMS)

---

# Author

Prepared as part of a SQL database assignment/project.

