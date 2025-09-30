# Python MySQL Insert Example

This project demonstrates how to **connect to a MySQL database using Python** and **insert data into a table**.

---

## 📌 Requirements
- Python 3.x
- MySQL Server (XAMPP / WAMP / MySQL Workbench)
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

# Run INSERT query
cursor.execute("INSERT INTO `customers` (`CustomerName`, `Address`, `PinCode`) VALUES ('sanjeev', 'buynhhfir', '141434')")
conn.commit()   # save changes

# Fetch results (⚠️ not needed for INSERT, usually used with SELECT)
for row in cursor.fetchall():
    print(row)

cursor.close()
conn.close()
```

---

## 🚀 Steps to Run

1. Make sure your **MySQL server is running**.
2. Import the `test.sql` file (see below) to create the database and `customers` table.

   ```bash
   mysql -u root -p < test.sql
   ```
3. Run the Python script:

   ```bash
   python app.py
   ```
4. A new row will be added to the **customers** table.

---

## ⚠️ Important Notes

* `conn.commit()` is **required** after `INSERT`, `UPDATE`, or `DELETE` queries.
* `cursor.fetchall()` is **not needed** after `INSERT`.

  * If you want to verify insertion, run a separate `SELECT * FROM customers`.
* Update `database`, `user`, and `password` in the connection as per your MySQL setup.

---

## 📄 Sample SQL (`test.sql`)

```sql
CREATE DATABASE IF NOT EXISTS test;
USE test;

CREATE TABLE IF NOT EXISTS customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    CustomerName VARCHAR(100) NOT NULL,
    Address VARCHAR(255),
    PinCode INT
);
```

---

✅ This script inserts a customer (`sanjeev`) into the `customers` table in MySQL.

```
