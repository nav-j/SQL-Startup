# SQL Task – Using SQL Operators

---

## Task Objective
Practice SQL **operators** such as:
- **Comparison Operators** (`=`, `>`, `<`, `>=`, `<=`, `<>`)
- **Logical Operators** (`AND`, `OR`, `NOT`)
- **Arithmetic Operators** (`+`, `-`, `*`, `/`)

---

## Step 1: Create Table

```sql
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(50),
    Department VARCHAR(50),
    Salary INT,
    Experience INT,
    City VARCHAR(50)
);
````

---

## Step 2: Insert Sample Data

```sql
INSERT INTO Employees (Name, Department, Salary, Experience, City)
VALUES
('Ravi', 'HR', 40000, 3, 'Delhi'),
('Priya', 'IT', 55000, 5, 'Mumbai'),
('Anil', 'Finance', 60000, 4, 'Bangalore'),
('Neha', 'IT', 45000, 2, 'Delhi'),
('Suresh', 'HR', 30000, 1, 'Chennai'),
('Meena', 'IT', 70000, 7, 'Pune');
```

---

## Step 3: Sample Table – `Employees`

| EmpID | Name   | Department | Salary | Experience | City      |
| ----- | ------ | ---------- | ------ | ---------- | --------- |
| 1     | Ravi   | HR         | 40000  | 3          | Delhi     |
| 2     | Priya  | IT         | 55000  | 5          | Mumbai    |
| 3     | Anil   | Finance    | 60000  | 4          | Bangalore |
| 4     | Neha   | IT         | 45000  | 2          | Delhi     |
| 5     | Suresh | HR         | 30000  | 1          | Chennai   |
| 6     | Meena  | IT         | 70000  | 7          | Pune      |

---

## Step 4: Tasks & Queries

---

### 🔹 **Task 1 – Comparison Operator**

Display employees whose **salary is greater than 50,000**.

```sql
SELECT Name, Department, Salary
FROM Employees
WHERE Salary > 50000;
```

## Sample Output:

| Name  | Department | Salary |
| ----- | ---------- | ------ |
| Priya | IT         | 55000  |
| Anil  | Finance    | 60000  |
| Meena | IT         | 70000  |

---

### **Task 2 – Logical Operator (AND)**

Find employees from the **IT department** whose **salary is above 45,000**.

```sql
SELECT Name, Salary, City
FROM Employees
WHERE Department = 'IT' AND Salary > 45000;
```

## Sample Output:

| Name  | Salary | City   |
| ----- | ------ | ------ |
| Priya | 55000  | Mumbai |
| Meena | 70000  | Pune   |

---

### **Task 3 – Logical Operator (OR)**

Display employees who are in the **HR** department **or** live in **Delhi**.

```sql
SELECT Name, Department, City
FROM Employees
WHERE Department = 'HR' OR City = 'Delhi';
```

## Sample Output:

| Name   | Department | City    |
| ------ | ---------- | ------- |
| Ravi   | HR         | Delhi   |
| Neha   | IT         | Delhi   |
| Suresh | HR         | Chennai |

---

### **Task 4 – Logical Operator (NOT)**

Find employees **not working in IT**.

```sql
SELECT Name, Department, Salary
FROM Employees
WHERE NOT Department = 'IT';
```

## Sample Output:

| Name   | Department | Salary |
| ------ | ---------- | ------ |
| Ravi   | HR         | 40000  |
| Anil   | Finance    | 60000  |
| Suresh | HR         | 30000  |

---

### **Task 5 – Arithmetic Operator**

Display each employee’s **annual salary** (12 × monthly salary).

```sql
SELECT Name, Salary, (Salary * 12) AS AnnualSalary
FROM Employees;
```

## Sample Output:

| Name   | Salary | AnnualSalary |
| ------ | ------ | ------------ |
| Ravi   | 40000  | 480000       |
| Priya  | 55000  | 660000       |
| Anil   | 60000  | 720000       |
| Neha   | 45000  | 540000       |
| Suresh | 30000  | 360000       |
| Meena  | 70000  | 840000       |

---

### **Task 6 – Combined Condition**

Find employees whose **experience is 3 years or more** and **salary less than 60,000**.

```sql
SELECT Name, Experience, Salary
FROM Employees
WHERE Experience >= 3 AND Salary < 60000;
```

## Sample Output:

| Name  | Experience | Salary |
| ----- | ---------- | ------ |
| Ravi  | 3          | 40000  |
| Priya | 5          | 55000  |

---

## Concepts Covered

* **Comparison operators:** `=`, `>`, `<`, `<>`
* **Logical operators:** `AND`, `OR`, `NOT`
* **Arithmetic operators:** `+`, `-`, `*`, `/`
* Combining conditions with multiple operators
