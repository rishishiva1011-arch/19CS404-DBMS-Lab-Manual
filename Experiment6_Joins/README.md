<img width="2535" height="1152" alt="image" src="https://github.com/user-attachments/assets/5e3c1761-bd3d-44a5-9f0c-a94dc352fdb3" /># Experiment 6: Joins

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
<img width="2541" height="1173" alt="image" src="https://github.com/user-attachments/assets/d294010f-119d-4f6e-ac37-00526a4fa580" />


```sql
select c.cust_name as 'Customer Name',c.city,s.name as Salesman,s.city,s.commission from customer c join salesman s on c.salesman_id=s.salesman_id where s.commission>0.12 and c.city <> s.city;
```

**Output:**

<img width="2487" height="1215" alt="image" src="https://github.com/user-attachments/assets/89a97f97-cbcb-429a-8163-42a80ecffcb2" />


**Question 2**
---
<img width="2535" height="1419" alt="image" src="https://github.com/user-attachments/assets/30bdce25-0156-4ec6-be83-bbd096c4763c" />


```sql
select c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt as 'Order Amount' from customer c left join orders o on c.customer_id=o.customer_id order by o.ord_date ASC;
```

**Output:**


<img width="2496" height="1482" alt="image" src="https://github.com/user-attachments/assets/5bbaf9b1-e7e7-4d84-be20-3f4d954e52db" />

**Question 3**
---
<img width="2529" height="963" alt="image" src="https://github.com/user-attachments/assets/24279953-637e-48f9-86b8-dc0c99ebe143" />


```sql
select n.nurse_id,n.first_name,n.last_name,d.department_id from nurses n inner join departments d on n.department_id=d.department_id where d.department_name='Pediatrics';
```

**Output:**

<img width="2487" height="786" alt="image" src="https://github.com/user-attachments/assets/d413e601-e795-4684-9751-f0e97fc88066" />


**Question 4**
---
<img width="2535" height="1152" alt="image" src="https://github.com/user-attachments/assets/d63c4376-9325-479e-8277-9f97ffefb5e5" />


```sql
select p.first_name as patient_name,d.first_name as doctor_name from patients p inner join doctors d on p.doctor_id=d.doctor_id where p.discharge_date is not null;
```

**Output:**

<img width="2490" height="744" alt="image" src="https://github.com/user-attachments/assets/b6e3a927-fc16-45c2-b270-1bc966b18ecb" />

**Question 5**
---
<img width="2541" height="1185" alt="image" src="https://github.com/user-attachments/assets/e8d69abc-5876-415b-bbab-b901981c15f6" />

```sql
select c.cust_name as 'Customer Name',c.city,s.name as Salesman,s.commission from customer c join salesman s on c.salesman_id=s.salesman_id where s.commission >0.12;
```

**Output:**

<img width="2496" height="1503" alt="image" src="https://github.com/user-attachments/assets/2f9fdbec-f2ba-4906-a987-5270f0960303" />


**Question 6**
---
<img width="2541" height="354" alt="image" src="https://github.com/user-attachments/assets/d11d6a0c-40d4-4042-9ebe-c297fd46cdfb" />


```sql
select c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt from customer c left join orders o on c.customer_id=o.customer_id where c.city='London';
```

**Output:**

<img width="2487" height="927" alt="image" src="https://github.com/user-attachments/assets/75938e38-b128-4f22-b275-00de016f5727" />

**Question 7**
---
<img width="2535" height="1455" alt="image" src="https://github.com/user-attachments/assets/c5aca4dc-32e7-42dd-8027-de63691b93de" />
<br>
<img width="2523" height="483" alt="image" src="https://github.com/user-attachments/assets/1180ea2b-7688-4aab-808e-b2d5ce6e954a" />


```sql
select o.ord_no,o.purch_amt,o.ord_date,c.cust_name,c.city as customer_city,c.grade,s.name as salesman_name,s.city as salesman_city,s.commission from orders o join customer c on c.customer_id=o.customer_id join salesman s on o.salesman_id=s.salesman_id;
```

**Output:**

<img width="2490" height="1491" alt="image" src="https://github.com/user-attachments/assets/de6e24de-2b93-422b-ac1d-da265f1bac55" />


**Question 8**
---
<img width="2541" height="966" alt="image" src="https://github.com/user-attachments/assets/bbe3b9e2-bc10-4ec0-8753-3d9dacbcfa65" />


```sql
select s.name,c.cust_name,c.city,c.grade,c.salesman_id from salesman s left join customer c on s.salesman_id = c.salesman_id;
```

**Output:**

<img width="2496" height="1761" alt="image" src="https://github.com/user-attachments/assets/922b4d4d-ca52-44c7-aaed-98efc2a1ad15" />


**Question 9**
---
<img width="2559" height="1008" alt="image" src="https://github.com/user-attachments/assets/9cb012bd-756a-4490-849a-f7a13fcbfafa" />


```sql
select p.first_name as patient_name,d.first_name as doctor_name from patients p inner join doctors d on p.doctor_id=d.doctor_id where p.discharge_date is null;
```

**Output:**

<img width="2487" height="885" alt="image" src="https://github.com/user-attachments/assets/4ad4c315-a763-42f2-8407-d0e03d3daa9c" />

**Question 10**
---
<img width="2520" height="1188" alt="image" src="https://github.com/user-attachments/assets/0d4203e6-5bc0-4efb-9a6c-4e0f8b07b0e9" />


```sql
select c.cust_name,c.city,c.grade,s.name as Salesman,s.city from customer c join salesman s on c.salesman_id=s.salesman_id order by customer_id;
```

**Output:**

<img width="2511" height="1758" alt="image" src="https://github.com/user-attachments/assets/f66c6db0-3d93-458e-949f-9f146ac015f0" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
