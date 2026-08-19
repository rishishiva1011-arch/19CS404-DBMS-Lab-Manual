# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
<br>
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/b338de35-5f4f-46b2-a70b-468cef1d2c21" />
<br>

## Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|---|---|---|
| MEMBERSHIP_TYPE | **membership_type_id (PK)**, type_name, description, duration_months, price | Defines membership plans |
| MEMBER | **member_id (PK)**, full_name, email, phone, date_of_birth, gender, join_date, membership_type_id (FK) | Stores gym members |
| TRAINER | **trainer_id (PK)**, full_name, email, phone, specialization, hire_date | Stores trainers |
| PROGRAM | **program_id (PK)**, program_name, description, category, duration_weeks | Fitness programs |
| MEMBER_PROGRAM | **member_id (PK, FK)**, **program_id (PK, FK)**, enroll_date | Connects members and programs |
| SESSION | **session_id (PK)**, session_date, start_time, end_time, location, notes, member_id (FK), program_id (FK), trainer_id (FK) | Training sessions |
| ATTENDANCE | **attendance_id (PK)**, check_in_time, check_out_time, status, session_id (FK), member_id (FK), trainer_id (FK) | Records session attendance |
| PAYMENT | **payment_id (PK)**, amount, payment_date, payment_method, transaction_id, member_id (FK), membership_type_id (FK), session_id (FK), notes | Tracks membership/session payments |

## Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|---|---|---|---|
| HAS | 1 : N | Partial | One membership type can have many members |
| JOINS | 1 : N | Partial | A member can join multiple programs through MEMBER_PROGRAM |
| OFFERS | N : 1 | Partial | Multiple MEMBER_PROGRAM records can belong to one program |
| BOOKS SESSIONS WITH | M : N | Partial | Members can book sessions with trainers |
| ASSIGNED TO | M : N | Partial | Trainers can be assigned to multiple programs |
| BOOKS | 1 : N | Partial | A member-program enrollment can have multiple sessions |
| RECORDED FOR | 1 : N | Total on Attendance | A session can have multiple attendance records |
| MAKES PAYMENTS | 1 : N | Total on Payment | A member can make multiple payments |

## Assumptions

- Each member has one membership type.
- A member can join multiple programs.
- A program can have multiple trainers.
- A member can book multiple training sessions.
- Each session is associated with a member, trainer, and program.
- Attendance is recorded for each session.
- A member can make multiple payments.
- MEMBER_PROGRAM uses a composite primary key.

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
