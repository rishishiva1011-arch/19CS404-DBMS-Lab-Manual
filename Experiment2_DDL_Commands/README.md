# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
<img width="2454" height="465" alt="image" src="https://github.com/user-attachments/assets/e49413b9-6968-4127-a548-86441d64d95f" />


```sql
CREATE TABLE item (item_id TEXT PRIMARY KEY,item_desc TEXT NOT NULL,rate INT NOT NULL,icom_id TEXT(4),FOREIGN KEY (icom_id) REFERENCES company(com_id)ON UPDATE CASCADE ON DELETE CASCADE)
```

**Output:**
<img width="2403" height="660" alt="image" src="https://github.com/user-attachments/assets/546e9aa2-4272-44e7-a10d-8090a4365b85" />


**Question 2**
---
<img width="2481" height="345" alt="image" src="https://github.com/user-attachments/assets/eaadcce8-121a-448b-9e55-7b0197219c55" />


```sql
CREATE TABLE Customers (CustomerID INTEGER,
Name TEXT,
Email TEXT,
JoinDate DATETIME);
```

**Output:**

<img width="2409" height="759" alt="image" src="https://github.com/user-attachments/assets/52b340c5-15eb-4496-a8f5-d157348d83c6" />


**Question 3**
---
<img width="2463" height="312" alt="image" src="https://github.com/user-attachments/assets/14763edb-79d6-46c0-a33e-420022804b7c" />


```sql
CREATE TABLE Shipments (ShipmentID INT PRIMARY KEY,ShipmentDate DATE,SupplierID INT,OrderID INT,FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),FOREIGN KEY (OrderID) REFERENCES Orders(OrderID));
```

**Output:**
<img width="2400" height="447" alt="image" src="https://github.com/user-attachments/assets/9d14ae81-7b5f-431f-ad9b-af1f62f59acd" />


**Question 4**
---
<img width="2451" height="219" alt="image" src="https://github.com/user-attachments/assets/9d1428e2-c885-439f-bd3b-8ae0dce72477" />

```sql
create table Departments(DepartmentID INTEGER,DepartmentName TEXT);
```

**Output:**

<img width="2388" height="672" alt="image" src="https://github.com/user-attachments/assets/891b5d83-f67d-473f-80fa-9e78a77b073b" />


**Question 5**
---
<img width="2463" height="318" alt="image" src="https://github.com/user-attachments/assets/ebd7910c-06ee-429d-976f-662f640ef61c" />

```sql
create table ProjectAssignments(AssignmentID INTEGER primary key,EmployeeID INTEGER,ProjectID INTEGER,AssignmentDate DATE NOT NULL,FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID));
```

**Output:**

<img width="2388" height="534" alt="image" src="https://github.com/user-attachments/assets/2450a7df-9f0b-43f9-b62c-d70557e05e3f" />


**Question 6**
---
<img width="2451" height="516" alt="image" src="https://github.com/user-attachments/assets/f1e6245b-1ae1-4a7c-a811-186f18416df4" />


```sql
alter table Student_details add column Mobilenumber number;
```

**Output:**

<img width="2400" height="684" alt="image" src="https://github.com/user-attachments/assets/fee75bb3-cd80-4b6d-8a48-b9289e3e1f36" />


**Question 7**
---
<img width="2421" height="672" alt="image" src="https://github.com/user-attachments/assets/609c970d-8a73-46c7-931c-4caf0a24a9d3" />


```sql
alter table Student_details add column Date_of_birth Date;
```

**Output:**

<img width="2400" height="681" alt="image" src="https://github.com/user-attachments/assets/4212e646-092f-4eb3-b04b-770f15ddab49" />

**Question 8**
---
<img width="2442" height="513" alt="image" src="https://github.com/user-attachments/assets/f59db8be-e99b-417b-a765-91efa5a8b12b" />


```sql
alter table Student_details add column State TEXT;
```

**Output:**

<img width="2403" height="684" alt="image" src="https://github.com/user-attachments/assets/2c1a2301-1cd7-484a-a0a5-d20bfe6b6bf2" />


**Question 9**
---
<img width="2457" height="486" alt="image" src="https://github.com/user-attachments/assets/21f4ab55-0e01-42a9-bc66-dad771d154e9" />


```sql
CREATE TABLE orders (ord_id TEXT LENGTH check(length(ord_id)=4) NOT NULL,item_id TEXT NOT NULL ,ord_date DATE ,ord_qty INTEGER,cost INTEGER, PRIMARY KEY(item_id , ord_date));
```

**Output:**

<img width="2394" height="621" alt="image" src="https://github.com/user-attachments/assets/239558b0-6923-4730-8e45-cc1db07a2bd2" />


**Question 10**
---
<img width="2448" height="381" alt="image" src="https://github.com/user-attachments/assets/c9ef2e44-8bc0-4cb2-a056-a6df5d6fe8c4" />

```sql
CREATE table Invoices(InvoiceID INT,InvoiceDate DATE,Amount REAL check(Amount>0),DueDate DATE check(DueDate>InvoiceDate),OrderID INT, foreign key (OrderID) REFERENCES Orders(OrderID));
```

**Output:**
<img width="2406" height="534" alt="image" src="https://github.com/user-attachments/assets/258fedf1-5f05-48af-8907-13e480bc027c" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
