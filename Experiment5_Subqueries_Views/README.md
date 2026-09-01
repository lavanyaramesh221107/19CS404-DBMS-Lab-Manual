# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="853" height="357" alt="image" src="https://github.com/user-attachments/assets/63c704a5-cf10-4992-8b8b-7c4c0831f86f" />


```
select * from medications where dosage=(select min(dosage) from medications);
```

**Output:**

<img width="852" height="393" alt="image" src="https://github.com/user-attachments/assets/39f07c86-f56f-401e-9613-378e3c59405a" />


**Question 2**
---
<img width="849" height="414" alt="image" src="https://github.com/user-attachments/assets/3a1b191f-19f4-49d0-8def-ac67507d6034" />


```
select name,city from customer where city in (select city from customer where id in (3,7));
```

**Output:**

<img width="738" height="642" alt="image" src="https://github.com/user-attachments/assets/e9cac8d9-1b59-4f4c-b9ca-c8d8a30d05ea" />


**Question 3**
---
<img width="850" height="438" alt="image" src="https://github.com/user-attachments/assets/85307c90-cf97-474f-8a15-194baec96381" />


```
select * from medications where dosage=(select max(dosage) from medications);
```

**Output:**

<img width="853" height="380" alt="image" src="https://github.com/user-attachments/assets/ea64bcf6-c1b0-4039-a164-e142f6c70dc5" />


**Question 4**
---
<img width="849" height="362" alt="image" src="https://github.com/user-attachments/assets/d9c5282f-db06-4107-943f-b90cc152d555" />


```
select * from departments where length(department_name)>(select avg(length(department_name)) from departments);
```

**Output:**

<img width="845" height="461" alt="image" src="https://github.com/user-attachments/assets/198c2396-92ab-4a07-baf8-92245b1eef51" />


**Question 5**
---
<img width="853" height="423" alt="image" src="https://github.com/user-attachments/assets/9d54d671-688f-410d-a4d4-cdc3c162a4ef" />


```
select * from orders where purch_amt > (select avg(purch_amt) from orders where ord_date='2012-10-10');
```

**Output:**
<img width="851" height="354" alt="image" src="https://github.com/user-attachments/assets/1bb137e8-af59-4ac0-ac53-877506a8b2e4" />


**Question 6**
---
<img width="853" height="489" alt="image" src="https://github.com/user-attachments/assets/41ceb422-8762-46cc-9d52-ad42361c4dda" />


```
select * from customers where salary=1500;
```

**Output:**
<img width="851" height="274" alt="image" src="https://github.com/user-attachments/assets/aa96488a-18ea-4bc6-b25b-eb4d34cb2bcd" />


**Question 7**
---
<img width="851" height="420" alt="image" src="https://github.com/user-attachments/assets/44afae8a-caea-495b-bd9c-88380afe1239" />


```
select name from customer where phone in (select phone from customer group by phone having count(*)=1);
```

**Output:**

<img width="849" height="606" alt="image" src="https://github.com/user-attachments/assets/16880b9a-aae4-411e-bdaa-fa854f8f81f5" />

**Question 8**
---
<img width="851" height="456" alt="image" src="https://github.com/user-attachments/assets/e0dab895-9f25-4376-b71a-706b3b51a76b" />


```
select * from employee where age < (select avg(age) from employee where income>250000);
```

**Output:**

<img width="849" height="399" alt="image" src="https://github.com/user-attachments/assets/df3abb14-a50d-4c02-bab7-abb390edb25b" />


**Question 9**
---
<img width="850" height="602" alt="image" src="https://github.com/user-attachments/assets/53d68dce-1120-4238-8ed4-9511558f0dcd" />


```
select * from customers where salary>1500;
```

**Output:**
<img width="853" height="463" alt="image" src="https://github.com/user-attachments/assets/0a65e4ac-565a-4a78-9fcd-f75bdfa129fc" />


**Question 10**
---
<img width="851" height="342" alt="image" src="https://github.com/user-attachments/assets/7598a13d-0096-4d31-a79e-3c041276ab81" />


```
SELECT grade, COUNT(*) 
FROM customer 
WHERE grade > (SELECT AVG(grade) 
               FROM customer 
               WHERE city = 'New York')
GROUP BY grade;

```

**Output:**
<img width="851" height="451" alt="image" src="https://github.com/user-attachments/assets/173a34a2-528f-4f53-96d1-2e935b905831" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
