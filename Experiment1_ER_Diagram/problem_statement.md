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

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/18590eff-fee0-447e-84c1-5c0141f3fb1b" />

## Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|---|---|---|
| BOOK | **book_id (PK)**, title, author, isbn, publish_year, available_copies | Stores book details |
| CATEGORY | **category_id (PK)**, category_name, description | Classifies books |
| MEMBER | **member_id (PK)**, full_name, email, phone, address, join_date | Library member |
| LOAN | **loan_id (PK)**, loan_date, due_date, return_date, status | Tracks book loans |
| LOAN_ITEM | **loan_item_id (PK)**, **book_id (FK)**, quantity | Books included in a loan |
| FINE | **fine_id (PK)**, fine_date, amount, paid_date, status | Tracks overdue fines |
| EVENT | **event_id (PK)**, event_name, event_date, description, location | Library events |
| ROOM | **room_id (PK)**, room_name, capacity, location, room_type | Rooms for events and study |
| SPEAKER | **speaker_id (PK)**, full_name, bio, contact_info | Event speakers/authors |

## Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|---|---|---|---|
| BOOK — BELONGS TO — CATEGORY | N : 1 | BOOK total | Each book belongs to one category |
| MEMBER — BORROWS — LOAN | 1 : N | LOAN total | A member can have multiple loans |
| LOAN — INCLUDES — LOAN_ITEM | 1 : N | LOAN_ITEM total | A loan can contain multiple books |
| BOOK — IS OF — LOAN_ITEM | 1 : N | LOAN_ITEM total | A book can appear in multiple loan records |
| LOAN — GENERATES — FINE | 1 : N | FINE partial | A late loan may generate a fine |
| MEMBER — REGISTERS FOR — EVENT | M : N | Partial | Members can register for multiple events |
| EVENT — HAS — SPEAKER | M : N | EVENT total | An event can have one or more speakers |
| EVENT — BOOKED IN — ROOM | N : 1 | EVENT total | An event uses a room |

## Assumptions

- Each book belongs to one category.
- A member can have multiple loans.
- A loan can contain multiple books.
- Late returns may generate fines.
- Members can register for multiple events.
- Each event has one or more speakers.
- A room can be booked for events or study.
- A speaker can participate in multiple events.

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

## ER Diagram:

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/c1f53f7a-a828-443a-80cb-e15d26f6f639" />


## Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|---|---|---|
| CUSTOMER | **customer_id (PK)**, full_name, phone, email, address | Stores customer details |
| RESERVATION | **reservation_id (PK)**, res_date, res_time, party_size, status, **customer_id (FK)**, **table_id (FK)**, **waiter_id (FK)** | Stores table reservations |
| TABLE | **table_id (PK)**, table_no, capacity, location, status | Restaurant tables |
| ORDER | **order_id (PK)**, order_date, order_time, status, **reservation_id (FK)** | Food orders linked to reservations |
| ORDER_ITEM | **order_item_id (PK)**, quantity, unit_price, special_instructions, **order_id (FK)**, **menu_item_id (FK)** | Items included in an order |
| MENU_ITEM | **menu_item_id (PK)**, item_name, description, unit_price, is_available, **category_id (FK)** | Dishes offered by restaurant |
| CATEGORY | **category_id (PK)**, category_name, description | Starter, Main, Dessert, etc. |
| BILL | **bill_id (PK)**, bill_date, subtotal, service_charge, tax, total_amount, **reservation_id (FK)** | Bill generated for a reservation |
| WAITER | **waiter_id (PK)**, full_name, phone, shift | Waiter assigned to reservations |

## Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|---|---|---|---|
| CUSTOMER — MAKES — RESERVATION | 1 : N | Reservation total | A customer can make multiple reservations |
| RESERVATION — RESERVES — TABLE | N : 1 | Reservation total | A reservation is assigned to one table |
| RESERVATION — PLACES — ORDER | 1 : N | Order total | A reservation can have multiple food orders |
| ORDER — CONTAINS — ORDER_ITEM | 1 : N | Order_Item total | Each order contains multiple dishes |
| ORDER_ITEM — REFERS TO — MENU_ITEM | N : 1 | Order_Item total | Each order item refers to one menu item |
| CATEGORY — HAS — MENU_ITEM | 1 : N | Menu_Item total | A category contains multiple dishes |
| RESERVATION — GENERATES — BILL | 1 : 1 | Bill total | Each reservation generates one bill |
| WAITER — SERVES — RESERVATION | 1 : N | Reservation total | A waiter can serve multiple reservations |

## Assumptions

- Each reservation is assigned to one table.
- A customer can make multiple reservations.
- A reservation can have multiple food orders.
- Each order contains multiple order items.
- Each menu item belongs to one category.
- Each reservation generates one bill.
- A waiter can serve multiple reservations.
- Walk-in customers are recorded as reservations with a suitable status.
- Service charge and tax are included in the bill.

