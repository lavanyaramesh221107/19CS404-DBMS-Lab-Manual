# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="848" height="468" alt="image" src="https://github.com/user-attachments/assets/72fc6f45-8885-46d7-95b2-54c35386f030" />


```
SELECT p.first_name, s.*
FROM patients p
INNER JOIN surgeries s ON p.patient_id = s.patient_id
WHERE p.discharge_date BETWEEN '2024-03-01' AND '2024-03-31'
  AND NOT (p.admission_date BETWEEN '2024-03-01' AND '2024-03-31');

```

**Output:**

<img width="848" height="344" alt="image" src="https://github.com/user-attachments/assets/31f35a3d-5ea3-4580-91eb-aee6768774c5" />


**Question 2**
---
<img width="850" height="509" alt="image" src="https://github.com/user-attachments/assets/7dbc5c18-5293-49f3-ac19-0443f8d014ba" />


```
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission
FROM customer c
JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE s.commission > 0.12;

```

**Output:**

<img width="846" height="540" alt="image" src="https://github.com/user-attachments/assets/b80b46ee-fb2e-4c7c-850f-025039379be8" />


**Question 3**
---
<img width="846" height="484" alt="image" src="https://github.com/user-attachments/assets/ce69d080-c5e5-4bce-aff7-62820dcc66fc" />

```
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission
FROM customer c
JOIN salesman s ON c.salesman_id = s.salesman_id;

```

**Output:**

<img width="849" height="552" alt="image" src="https://github.com/user-attachments/assets/7e016784-a0e3-4b2d-b2ea-70f60750fd2a" />


**Question 4**
---
<img width="847" height="344" alt="image" src="https://github.com/user-attachments/assets/8958ae44-ff30-43ae-aa69-816118216136" />


```
SELECT 
    s.name AS salesman_name,
    c.cust_name AS customer_name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id = c.salesman_id;

```

**Output:**
<img width="848" height="838" alt="image" src="https://github.com/user-attachments/assets/4e180a0f-ac7d-421f-88eb-05ee0e3cc40c" />


**Question 5**
---
<img width="849" height="464" alt="image" src="https://github.com/user-attachments/assets/8f8f9cf7-230b-405c-bb25-22f6701fcd8c" />


```
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;

```

**Output:**

<img width="850" height="379" alt="image" src="https://github.com/user-attachments/assets/311fec70-359e-44ca-a832-efcaf4af2afc" />


**Question 6**
---
<img width="847" height="275" alt="image" src="https://github.com/user-attachments/assets/701ea0b9-9fc0-4cad-b0ca-d06d86865ac1" />


```
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE c.city = 'London';

```

**Output:**

<img width="850" height="378" alt="image" src="https://github.com/user-attachments/assets/9af344c5-55dd-443a-9774-2ee29b94f6c0" />

**Question 7**
---
<img width="849" height="494" alt="image" src="https://github.com/user-attachments/assets/e94093dd-414a-4e88-987b-4c3f769d5849" />


```
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
JOIN salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**
<img width="850" height="557" alt="image" src="https://github.com/user-attachments/assets/a9201aab-ab9e-4db9-956d-8ca2cd6a379a" />


**Question 8**
---
<img width="850" height="438" alt="image" src="https://github.com/user-attachments/assets/d00acebf-68a2-40dd-be19-56100eaee113" />



```
SELECT 
    p.first_name AS patient_name,
    t.result_id,
    t.patient_id,
    t.test_name,
    t.result,
    t.test_date
FROM patients p
JOIN test_results t ON p.patient_id = t.patient_id
WHERE t.test_name = 'Blood Pressure';

```

**Output:**

<img width="851" height="329" alt="image" src="https://github.com/user-attachments/assets/aec2c79a-519d-491a-adb7-4914d325a16a" />

**Question 9**
---
<img width="846" height="483" alt="image" src="https://github.com/user-attachments/assets/93d2099b-6102-4832-a7c2-2562b0d6d211" />


```
SELECT 
    c.cust_name,
    c.city AS city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM customer c
JOIN salesman s ON c.salesman_id = s.salesman_id
ORDER BY c.customer_id ASC;

```

**Output:**

<img width="850" height="561" alt="image" src="https://github.com/user-attachments/assets/18a4f479-0328-40bc-a322-dc703165a6f7" />


**Question 10**
---
<img width="848" height="469" alt="image" src="https://github.com/user-attachments/assets/56e24886-5cc3-4b80-9926-785c90c86a64" />


```
SELECT 
    p.first_name AS patient_name,
    d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d ON p.doctor_id = d.doctor_id
WHERE p.discharge_date IS NOT NULL;

```

**Output:**

<img width="847" height="334" alt="image" src="https://github.com/user-attachments/assets/9f4f98ec-a140-41d2-84d9-b93f261122ec" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
