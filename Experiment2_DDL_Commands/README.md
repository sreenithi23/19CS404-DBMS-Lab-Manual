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



![image](https://github.com/user-attachments/assets/3fe83a1a-9889-4688-82ee-6c8f85d7944b)


```
Create table Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT);
```

**Output:**
![image](https://github.com/user-attachments/assets/e65a1e32-affa-418c-9315-c79b79ad5704)



**Question 2**



![image](https://github.com/user-attachments/assets/72849a5e-029c-4112-8f8d-40ace39a1aea)


```
alter table Student_details add column  ParentsNumber number;
alter table Student_details add column  Adhar_Number number;
```

**Output:**

![image](https://github.com/user-attachments/assets/b52a377f-5c94-49d2-94ed-6815a37a67ff)



**Question 3**
---
![image](https://github.com/user-attachments/assets/d949e054-fa08-423e-87d4-d91e6ca529f6)

```
DELETE FROM Doctors
WHERE specialization='Pediatrics'
and  first_name='Michael';
```
**Output:**

![image](https://github.com/user-attachments/assets/17bd17b1-a21f-4601-8e62-37817c6a9ad7)


**Question 4**


![image](https://github.com/user-attachments/assets/ff18f53f-98d7-43e0-a9aa-7ff9aa459246)

```
select date(AppointmentDateTime) as "AppointmentDate",count(AppointmentID) as TotalAppointments
from Appointments
group by AppointmentDateTime;
```

**Output:**


![image](https://github.com/user-attachments/assets/5edfdff8-341e-46f6-80ae-10f3beb2b22f)


**Question 5**


!![image](https://github.com/user-attachments/assets/88581c55-7b8c-4c2d-b19c-7a949373be8d)


```
create table Orders(
OrderID INTEGER primary key,
OrderDate date not null,
CustomerID INTEGER,
foreign key(CustomerID)references Customers(CustomerID)
);
```
**Output:**

![image](https://github.com/user-attachments/assets/64d73118-9962-474f-bf55-c6536b17f3d2)


**Question 6**
---


![image](https://github.com/user-attachments/assets/ee78fd02-88fe-4979-a70f-833035a969b3)

```
create table Products(
ProductID INTEGER primary key,
ProductName TEXT unique not NULL,
Price REAL,
StockQuantity INTEGER,
check(Price>0),
check(StockQuantity>=0)
);
```
**Output:**

![image](https://github.com/user-attachments/assets/ca25f3fc-5b2d-46f3-ad24-a4e5c3f271b9)


**Question 7**


![image](https://github.com/user-attachments/assets/11e1c767-4946-483d-a456-67eaae169bcb)

```
create table Products(
ProductID INTEGER primary key,
ProductName TEXT unique not NULL,
Price REAL,
StockQuantity INTEGER,
check(Price>0),
check(StockQuantity>=0)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/ac82452b-8bd9-4105-b45d-c056acc403a8)


**Question 8**
---


![image](https://github.com/user-attachments/assets/c264880a-7def-4ed9-89f1-9c5a2f709ece)

```
CREATE TABLE contacts(
contact_id INTEGER  primary key,
first_name TEXT not NULL,
last_name TEXT not NULL,
email TEXT,
phone TEXT not NULL,
CHECK (length(phone)>=10)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/7d6bbaa4-0052-4e59-b998-03698b7bd780)


**Question 9**


![image](https://github.com/user-attachments/assets/7d6938b8-d8ad-431d-950f-09f30a41d700)

```
create table Shipments(
ShipmentID INTEGER  primary key,
ShipmentDate  DATE,
SupplierID INTEGER ,
OrderID INTEGER,
foreign key(SupplierID) References Suppliers(SupplierID),
foreign key(OrderID) References Orders(OrderID));
```

**Output:**

![image](https://github.com/user-attachments/assets/88205a4b-e1f0-451b-9493-41091bf7f20a)


**Question 10**


![image](https://github.com/user-attachments/assets/4d391e39-c9d6-4114-a310-1b234199a499)

```
create table products(
product_id INTEGER primary key,
product_name TEXT not NULL,
list_price DECIMAL (10, 2) not NULL check(list_price>=0),
discount DECIMAL (10, 2) default 0 not NULL check(discount>=0) ,
check(list_price>=discount)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/2fe7d3c1-3a5b-4a8e-9665-343f611b5d06)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
