## Task 2 – Use `ALTER TABLE` with Constraints

You are given a table named **Employees** with the following data:

| EmpID | FirstName | LastName | Salary | Department |
| ----- | --------- | -------- | ------ | ---------- |
| 1     | Raj       | Kumar    | 35000  | HR         |
| 2     | Simran    | Kaur     | 42000  | IT         |
| 3     | Arjun     | Singh    | 39000  | Finance    |

---

### 👉 Your Tasks using `ALTER TABLE`

1. Add a new column `Email` (VARCHAR(100)).
2. Make the `Email` column `UNIQUE`.
3. Change the `Salary` column data type to `DECIMAL(10,2)`.
4. Rename the column `Department` to `DeptName`.
5. Add a new column `JoinDate` with default `'2024-01-01'`.
6. Add a `CHECK` constraint to ensure Salary is greater than 30000.

---

### ✅ SQL Solutions

```sql
-- 1. Add Email column
ALTER TABLE Employees
ADD Email VARCHAR(100);

-- 2. Make Email UNIQUE
ALTER TABLE Employees
ADD CONSTRAINT unique_email UNIQUE (Email);

-- 3. Modify Salary data type
ALTER TABLE Employees
MODIFY Salary DECIMAL(10,2);

-- 4. Rename Department to DeptName
ALTER TABLE Employees
RENAME COLUMN Department TO DeptName;

-- 5. Add JoinDate with default
ALTER TABLE Employees
ADD JoinDate DATE DEFAULT '2024-01-01';

-- 6. Add CHECK constraint on Salary
ALTER TABLE Employees
ADD CONSTRAINT chk_salary CHECK (Salary > 30000);
```

---

### ✅ Final Table Structure (after ALTER)

| Column     | Type                      |
| ---------- | ------------------------- |
| EmpID      | INT (Primary Key)         |
| FirstName  | VARCHAR                   |
| LastName   | VARCHAR                   |
| Salary     | DECIMAL(10,2)             |
| DeptName   | VARCHAR                   |
| Email      | VARCHAR UNIQUE            |
| JoinDate   | DATE DEFAULT '2024-01-01' |
| chk_salary | CHECK (Salary > 30000)    |

---
