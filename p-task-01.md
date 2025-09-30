# Python MySQL Example

This project demonstrates how to **connect to a MySQL database using Python** and run a simple SQL query.

---

## 📌 Requirements
- Python 3.x
- MySQL Server (e.g., XAMPP / WAMP / MySQL Workbench)
- Python library: [`mysql-connector-python`](https://pypi.org/project/mysql-connector-python/)

Install the connector:
```bash
pip install mysql-connector-python
````

---

## ⚙️ Code Explanation

```python
import mysql.connector

# Connect to MySQL
conn = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",
    database="test"   # replace with your database name
)

cursor = conn.cursor()

# Run query
cursor.execute("SELECT * FROM costomers")

# Fetch results
for row in cursor.fetchall():
    print(row)

cursor.close()
conn.close()
```

---

## 🚀 Steps to Run

1. Make sure your **MySQL server is running**.
2. Create a database (here it is named `test`).
3. Create a table (example: `costomers`) and insert some rows.
4. Run the Python script:

   ```bash
   python app.py
   ```
5. You’ll see the output of all rows from the `costomers` table.

---

## ⚠️ Note

* The table name `costomers` may be a typo — it should probably be `customers`.
* Update `database`, `user`, and `password` in the connection as per your MySQL setup.

---

✅ Now you have a simple way to fetch and display records from MySQL using Python!

```


---

## 📄 test.sql  

```sql
-- Create database
CREATE DATABASE IF NOT EXISTS test;
USE test;

-- Create table
CREATE TABLE IF NOT EXISTS customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    CustomerName VARCHAR(100) NOT NULL,
    Address VARCHAR(255),
    PinCode INT
);

-- Insert sample data
INSERT INTO customers (CustomerName, Address, PinCode) VALUES
('John Doe', '123 Main Street', 110001),
('Jane Smith', '456 Park Avenue', 220002),
('Alice Johnson', '789 Green Road', 330003);
