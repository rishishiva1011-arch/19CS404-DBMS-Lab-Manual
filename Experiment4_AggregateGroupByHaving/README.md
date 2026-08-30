# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="810" height="183" alt="image" src="https://github.com/user-attachments/assets/c07e2ed2-47d6-471f-84a3-39e7e4340f56" />



```sql
select date(AppointmentDateTime) as AppointmentDate,count(*) as TotalAppointments from Appointments group by AppointmentDate ;
```

**Output:**

<img width="798" height="408" alt="image" src="https://github.com/user-attachments/assets/d6b6a6d9-3945-4e1c-a728-467d25ba102a" />


**Question 2**
---
<img width="813" height="150" alt="image" src="https://github.com/user-attachments/assets/03d1757d-e045-4b15-bed2-bbf3f4863524" />


```sql
select PatientID, count(*) as TotalRecords from MedicalRecords group by PatientID;
```

**Output:**

<img width="795" height="411" alt="image" src="https://github.com/user-attachments/assets/646c1436-97ee-4a36-bcc2-7ee91cdea4b9" />


**Question 3**
---
<img width="816" height="183" alt="image" src="https://github.com/user-attachments/assets/bd2d2cbd-e1d8-46ad-b807-9fe75c41dd4d" />


```sql
select strftime('%Y',ValidityPeriod) as ValidityYear, count (*) as TotalPatients from Insurance group by ValidityYear;
```

**Output:**

<img width="795" height="240" alt="image" src="https://github.com/user-attachments/assets/3b1f3185-cb0c-45a3-b5d8-985778e7adf2" />


**Question 4**
---
<img width="816" height="177" alt="image" src="https://github.com/user-attachments/assets/1b07afe9-e79e-4ea8-969d-6f482d87c9bd" />


```sql
select count(distinct salesman_id ) as COUNT from orders;
```

**Output:**

<img width="798" height="192" alt="image" src="https://github.com/user-attachments/assets/a60dee46-71d0-4bf1-9969-d4fbef04d48b" />


**Question 5**
---
<img width="819" height="177" alt="image" src="https://github.com/user-attachments/assets/805b81d5-2139-42fc-bb23-482697f385d6" />


```sql
select count(*) as COUNT from customer where grade is not null;
```

**Output:**

<img width="798" height="192" alt="image" src="https://github.com/user-attachments/assets/014151f0-5219-4cc2-bb66-0c8d9f2a960d" />


**Question 6**
---
<img width="819" height="189" alt="image" src="https://github.com/user-attachments/assets/2ecf366e-9cb3-459a-bdb7-d13fb07e2f0a" />


```sql
select sum(inventory) as total from fruits where unit='LB'; 
```

**Output:**

<img width="801" height="192" alt="image" src="https://github.com/user-attachments/assets/f9cefd19-82b3-4a4f-ab08-1a5c68077523" />


**Question 7**
---
<img width="813" height="189" alt="image" src="https://github.com/user-attachments/assets/8e8f0cc1-c685-439c-81df-141a3a7aec5d" />


```sql
select name as fruit_name, inventory as lowest_quantity from fruits order by inventory limit 1;
```

**Output:**

<img width="798" height="192" alt="image" src="https://github.com/user-attachments/assets/9e2bad0f-9116-4a51-b48f-b54e4aeac6d1" />



**Question 8**
---
<img width="819" height="162" alt="image" src="https://github.com/user-attachments/assets/26f6608e-1fc3-4095-b290-b80e5b45297a" />


```sql
select (age/5)*5 as age_group, MIN(salary) as 'MIN(salary)' from customer1 group by age_group having min(salary)<2000;
```

**Output:**

<img width="798" height="204" alt="image" src="https://github.com/user-attachments/assets/cc728257-94d7-4e3f-8442-80d66e6234f9" />


**Question 9**
---
<img width="816" height="183" alt="image" src="https://github.com/user-attachments/assets/6055bcfb-43fd-4c3f-aac0-f85ded53086e" />


```sql
select age,MIN(income) as 'MIN(income)' from employee group by age having min(income)<400000;
```

**Output:**

<img width="795" height="237" alt="image" src="https://github.com/user-attachments/assets/48ffbc5f-2347-4225-833c-aa5f480cd513" />


**Question 10**
---
<img width="816" height="186" alt="image" src="https://github.com/user-attachments/assets/e1df2c90-026e-43de-912b-63d4560157fe" />


```sql
select category_id , avg(price) as 'AVG(Price)' from products group by category_id having avg(price) between 10 and 15;
```

**Output:**

<img width="795" height="207" alt="image" src="https://github.com/user-attachments/assets/25ec1d6e-ef88-4b45-ab59-d256382e8499" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
