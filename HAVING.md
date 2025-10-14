Let’s move on to the **`HAVING`** clause in SQL.
The `HAVING` clause is used to filter groups **after aggregation**, whereas `WHERE` filters rows **before aggregation**.

# SQL Task – Using HAVING Clause

The **`HAVING`** clause is used with aggregate functions to filter grouped records.  
It’s often used along with `GROUP BY`.

---

## Table: Sales

| SaleID | ProductName | Category   | Quantity | Price |
|--------|--------------|------------|-----------|--------|
| 1      | Laptop       | Electronics | 3         | 50000  |
| 2      | Mobile       | Electronics | 8         | 20000  |
| 3      | Headphones   | Electronics | 15        | 3000   |
| 4      | Sofa         | Furniture   | 2         | 25000  |
| 5      | Chair        | Furniture   | 10        | 4000   |
| 6      | Table        | Furniture   | 4         | 10000  |
| 7      | Mixer        | Appliances  | 5         | 6000   |
| 8      | TV           | Electronics | 6         | 45000  |
| 9      | Fridge       | Appliances  | 3         | 30000  |
| 10     | Oven         | Appliances  | 2         | 15000  |

---

## **Task**

Find the **total sales amount** (Quantity × Price) for each category  
and display only those **categories where the total sales exceed ₹1,00,000**.

---

### **Solution**

```sql
SELECT 
    Category,
    SUM(Quantity * Price) AS TotalSales
FROM Sales
GROUP BY Category
HAVING SUM(Quantity * Price) > 100000;
````

---

### **Expected Output**

| Category    | TotalSales |
| ----------- | ---------- |
| Electronics | 559000     |
| Furniture   | 130000     |
| Appliances  | 135000     |

---

## **Bonus Task**

Display only those categories where **average price per product** is **greater than ₹10,000**.

```sql
SELECT 
    Category,
    AVG(Price) AS AveragePrice
FROM Sales
GROUP BY Category
HAVING AVG(Price) > 10000;
```

### Sample Output:

| Category    | AveragePrice |
| ----------- | ------------ |
| Electronics | 29500        |
| Appliances  | 17000        |

---

## **Concepts Covered**

* `GROUP BY` with aggregate functions (`SUM`, `AVG`)
* Using `HAVING` to filter aggregated data
* Difference between `WHERE` and `HAVING`

---
