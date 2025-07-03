![image](https://github.com/user-attachments/assets/8237da51-73f2-4af3-a3ab-011cda5cb10a)

# 🎯 Top 25 SQL Questions for Interview Prep (With LeetCode Links)

**Curated list of 25 questions** that are **frequently asked in tech interviews**, covering all major SQL concepts.
---
## 🟢 Basic `SELECT` / `WHERE` / `ORDER BY`

> 🧠 **Pattern**: Use when you're filtering or displaying simple attributes
> 🧱 **Structure**:

```sql
SELECT column1, column2
FROM table
WHERE condition
ORDER BY column ASC/DESC;
```

1. [Recyclable and Low Fat Products](https://leetcode.com/problems/recyclable-and-low-fat-products/)
   `WHERE attribute1 = 'value' AND attribute2 < threshold`

2. [Employees Earning More Than Their Managers](https://leetcode.com/problems/employees-earning-more-than-their-managers/)
   `Self Join + WHERE emp.salary > manager.salary`

3. [Customers Who Never Order](https://leetcode.com/problems/customers-who-never-order/)
   `LEFT JOIN + WHERE order.id IS NULL`

---

## 🔗 Joins (`INNER`, `LEFT`, `SELF`)

> 🧠 **Pattern**: Use when combining data from **multiple tables**
> 🧱 **Structure**:

```sql
SELECT ...
FROM A
JOIN B ON A.key = B.key
WHERE ...
```

4. [Combine Two Tables](https://leetcode.com/problems/combine-two-tables/)
   `LEFT JOIN to include all from Person, even if no Address`

5. [Employee Bonus](https://leetcode.com/problems/employee-bonus/)
   `LEFT JOIN employees and bonuses + WHERE bonus IS NULL or < amount`

6. [Managers with at Least 5 Direct Reports](https://leetcode.com/problems/managers-with-at-least-5-direct-reports/)
   `GROUP BY manager_id + HAVING COUNT(*) >= 5`

---

## 📊 `GROUP BY` + `HAVING`

> 🧠 **Pattern**: Use for **aggregated metrics** per group
> 🧱 **Structure**:

```sql
SELECT group_col, AGG_FUNC(col)
FROM table
GROUP BY group_col
HAVING AGG_FUNC(col) condition;
```

7. [Department Highest Salary](https://leetcode.com/problems/department-highest-salary/)
   `Subquery + JOIN to filter highest per dept`

8. [Group Sold Products By The Date](https://leetcode.com/problems/group-sold-products-by-the-date/)
   `GROUP BY sell_date, product + COUNT(product)`

9. [Market Analysis I](https://leetcode.com/problems/market-analysis-i/)
   `GROUP BY + COUNT(DISTINCT) with JOIN`

---

## 🪟 Window Functions / Ranking

> 🧠 **Pattern**: Use when you need **row-wise calculations across partitions**
> 🧱 **Structure**:

```sql
SELECT ..., RANK() OVER (PARTITION BY col ORDER BY col DESC) AS rank
FROM table
```

10. [Nth Highest Salary](https://leetcode.com/problems/nth-highest-salary/)
    `DENSE_RANK() OVER (ORDER BY salary DESC)`

11. [Rank Scores](https://leetcode.com/problems/rank-scores/)
    `DENSE_RANK() OVER (ORDER BY score DESC)`

12. [Consecutive Numbers](https://leetcode.com/problems/consecutive-numbers/)
    `Use LAG() / LEAD() or self-join to detect consecutive rows`

---

## 🧠 Subqueries / Nested Queries

> 🧠 **Pattern**: Use when a **value depends on another filtered result set**
> 🧱 **Structure**:

```sql
SELECT ...
FROM table
WHERE col IN (
  SELECT col FROM table WHERE condition
);
```

13. [Duplicate Emails](https://leetcode.com/problems/duplicate-emails/)
    `GROUP BY email + HAVING COUNT(*) > 1`

14. [Not Boring Movies](https://leetcode.com/problems/not-boring-movies/)
    `WHERE id % 2 = 1 AND description != 'boring'`

15. [Rising Temperature](https://leetcode.com/problems/rising-temperature/)
    `Self-Join OR LAG() to compare with previous day's temp`

---

## ⚙️ `CASE WHEN` / Logic Queries

> 🧠 **Pattern**: Use when **conditional output** is needed
> 🧱 **Structure**:

```sql
SELECT name,
  CASE
    WHEN condition THEN 'Value1'
    ELSE 'Value2'
  END AS alias
FROM table;
```

16. [Calculate Special Bonus](https://leetcode.com/problems/calculate-special-bonus/)
    `CASE WHEN name NOT LIKE 'M%' THEN salary ELSE 0`

17. [Replace Employee ID With The Unique Identifier](https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/)
    `JOIN + SELECT uuid AS id`

---

## ⏳ Date / String Functions

> 🧠 **Pattern**: Use when manipulating **dates or text**
> 🧱 **Structure**:

```sql
SELECT ...
FROM table
WHERE DATE(col) = 'YYYY-MM-DD'
-- OR use SUBSTRING(), CONCAT(), etc.
```

18. [Weather Observation Station 5](https://leetcode.com/problems/weather-observation-station-5/)
    `SELECT DISTINCT city FROM station WHERE ...`

19. [Find Total Time Spent by Each Employee](https://leetcode.com/problems/find-total-time-spent-by-each-employee/)
    `GROUP BY emp_id + SUM(time_diff)`

20. [Last Person to Fit in the Bus](https://leetcode.com/problems/last-person-to-fit-in-the-bus/)
    `ORDER BY + cumulative sum / window logic`

---

## 🔁 Advanced Joins / Set Operations

> 🧠 **Pattern**: Use when handling **row-level comparisons** or **multi-table data analysis**
> 🧱 **Structure**:

```sql
SELECT ...
FROM table1
FULL OUTER JOIN table2 ON condition
WHERE ...
```

21. [Duplicate Rows](https://leetcode.com/problems/duplicate-rows/)
    `GROUP BY all columns + HAVING COUNT(*) > 1`

22. [Project Employees I](https://leetcode.com/problems/project-employees-i/)
    `GROUP BY project_id + MAX(experience_years)`

---

## 🌍 Real-World Case Studies

> 🧠 **Pattern**: Combines all concepts – JOINs, aggregates, windows, conditions
> 🧱 Think in **layers**:
> `Step 1: Identify relationships` →
> `Step 2: Aggregate or filter` →
> `Step 3: Combine with JOINs or CTEs`

23. [Confirmation Rate](https://leetcode.com/problems/confirmation-rate/)
    `GROUP BY user_id + COUNT(CASE WHEN action = 'confirmed')`

24. [Average Time of Process per Machine](https://leetcode.com/problems/average-time-of-process-per-machine/)
    `Self Join + TIME_DIFF for start & end`

25. [Monthly Transactions I](https://leetcode.com/problems/monthly-transactions-i/)
    `GROUP BY MONTH(date_column), country`

---

📘 **Remember**:
> SQL interviews often test how you:  
 * Handle nulls
 * Choose the right type of JOIN
 * Use `GROUP BY` + `HAVING` smartly
 * Read questions carefully to avoid traps
 * Optimize logic using `CASE`, subqueries, or CTEs

---


