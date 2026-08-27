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
<img width="2568" height="513" alt="image" src="https://github.com/user-attachments/assets/8ea4c60f-49df-4805-826c-17c906e07a73" />


```sql
select name from customer where phone in (select phone from customer group by phone having count(*)=1)
```

**Output:**

<img width="2478" height="855" alt="image" src="https://github.com/user-attachments/assets/231e16ea-2b57-47a6-8cc7-67089d114c1e" />


**Question 2**
---

<img width="2532" height="708" alt="image" src="https://github.com/user-attachments/assets/7a6bbf86-7aac-4ad3-ae4d-730d4a4b57d6" />


```sql
select * from CUSTOMERS where SALARY<2500;
```

**Output:**

<img width="2481" height="852" alt="image" src="https://github.com/user-attachments/assets/7b9392cd-9062-494d-966e-2a7c7aa2bbfd" />

**Question 3**
---
<img width="2544" height="774" alt="image" src="https://github.com/user-attachments/assets/ffc5eef7-41b9-47a1-b5bf-d4edbe60a46b" />

```sql
select student_name,grade from GRADES g where grade=(select MIN(grade) from GRADES where subject=g.subject);
```

**Output:**

<img width="2490" height="807" alt="image" src="https://github.com/user-attachments/assets/c89d0bf2-7709-461b-bcc2-4b96b1c5bb24" />

**Question 4**
---
<img width="2523" height="1008" alt="image" src="https://github.com/user-attachments/assets/1918e50e-5f6e-4924-b7b9-85be52e679de" />


```sql
select * from ORDERS where salesman_id in(select salesman_id from SALESMAN where city in ('New York'));
```

**Output:**

<img width="2487" height="900" alt="image" src="https://github.com/user-attachments/assets/8758ee61-0056-491c-87ca-dd36184050f5" />


**Question 5**
---
<img width="2538" height="711" alt="image" src="https://github.com/user-attachments/assets/7e0c35c1-59f7-417c-8326-1316029538d9" />


```sql
select * from CUSTOMERS where SALARY = 1500;
```

**Output:**
<img width="2505" height="621" alt="image" src="https://github.com/user-attachments/assets/f091b19e-aeec-4678-8f0a-e876e94371a7" />


**Question 6**
---
<img width="2544" height="702" alt="image" src="https://github.com/user-attachments/assets/90c77761-5150-4e0b-a5a7-f7d292cd044f" />

```sql
select * from CUSTOMERS where age<30;
```

**Output:**

<img width="2481" height="1095" alt="image" src="https://github.com/user-attachments/assets/8aae4e23-a1c7-4bdf-9d33-e4f1feb4093a" />

**Question 7**
---
<img width="2523" height="681" alt="image" src="https://github.com/user-attachments/assets/899e6ce1-106c-44be-b32d-3eefdec22b84" />


```sql
select * from CUSTOMERS where ADDRESS = 'Delhi' and AGE<30 order by ID;
```

**Output:**

<img width="2499" height="672" alt="image" src="https://github.com/user-attachments/assets/68462711-514c-4412-b771-f10fc1e6bf0f" />


**Question 8**
---
<img width="2526" height="633" alt="image" src="https://github.com/user-attachments/assets/891cdba6-70ec-49f0-b66f-d1e71ad87487" />


```sql
select * from Employee where age < (select avg(age) from Employee where income>1000000 );
```

**Output:**

<img width="2499" height="804" alt="image" src="https://github.com/user-attachments/assets/4c99a3a3-b5e1-4653-991d-ac30ca956bfc" />


**Question 9**
---
<img width="2538" height="636" alt="image" src="https://github.com/user-attachments/assets/4f5fecb7-3e1a-4427-aa03-69f390d4f8a3" />


```sql
select * from Employee where age<(select avg(age) from Employee where income>250000);
```

**Output:**

<img width="2493" height="987" alt="image" src="https://github.com/user-attachments/assets/3b51cd37-560d-4de8-8299-902e0f93781b" />


**Question 10**
---
<img width="2538" height="486" alt="image" src="https://github.com/user-attachments/assets/a902c99b-beee-40cc-8d5b-63f3c5490cef" />


```sql
select name,city from customer where city in (select city from customer where id in (3,7));
```

**Output:**
<img width="2487" height="846" alt="image" src="https://github.com/user-attachments/assets/032d4078-d6fd-445c-a63e-59376484896d" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
