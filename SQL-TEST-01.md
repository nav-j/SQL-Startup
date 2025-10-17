# SQL Task – Working with a Table

---

##  Task Objective
Create a table named **`Students`**, insert data, and run queries to analyze and retrieve information.

---

## Step 1: Create Table

```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(50),
    Age INT,
    Course VARCHAR(50),
    Marks INT,
    City VARCHAR(50)
);
````

---

## Step 2: Insert Sample Data

```sql
INSERT INTO Students (Name, Age, Course, Marks, City)
VALUES
('Ravi', 21, 'Computer Science', 85, 'Delhi'),
('Neha', 20, 'Mathematics', 78, 'Mumbai'),
('Amit', 22, 'Computer Science', 90, 'Pune'),
('Kavita', 19, 'Physics', 65, 'Delhi'),
('Suresh', 21, 'Mathematics', 88, 'Chennai'),
('Pooja', 23, 'Computer Science', 75, 'Bangalore'),
('Rohan', 22, 'Physics', 58, 'Kolkata'),
('Simran', 20, 'Mathematics', 92, 'Delhi');
```

---

## Step 3: Sample Table — `Students`

| StudentID | Name   | Age | Course           | Marks | City      |
| --------- | ------ | --- | ---------------- | ----- | --------- |
| 1         | Ravi   | 21  | Computer Science | 85    | Delhi     |
| 2         | Neha   | 20  | Mathematics      | 78    | Mumbai    |
| 3         | Amit   | 22  | Computer Science | 90    | Pune      |
| 4         | Kavita | 19  | Physics          | 65    | Delhi     |
| 5         | Suresh | 21  | Mathematics      | 88    | Chennai   |
| 6         | Pooja  | 23  | Computer Science | 75    | Bangalore |
| 7         | Rohan  | 22  | Physics          | 58    | Kolkata   |
| 8         | Simran | 20  | Mathematics      | 92    | Delhi     |

---

## Step 4: Tasks & Solutions

---

### 🔹 **Task 1:** Display all students enrolled in **Computer Science**

```sql
SELECT * 
FROM Students
WHERE Course = 'Computer Science';
```

**🟢 Sample Output:**

| StudentID | Name  | Age | Course           | Marks | City      |
| --------- | ----- | --- | ---------------- | ----- | --------- |
| 1         | Ravi  | 21  | Computer Science | 85    | Delhi     |
| 3         | Amit  | 22  | Computer Science | 90    | Pune      |
| 6         | Pooja | 23  | Computer Science | 75    | Bangalore |

---

### 🔹 **Task 2:** Find students who scored more than **80 marks**

```sql
SELECT Name, Course, Marks
FROM Students
WHERE Marks > 80;
```

**🟢 Sample Output:**

| Name   | Course           | Marks |
| ------ | ---------------- | ----- |
| Ravi   | Computer Science | 85    |
| Amit   | Computer Science | 90    |
| Suresh | Mathematics      | 88    |
| Simran | Mathematics      | 92    |

---

### 🔹 **Task 3:** Find the **average marks** of students in each course

```sql
SELECT Course, AVG(Marks) AS AverageMarks
FROM Students
GROUP BY Course;
```

**🟢 Sample Output:**

| Course           | AverageMarks |
| ---------------- | ------------ |
| Computer Science | 83.33        |
| Mathematics      | 86.00        |
| Physics          | 61.50        |

---

### 🔹 **Task 4:** Display students from **Delhi**

```sql
SELECT Name, Course, City
FROM Students
WHERE City = 'Delhi';
```

**🟢 Sample Output:**

| Name   | Course           | City  |
| ------ | ---------------- | ----- |
| Ravi   | Computer Science | Delhi |
| Kavita | Physics          | Delhi |
| Simran | Mathematics      | Delhi |

---

### 🔹 **Task 5:** Find the student with the **highest marks**

```sql
SELECT Name, Marks
FROM Students
WHERE Marks = (SELECT MAX(Marks) FROM Students);
```

**🟢 Sample Output:**

| Name   | Marks |
| ------ | ----- |
| Simran | 92    |

---

## ✅ Concepts Covered

* Table creation (`CREATE TABLE`)
* Data insertion (`INSERT INTO`)
* Data retrieval (`SELECT`)
* Filtering (`WHERE`)
* Aggregation (`AVG`, `MAX`)
* Grouping (`GROUP BY`)
* Subquery usage
