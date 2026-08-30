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
<img width="2448" height="543" alt="image" src="https://github.com/user-attachments/assets/c7d8ad04-912a-4774-b004-8221a751abb5" />


```sql
select date(AppointmentDateTime) as AppointmentDate,count(*) as TotalAppointments from Appointments group by AppointmentDate ;
```

**Output:**
<img width="2397" height="1233" alt="image" src="https://github.com/user-attachments/assets/df96e335-19cf-4afe-84eb-e224ce3dd5f7" />



**Question 2**
---
<img width="2457" height="459" alt="image" src="https://github.com/user-attachments/assets/e1602132-53c6-4600-9463-3eac85e93884" />



```sql
select PatientID, count(*) as TotalRecords from MedicalRecords group by PatientID;
```

**Output:**
<img width="2391" height="1239" alt="image" src="https://github.com/user-attachments/assets/b0ade930-c9fc-4827-b647-0933302b3475" />


**Question 3**
---
<img width="2463" height="546" alt="image" src="https://github.com/user-attachments/assets/567520c1-892a-491b-89e8-280095c53f62" />


```sql
select strftime('%Y',ValidityPeriod) as ValidityYear, count (*) as TotalPatients from Insurance group by ValidityYear;
```

**Output:**

<img width="2394" height="723" alt="image" src="https://github.com/user-attachments/assets/d3122607-9629-476a-9075-ea5fac663eac" />



**Question 4**
---
<img width="2463" height="531" alt="image" src="https://github.com/user-attachments/assets/aaddfff1-5c03-45ea-adc4-e6ce2e6e87ab" />


```sql
select count(distinct salesman_id ) as COUNT from orders;
```

**Output:**

<img width="2403" height="573" alt="image" src="https://github.com/user-attachments/assets/a02c690b-5f94-43cf-9944-a57ec5933336" />



**Question 5**
---
<img width="2469" height="531" alt="image" src="https://github.com/user-attachments/assets/10a566c3-8668-4f56-836d-26d69ce92378" />



```sql
select count(*) as COUNT from customer where grade is not null;
```

**Output:**

<img width="2409" height="576" alt="image" src="https://github.com/user-attachments/assets/f6f28d26-1761-41de-9e66-2ee9158f820b" />



**Question 6**
---
<img width="2454" height="564" alt="image" src="https://github.com/user-attachments/assets/86eae1e3-752d-4a7c-9f7a-f84e60f6f86f" />



```sql
select sum(inventory) as total from fruits where unit='LB'; 
```

**Output:**

<img width="2391" height="585" alt="image" src="https://github.com/user-attachments/assets/f5b960d8-4d4b-4099-bbdf-1ab9c6f95f45" />



**Question 7**
---
<img width="2460" height="597" alt="image" src="https://github.com/user-attachments/assets/46abd3d6-8d17-405a-8f11-641556b821ab" />



```sql
select name as fruit_name, inventory as lowest_quantity from fruits order by inventory limit 1;
```

**Output:**

<img width="2397" height="576" alt="image" src="https://github.com/user-attachments/assets/698d2ad8-5e81-4109-9da0-8eabbcd744b0" />


**Question 8**
---
<img width="2466" height="492" alt="image" src="https://github.com/user-attachments/assets/ebdefa47-47e5-46c0-b59c-17f780db08f2" />



```sql
select (age/5)*5 as age_group, MIN(salary) as 'MIN(salary)' from customer1 group by age_group having min(salary)<2000;
```

**Output:**

<img width="2403" height="624" alt="image" src="https://github.com/user-attachments/assets/4cc31e1e-8c49-414d-829d-3e4b45877529" />



**Question 9**
---
<img width="2457" height="549" alt="image" src="https://github.com/user-attachments/assets/84a04e20-e970-487a-959e-4ae927d59d95" />



```sql
select age,MIN(income) as 'MIN(income)' from employee group by age having min(income)<400000;
```

**Output:**

<img width="2403" height="720" alt="image" src="https://github.com/user-attachments/assets/0611edd8-f5de-4dd7-90cc-e4c7f8968236" />



**Question 10**
---
<img width="2463" height="558" alt="image" src="https://github.com/user-attachments/assets/9aa58047-68cf-4ab0-b1da-ad7196b567ee" />



```sql
select category_id , avg(price) as 'AVG(Price)' from products group by category_id having avg(price) between 10 and 15;
```

**Output:**

<img width="2388" height="627" alt="image" src="https://github.com/user-attachments/assets/d2d183f4-2639-4669-bc39-41f6b3bbb124" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
