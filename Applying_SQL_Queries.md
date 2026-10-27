# SQL Filtering and Database Investigations

> **Note:** This project was developed within a simulated lab environment for practical hands-on security training. Any references to company data or networks are used solely for demonstration and learning purposes.

## Executive Summary
Security operations teams rely on database queries to investigate security incidents and manage administrative system updates efficiently. This project utilizes structured SQL queries to parse database logs, filter unauthorized access attempts, and isolate specific employee cohorts for software deployments. By streamlining data retrieval, the solution enables rapid incident response and precise configuration management.

## Project Description
SQL queries allow us to thoroughly search company databases for a variety of reasons, such as reviewing login timestamps, locations, and departments. This enables precise security control by facilitating security investigations as well as operational tasks like maintenance and software updates[cite: 1].

## Objective
The objective of this project is to write and execute targeted SQL queries to investigate security events, filter unauthorized login attempts, and isolate specific employee groups for administrative updates.

## Skills and Tools Demonstrated
- **Languages & Libraries:** SQL (Structured Query Language)
- **Concepts & Operations:** Data filtering, conditional logic (`AND`, `OR`, `NOT`), pattern matching (`LIKE`), wildcard usage (`%`), security investigations, and asset management


### 1. Retrieve after-hours failed login attempts
To investigate a potential security incident that occurred after hours, I needed to identify all failed login attempts. I pulled these records using the following SQL query:

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00:00' AND success = 'FALSE';
```
This query selects all failed login attempts that occurred after 6:00 PM. The `SELECT *` command returns all columns, the `FROM` clause specifies the `log_in_attempts` data table, and the `WHERE` clause uses the `AND` operator to filter results to only show entries where the time is past 18:00:00 and the success status is false.

### 2. Retrieve login attempts on specific dates
To investigate suspicious activity that took place over a specific timeframe, I used this query to retrieve all login attempts occurring on May 8, 2022, or May 9, 2022:

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```
This selects all results from the `log_in_attempts` table. The `WHERE` clause uses the `OR` operator to filter the results, ensuring that any login occurring on either of the specific dates is returned for review.

### 3. Retrieve login attempts outside of Mexico
After determining that the unauthorized activity did not originate in Mexico, I needed to filter those specific logins out of the dataset to narrow down the investigation. 

```sql
SELECT * 
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```
This query returns all login attempts excluding those from Mexico. Because the database contains variations like `"MEX"` and `"MEXICO"`, I used the `LIKE` operator combined with the `%` wildcard to identify any country entry starting with `"MEX"`. The `NOT` operator is then used to filter out all variations of those pattern matches.

### 4. Retrieve employees in Marketing
To prepare for targeted system updates, I needed to identify specific employee machines within the Marketing department. I used the following query to retrieve the necessary employee records:

```sql
SELECT * 
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
```
This selects all employees in the Marketing department who are located in the East building. The `department = 'Marketing'` condition filters the dataset for Marketing employees, while the `AND` operator combined with `office LIKE 'East%'` further narrows the results to include only those whose office location begins with `"East"`.

### 5. Retrieve employees in Finance or Sales
To gather device data for upcoming system updates across the Sales and Finance departments, I needed to retrieve all employee records for those specific groups. 

```sql
SELECT * 
FROM employees
WHERE department = 'Sales' OR department = 'Finance';
```
This query filters the dataset to return listings for both departments. By linking the two department conditions with the `OR` operator, the query successfully outputs all employee records belonging to either Sales or Finance.


### 6. Retrieve all employees not in IT
Because the Information Technology department had already received the latest system update, I needed to retrieve machine data for employees in all other departments. 

```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```
This query selects all records from the `employees` table while excluding the IT department. By applying the `NOT` operator to the `department = 'Information Technology'` condition, the dataset is filtered to return only the employee records required for the remaining updates.

## Summary
In this project, I investigated suspicious events by querying failed login attempts and narrowing down the exact dates and locations they originated from. I also prepared the environment for targeted system updates by filtering employee records based on specific department names and office locations, ensuring we pulled the exact data needed for deployment.
