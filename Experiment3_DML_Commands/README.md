# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="2448" height="786" alt="image" src="https://github.com/user-attachments/assets/8b038410-3b5e-4c4e-be60-8e15a8510dc5" />


```sql
update EMPLOYEES set EMAIL='not available',COMMISSION_PCT = 0.55 where DEPARTMENT_ID = 110;
```

**Output:**

<img width="2394" height="711" alt="image" src="https://github.com/user-attachments/assets/36b8d5be-4e70-4f89-8fe5-00a75dbc4570" />


**Question 2**
---
<img width="2454" height="735" alt="image" src="https://github.com/user-attachments/assets/b2d41e84-39ea-46a5-827e-f536afdef9fd" />


```sql
update EMPLOYEES set HIRE_DATE='2024-01-24' where DEPARTMENT_ID=50;
```

**Output:**

<img width="2406" height="546" alt="image" src="https://github.com/user-attachments/assets/fff007a9-c1e6-475d-b726-0f2cf80394d8" />


**Question 3**
---
<img width="2454" height="651" alt="image" src="https://github.com/user-attachments/assets/53377d7c-c21c-43bd-94d5-9685cb5ffb62" />


```sql
update Products set reorder_lvl = 20 where quantity<10 and category='Snacks';
```

**Output:**

<img width="2400" height="1092" alt="image" src="https://github.com/user-attachments/assets/dd5f1584-15e7-47de-9e90-b44156165464" />


**Question 4**
---
<img width="2454" height="717" alt="image" src="https://github.com/user-attachments/assets/57552afc-9426-47ce-b0d9-5860aa4f1f0e" />


```sql
update PRODUCTS set reorder_lvl = reorder_lvl * 0.7 where product_name like '%cream%' and quantity>reorder_lvl;
```

**Output:**

<img width="2400" height="951" alt="image" src="https://github.com/user-attachments/assets/a1738acc-e43c-4c48-8660-1cb6a2f089fa" />


**Question 5**
---
<img width="2442" height="756" alt="image" src="https://github.com/user-attachments/assets/8672ddf0-9769-4fc5-91ee-103704e02aa9" />


```sql
update EMPLOYEES set EMAIL = 'Unavailable';
```

**Output:**

<img width="2403" height="858" alt="image" src="https://github.com/user-attachments/assets/044a5d35-9594-4f40-b580-e0fefa0b1e46" />


**Question 6**
---
<img width="2463" height="555" alt="image" src="https://github.com/user-attachments/assets/6ae3cbff-fb5d-4544-9809-c6f7aa07c93a" />


```sql
delete from Customer where (GRADE = 3 or AGENT_CODE = 'A008') AND OUTSTANDING_AMT<5000;
```

**Output:**

<img width="2400" height="762" alt="image" src="https://github.com/user-attachments/assets/ab0ab952-3777-4ea5-a8a4-a6c21b183c11" />


**Question 7**
---
<img width="2460" height="288" alt="image" src="https://github.com/user-attachments/assets/ad804298-15af-4f5d-b25d-b12f1e4be152" />


```sql
delete from doctors where specialization is null;
```

**Output:**

<img width="2502" height="1608" alt="image" src="https://github.com/user-attachments/assets/1dee8519-da79-4e48-9e7b-20b434c138a3" />


**Question 8**
---
<img width="2460" height="600" alt="image" src="https://github.com/user-attachments/assets/2ac5b061-51a1-4628-8ca7-13557907de38" />


```sql
delete from customer where grade<2;
```

**Output:**

<img width="2394" height="1044" alt="image" src="https://github.com/user-attachments/assets/83d327e7-e96e-43bc-9be0-a62076960ba0" />


**Question 9**
---
<img width="2460" height="270" alt="image" src="https://github.com/user-attachments/assets/807fee55-d7ec-4408-865f-2182cf83557a" />


```sql
delete from surgeries where surgery_date = '2024-02-28';
```

**Output:**

<img width="2391" height="687" alt="image" src="https://github.com/user-attachments/assets/9037caf6-a4d6-4b34-bb8c-f701552b4eaf" />


**Question 10**
---
<img width="2460" height="693" alt="image" src="https://github.com/user-attachments/assets/d038f384-412f-4dfd-a862-a3601c38daab" />


```sql
delete from Customer where CUST_COUNTRY = 'India' and CUST_CITY not in ('Chennai');
```

**Output:**

<img width="2391" height="1710" alt="image" src="https://github.com/user-attachments/assets/805d40df-fac5-400b-b06e-41dce4d44da3" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
