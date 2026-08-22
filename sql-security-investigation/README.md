# SQL Security Investigation

## Project Overview

This project demonstrates how I used SQL to investigate potential security issues involving employee login activity and company devices. I analyzed data from the `log_in_attempts` and `employees` tables to identify suspicious login activity and determine which employee machines required security updates.

The purpose of this project was not only to retrieve data, but to practice using SQL as an investigative tool. I used filters to narrow large datasets down to information that would be useful during a security investigation.

## Scenario

As part of a simulated security investigation, I was responsible for reviewing login activity and employee information after potential security issues were discovered.

The investigation required me to:

- Identify failed login attempts occurring after business hours
- Investigate login activity from specific dates
- Identify login attempts originating outside of Mexico
- Locate Marketing employees working in East building offices
- Identify employees in the Finance and Sales departments
- Identify employees outside of the Information Technology department

## SQL Skills Demonstrated

During this investigation, I worked with:

- `SELECT` and `FROM` to retrieve database records
- `WHERE` to filter records
- `AND` to require multiple conditions
- `OR` to retrieve records matching either condition
- `NOT` to exclude records
- `LIKE` and `%` for pattern matching
- Date filtering
- Time filtering
- SQL troubleshooting
- Query-result validation

---

## Investigation 1: Failed After-Hours Login Attempts

I investigated failed login attempts that occurred after 6:00 PM.

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00'
AND success = 0;
```

The `login_time > '18:00'` condition limits the results to login attempts occurring after 6:00 PM. The `success = 0` condition identifies unsuccessful login attempts.

I used `AND` because both conditions had to be true.

The query returned **19 failed after-hours login attempts** for further investigation.

---

## Investigation 2: Login Attempts on Specific Dates

A suspicious event occurred on May 9, 2022, so I reviewed login activity from May 9 and the previous day, May 8.

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-08'
OR login_date = '2022-05-09';
```

I used `OR` because a login attempt could have occurred on either date and still be relevant to the investigation.

The query returned **75 login attempts** from the two dates.

---

## Investigation 3: Login Attempts Outside of Mexico

I needed to identify login attempts that did not originate in Mexico.

The database contained multiple representations of Mexico, including `MEX` and `MEXICO`. I used pattern matching to account for both values.

```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

`LIKE 'MEX%'` matches values beginning with `MEX`. The `%` wildcard represents any characters that may follow `MEX`.

Adding `NOT` excludes those records, leaving login attempts originating outside of Mexico.

The query returned **144 login attempts** from outside Mexico.

---

## Investigation 4: Marketing Employees in the East Building

The security team needed information about machines assigned to Marketing employees located in East building offices.

```sql
SELECT *
FROM employees
WHERE department = 'Marketing'
AND office LIKE 'East%';
```

The first condition limits the results to employees in Marketing.

`LIKE 'East%'` matches office locations beginning with `East`, regardless of the office number that follows.

I used `AND` because employees needed to meet both conditions.

The query returned **7 employees**.

---

## Investigation 5: Finance and Sales Employees

I retrieved employees belonging to either the Finance or Sales departments.

```sql
SELECT *
FROM employees
WHERE department = 'Finance'
OR department = 'Sales';
```

I used `OR` because an employee only needed to belong to one of the two departments to appear in the results.

The query returned **71 employees**.

---

## Investigation 6: Employees Outside of Information Technology

Employees in Information Technology had already received a security update, so I needed to identify employees in every other department.

```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```

Using `NOT` excludes employees whose department is Information Technology.

The query returned **161 employees** who were outside of the Information Technology department.

---

# Troubleshooting and Lessons Learned

One of the most useful parts of this project was learning how to recognize and correct SQL mistakes instead of expecting every query to work correctly the first time.

### Mistake 1: Filtering Locations Outside Mexico

While investigating login attempts outside Mexico, I initially had trouble structuring the condition correctly.

I learned that the database contained both `MEX` and `MEXICO`, so checking for only one exact value would not properly handle the data.

The corrected condition was:

```sql
WHERE NOT country LIKE 'MEX%';
```

This taught me how `LIKE`, `%`, and `NOT` can work together to exclude multiple values that share the same pattern.

### Mistake 2: Filtering Finance or Sales

I initially attempted to filter Finance and Sales without creating a complete comparison for both departments.

The correct query requires the `department` column to be compared separately against each value:

```sql
SELECT *
FROM employees
WHERE department = 'Finance'
OR department = 'Sales';
```

This helped me understand that both sides of an `OR` condition need to represent valid conditions.

### Validating Results

I also learned that a SQL query running without an error does not automatically mean that the query is logically correct.

After running a query, I need to review the returned records and ask whether the results actually answer the question I intended to investigate.

This is especially important in cybersecurity because an incorrect filter could cause an analyst to overlook relevant security events or investigate unrelated activity.

---

## Security Relevance

Security analysts frequently work with large datasets containing authentication logs, user accounts, devices, network activity, and security events.

SQL allows an analyst to narrow that information to specific users, locations, dates, times, or conditions. Instead of manually reviewing every record, queries can isolate activity that requires further investigation.

This project helped me practice thinking about SQL as an investigation tool rather than only as a database language.

---

## Evidence

This repository includes supporting evidence from the lab environment showing the SQL queries and their results.

The evidence demonstrates both the completed investigation and the process I used to work through the queries.

## Tools and Technologies

- SQL
- MariaDB
- Linux command-line environment
- Relational databases
- Security log analysis
- Data filtering
- Query troubleshooting

## Key Takeaway

The biggest lesson from this project was that effective SQL analysis involves more than writing a query. I need to understand what I am searching for, choose the correct filters, examine the returned results, recognize when something does not look right, and correct the query when necessary.

That troubleshooting process is an important part of using SQL during a security investigation.
