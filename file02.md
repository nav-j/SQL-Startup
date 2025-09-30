## Access **MySQL database from XAMPP** in a **Jupyter Notebook**.
You just need the right Python connector.


---

## Step 1: Start MySQL in XAMPP

* Open **XAMPP Control Panel** → Start **MySQL** service.
* Default credentials:

  * Host = `localhost`
  * User = `root`
  * Password = *(empty)*

---

## Step 2: Install Required Libraries

In Jupyter Notebook (or terminal), run:

```bash
pip install mysql-connector-python
pip install sqlalchemy
pip install pymysql
pip install pandas
```

---

## Step 3: Connect to MySQL Database

### Using **mysql-connector-python**

```python
import mysql.connector

# Connect to MySQL
conn = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",
    database="mydb"   # replace with your database name
)

cursor = conn.cursor()

# Run query
cursor.execute("SELECT * FROM users")

# Fetch results
for row in cursor.fetchall():
    print(row)

cursor.close()
conn.close()
```

---

### Using **SQLAlchemy + Pandas** (easy for data analysis)

```python
import pandas as pd
from sqlalchemy import create_engine

# Create connection engine
engine = create_engine("mysql+pymysql://root:@localhost/mydb")

# Query into DataFrame
df = pd.read_sql("SELECT * FROM users", engine)
print(df.head())
```

---

## Step 4: Practice Queries

Now you can:

```python
df.info()
df.describe()
df['name'].value_counts()
```

and use **Pandas + SQL together** 🚀

---
