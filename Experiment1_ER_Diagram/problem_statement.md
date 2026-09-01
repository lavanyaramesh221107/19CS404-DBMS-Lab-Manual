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
<img width="854" height="568" alt="image" src="https://github.com/user-attachments/assets/cfa51045-8380-416c-a68b-21a37726953c" />

### Entities and Attributes
<img width="854" height="268" alt="image" src="https://github.com/user-attachments/assets/1706614a-9d35-4e96-94d2-65c738f3b638" />


### Relationships and Constraints
<img width="850" height="240" alt="image" src="https://github.com/user-attachments/assets/1f24ad36-9dd5-4a9d-8e69-c8e59d42fb80" />


### Assumptions

One membership type per member.

A program must have at least one trainer.

Personal training is optional and billed separately.

Attendance is recorded only when members participate.

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
<img width="855" height="613" alt="image" src="https://github.com/user-attachments/assets/b60d02a5-e848-49ac-91ae-d0ff5bb13873" />


### Entities and Attributes
<img width="857" height="292" alt="image" src="https://github.com/user-attachments/assets/76439b4c-129f-4694-a35c-9ca0c6f6b9e8" />


### Relationships and Constraints
<img width="849" height="315" alt="image" src="https://github.com/user-attachments/assets/19bb257a-1863-4775-adf0-90456af88ea4" />

### Assumptions

Each book has only one copy in the database (copies could be modeled separately if needed).

Fines are tracked as part of loan record.

Members may or may not attend events.

Each event takes place in exactly one room.

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
<img width="850" height="500" alt="image" src="https://github.com/user-attachments/assets/a80626bd-ec60-42b4-8ccf-8f82c07b2f80" />


### Entities and Attributes
<img width="851" height="321" alt="image" src="https://github.com/user-attachments/assets/e98d7d8b-cd60-4029-9f8a-22516133e03d" />


### Relationships and Constraints
<img width="852" height="317" alt="image" src="https://github.com/user-attachments/assets/65d304dc-bd24-4727-9eb9-bcbe911d62ed" />


### Assumptions

Walk-in customers treated as reservations without advance booking.

One waiter handles a reservation at a time.

Service charge fixed per bill.



## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
