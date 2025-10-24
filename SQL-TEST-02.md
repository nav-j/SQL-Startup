# Ultimate SQL Practice Task – All-in-One Project

---

## 🎯 Objective
Practice all major **SQL topics** with one complete example:
- Table creation  
- Insertion  
- Filtering (WHERE, AND, OR, NOT)  
- Operators  
- Sorting  
- Aggregate Functions  
- GROUP BY / HAVING  
- JOIN  
- UNION / UNION ALL  
- Subqueries (EXISTS, ANY, ALL)  
- CASE Statements  
- Stored Procedures  
- UPDATE / DELETE  
- LIMIT  

---

## 🧱 Step 1: Create Tables

```sql
CREATE TABLE Departments (
    DeptID INT PRIMARY KEY AUTO_INCREMENT,
    DeptName VARCHAR(50)
);

CREATE TABLE Employees (
    EmpID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(50),
    DepartmentID INT,
    Salary INT,
    Experience INT,
    City VARCHAR(50),
    FOREIGN KEY (DepartmentID) REFERENCES Departments(DeptID)
);
````

---

## 📥 Step 2: Insert Data

```sql
INSERT INTO Departments (DeptName) VALUES
('HR'), ('IT'), ('Finance'), ('Marketing');

INSERT INTO Employees (Name, DepartmentID, Salary, Experience, City)
VALUES
('Ravi', 1, 40000, 3, 'Delhi'),
('Priya', 2, 55000, 5, 'Mumbai'),
('Anil', 3, 60000, 4, 'Bangalore'),
('Neha', 2, 45000, 2, 'Delhi'),
('Suresh', 1, 30000, 1, 'Chennai'),
('Meena', 2, 70000, 7, 'Pune'),
('Kavita', 4, 52000, 4, 'Mumbai'),
('Rajesh', 3, 75000, 8, 'Delhi');
```

---

## 🧾 Step 3: Sample Tables

### 🧩 **Departments**

| DeptID | DeptName  |
| ------ | --------- |
| 1      | HR        |
| 2      | IT        |
| 3      | Finance   |
| 4      | Marketing |

### 🧩 **Employees**

| EmpID | Name   | DepartmentID | Salary | Experience | City      |
| ----- | ------ | ------------ | ------ | ---------- | --------- |
| 1     | Ravi   | 1            | 40000  | 3          | Delhi     |
| 2     | Priya  | 2            | 55000  | 5          | Mumbai    |
| 3     | Anil   | 3            | 60000  | 4          | Bangalore |
| 4     | Neha   | 2            | 45000  | 2          | Delhi     |
| 5     | Suresh | 1            | 30000  | 1          | Chennai   |
| 6     | Meena  | 2            | 70000  | 7          | Pune      |
| 7     | Kavita | 4            | 52000  | 4          | Mumbai    |
| 8     | Rajesh | 3            | 75000  | 8          | Delhi     |

---

## 🧮 Step 4: Tasks, Queries & Sample Outputs

---

### 🔹 **Task 1 – WHERE Clause**

Display employees who work in **Delhi** and earn more than **40,000**.

```sql
SELECT Name, City, Salary
FROM Employees
WHERE City = 'Delhi' AND Salary > 40000;
```

**🟢 Sample Output**

| Name   | City  | Salary |
| ------ | ----- | ------ |
| Rajesh | Delhi | 75000  |
| Neha   | Delhi | 45000  |

---

### 🔹 **Task 2 – ORDER BY**

Display all employees **ordered by Salary (descending)**.

```sql
SELECT Name, Salary
FROM Employees
ORDER BY Salary DESC;
```

**🟢 Sample Output**

| Name   | Salary |
| ------ | ------ |
| Rajesh | 75000  |
| Meena  | 70000  |
| Anil   | 60000  |
| Priya  | 55000  |
| Kavita | 52000  |
| Neha   | 45000  |
| Ravi   | 40000  |
| Suresh | 30000  |

---

### 🔹 **Task 3 – Aggregate Functions**

Find the **highest, lowest, and average salary**.

```sql
SELECT MAX(Salary) AS Highest, MIN(Salary) AS Lowest, AVG(Salary) AS Average
FROM Employees;
```

**🟢 Sample Output**

| Highest | Lowest | Average |
| ------- | ------ | ------- |
| 75000   | 30000  | 50875   |

---

### 🔹 **Task 4 – GROUP BY + HAVING**

Find departments where **average salary > 50,000**.

```sql
SELECT DepartmentID, AVG(Salary) AS AvgSalary
FROM Employees
GROUP BY DepartmentID
HAVING AVG(Salary) > 50000;
```

**🟢 Sample Output**

| DepartmentID | AvgSalary |
| ------------ | --------- |
| 2            | 56666.67  |
| 3            | 67500.00  |
| 4            | 52000.00  |

---

### 🔹 **Task 5 – JOIN**

Show each employee’s name with their department name.

```sql
SELECT e.Name, d.DeptName, e.Salary
FROM Employees e
JOIN Departments d ON e.DepartmentID = d.DeptID;
```

**🟢 Sample Output**

| Name   | DeptName  | Salary |
| ------ | --------- | ------ |
| Ravi   | HR        | 40000  |
| Priya  | IT        | 55000  |
| Anil   | Finance   | 60000  |
| Neha   | IT        | 45000  |
| Suresh | HR        | 30000  |
| Meena  | IT        | 70000  |
| Kavita | Marketing | 52000  |
| Rajesh | Finance   | 75000  |

---

### 🔹 **Task 6 – UNION**

Combine employees who work in **Delhi** and **Mumbai** (no duplicates).

```sql
SELECT Name, City FROM Employees WHERE City = 'Delhi'
UNION
SELECT Name, City FROM Employees WHERE City = 'Mumbai';
```

**🟢 Sample Output**

| Name   | City   |
| ------ | ------ |
| Ravi   | Delhi  |
| Neha   | Delhi  |
| Rajesh | Delhi  |
| Priya  | Mumbai |
| Kavita | Mumbai |

---

### 🔹 **Task 7 – CASE Statement**

Classify employees based on salary range.

```sql
SELECT Name, Salary,
CASE
    WHEN Salary < 40000 THEN 'Low Salary'
    WHEN Salary BETWEEN 40000 AND 60000 THEN 'Medium Salary'
    ELSE 'High Salary'
END AS SalaryLevel
FROM Employees;
```

**🟢 Sample Output**

| Name   | Salary | SalaryLevel   |
| ------ | ------ | ------------- |
| Ravi   | 40000  | Medium Salary |
| Priya  | 55000  | Medium Salary |
| Anil   | 60000  | Medium Salary |
| Neha   | 45000  | Medium Salary |
| Suresh | 30000  | Low Salary    |
| Meena  | 70000  | High Salary   |
| Kavita | 52000  | Medium Salary |
| Rajesh | 75000  | High Salary   |

---

### 🔹 **Task 8 – EXISTS Subquery**

List departments that have employees.

```sql
SELECT DeptName
FROM Departments d
WHERE EXISTS (
    SELECT 1 FROM Employees e WHERE e.DepartmentID = d.DeptID
);
```

**🟢 Sample Output**

| DeptName  |
| --------- |
| HR        |
| IT        |
| Finance   |
| Marketing |

---

### 🔹 **Task 9 – ANY and ALL**

Find employees whose salary is greater than **ANY salary in HR**.

```sql
SELECT Name, Salary
FROM Employees
WHERE Salary > ANY (SELECT Salary FROM Employees WHERE DepartmentID = 1);
```

**🟢 Sample Output**

| Name   | Salary |
| ------ | ------ |
| Priya  | 55000  |
| Anil   | 60000  |
| Meena  | 70000  |
| Kavita | 52000  |
| Rajesh | 75000  |

---

### 🔹 **Task 10 – Stored Procedure**

Create a stored procedure to get employees by city.

```sql
DELIMITER //
CREATE PROCEDURE GetEmployeesByCity(IN cityName VARCHAR(50))
BEGIN
    SELECT Name, DepartmentID, Salary
    FROM Employees
    WHERE City = cityName;
END //
DELIMITER ;

CALL GetEmployeesByCity('Delhi');
```

**🟢 Sample Output**

| Name   | DepartmentID | Salary |
| ------ | ------------ | ------ |
| Ravi   | 1            | 40000  |
| Neha   | 2            | 45000  |
| Rajesh | 3            | 75000  |

---

### 🔹 **Task 11 – DELETE**

Delete employees who have less than 2 years experience.

```sql
DELETE FROM Employees
WHERE Experience < 2;
```

**🟢 Sample Output**

✅ 1 Row Deleted — Suresh removed.

---

### 🔹 **Task 12 – UPDATE**

Increase salary of IT department employees by 10%.

```sql
UPDATE Employees
SET Salary = Salary * 1.10
WHERE DepartmentID = 2;
```

**🟢 Sample Output**

✅ Updated rows: Priya, Neha, Meena
New salaries = 60500, 49500, 77000 respectively.

---

### 🔹 **Task 13 – LIMIT (Top Records)**

Display **top 3 highest-paid** employees.

```sql
SELECT Name, Salary
FROM Employees
ORDER BY Salary DESC
LIMIT 3;
```

**🟢 Sample Output**

| Name   | Salary |
| ------ | ------ |
| Rajesh | 75000  |
| Meena  | 70000  |
| Anil   | 60000  |

---

### 🔹 **Task 14 – Arithmetic Operator**

Display salary with a **10% annual bonus**.

```sql
SELECT Name, Salary, (Salary * 1.10) AS SalaryWithBonus
FROM Employees;
```

**🟢 Sample Output**

| Name   | Salary | SalaryWithBonus |
| ------ | ------ | --------------- |
| Ravi   | 40000  | 44000           |
| Priya  | 55000  | 60500           |
| Anil   | 60000  | 66000           |
| Neha   | 45000  | 49500           |
| Meena  | 70000  | 77000           |
| Kavita | 52000  | 57200           |
| Rajesh | 75000  | 82500           |

---

### 🔹 **Task 15 – LIKE Operator**

Find employees whose names start with ‘R’.

```sql
SELECT Name, City
FROM Employees
WHERE Name LIKE 'R%';
```

**🟢 Sample Output**

| Name   | City  |
| ------ | ----- |
| Ravi   | Delhi |
| Rajesh | Delhi |

---

## ✅ Concepts Covered

| Category        | Topics                                 |
| --------------- | -------------------------------------- |
| **Basic SQL**   | CREATE, INSERT, SELECT, UPDATE, DELETE |
| **Filtering**   | WHERE, AND, OR, NOT, IN, BETWEEN, LIKE |
| **Sorting**     | ORDER BY, LIMIT                        |
| **Aggregation** | COUNT, SUM, AVG, MIN, MAX              |
| **Grouping**    | GROUP BY, HAVING                       |
| **Joins**       | INNER JOIN, LEFT JOIN                  |
| **Subqueries**  | EXISTS, ANY, ALL                       |
| **Combination** | UNION, UNION ALL                       |
| **Logic**       | CASE statements                        |
| **Procedures**  | CREATE PROCEDURE, CALL                 |
| **Operators**   | Comparison, Logical, Arithmetic        |

---

Would you like me to export this as a **README.md** or **Word (.docx)** file for easy sharing and submission?
```
