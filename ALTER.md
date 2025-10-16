## SQL ALTER TABLE practice task.

### Given Table: `Persons`

| ID | LastName  | FirstName | Address      | City      |
| -- | --------- | --------- | ------------ | --------- |
| 1  | Hansen    | Ola       | Timoteivn 10 | Sandnes   |
| 2  | Svendson  | Tove      | Borgvn 23    | Sandnes   |
| 3  | Pettersen | Kari      | Storgt 20    | Stavanger |

---

### Task: Practice SQL `ALTER TABLE`

Write SQL queries to make the following changes to the `Persons` table:

1. **Add a new column** named `DateOfBirth` of type `DATE`.
2. **Rename** the column `Address` to `HomeAddress`.
3. **Modify** the column `City` to increase its size to `VARCHAR(100)`.
4. **Add a new column** `Email` that must be **unique**.
5. **Delete** the column `Email` from the table.
6. **Drop** the column `DateOfBirth`.
7. **Add** a new column `Age` with default value `18`.

---

### ✅ Output Format

Below is the **complete answer with all SQL solutions** ✅

---

### ✅ SQL Queries Using `ALTER TABLE`

```sql
-- 1. Add a new column DateOfBirth of type DATE
ALTER TABLE Persons 
ADD DateOfBirth DATE;

-- 2. Rename column Address to HomeAddress
ALTER TABLE Persons 
RENAME COLUMN Address TO HomeAddress;

-- 3. Modify the size of City column to VARCHAR(100)
ALTER TABLE Persons 
MODIFY City VARCHAR(100);

-- 4. Add a new column Email that must be UNIQUE
ALTER TABLE Persons 
ADD Email VARCHAR(100) UNIQUE;

-- 5. Delete the Email column
ALTER TABLE Persons 
DROP COLUMN Email;

-- 6. Drop the DateOfBirth column
ALTER TABLE Persons 
DROP COLUMN DateOfBirth;

-- 7. Add a new column Age with default value 18
ALTER TABLE Persons 
ADD Age INT DEFAULT 18;
```

---

### ✅ Final Table Structure After All Changes

| Column Name | Data Type        |
| ----------- | ---------------- |
| ID          | INT              |
| LastName    | VARCHAR          |
| FirstName   | VARCHAR          |
| HomeAddress | VARCHAR          |
| City        | VARCHAR(100)     |
| Age         | INT (Default 18) |

---
