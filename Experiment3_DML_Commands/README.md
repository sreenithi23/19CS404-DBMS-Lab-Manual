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
![image](https://github.com/user-attachments/assets/090a8b34-eefb-4e37-8f30-d4b015ebd3ec)

```
insert into Products(Name,Category,Price,Stock)
values ('Smartphone', 'Electronics',800,150);
insert into Products(Name,Category,Price,Stock)
values('Headphones','Accessories',200,300);
```

**Output:**

![image](https://github.com/user-attachments/assets/afd62a75-6c7a-4d04-9e4e-a83ac6b7fe4b)


**Question 2**
---
![image](https://github.com/user-attachments/assets/cb661dd0-f31f-484d-a2e4-b5eb5d261912)

```
insert into Employee (EmployeeID, Name, Department, Salary) select EmployeeID, Name, Department, Salary from Former_employees;
```

**Output:**

![image](https://github.com/user-attachments/assets/fe199bd1-8a05-4959-9224-407fdd7ddeea)


**Question 3**
---
![image](https://github.com/user-attachments/assets/eacea9b2-6464-49b7-8213-3911fbf7a233)

```
select *
from EmployeeInfo
where EmpFname not in ('Sanjay','Sonia');
```

**Output:**

![image](https://github.com/user-attachments/assets/d84c366f-e430-46db-8dfe-d7016627cc18)


**Question 4**
---
![image](https://github.com/user-attachments/assets/1ff31151-56b2-49e6-b3d4-099b22f49c62)

```
SELECT *
FROM EmployeeInfo
ORDER BY EmpID DESC
LIMIT 5;
```

**Output:**

![image](https://github.com/user-attachments/assets/5364a0e1-0489-4820-80c6-ea5e8d55cdfb)


**Question 5**
---
![image](https://github.com/user-attachments/assets/0dea95e1-ff31-472f-ba52-092ded7406d0)

```
SELECT id,value2,
       CASE
            WHEN value2<30 THEN 'Poor'
            WHEN value2 between 30 and 70 THEN 'Average'
            WHEN value2>70 THEN 'Excellent'
        END AS  performance
FROM Calculations
```
**Output:**

![image](https://github.com/user-attachments/assets/e3b33b89-6644-4151-8af1-2a7b278ecbc8)


**Question 6**
---
![image](https://github.com/user-attachments/assets/c4a706ff-a353-4c02-8916-5850bd05439d)

```
UPDATE PRODUCTS
SET reorder_lvl=40
WHERE category='Grocery';
```
**Output:**
![image](https://github.com/user-attachments/assets/5e949226-e2de-4688-bef8-3977271735ca)


**Question 7**
---
![image](https://github.com/user-attachments/assets/c0057329-740b-4049-8792-68ab344bf334)

```
UPDATE Employees
SET salary=salary*2
where department_id=20
and job_id LIKE '%MAN';
```

**Output:**

![image](https://github.com/user-attachments/assets/9cdb1f68-66e8-463a-b322-664004fea464)


**Question 8**
---
![image](https://github.com/user-attachments/assets/e2c4c654-14d9-4a1b-bf65-50ea060bb612)

```
DELETE FROM customer
WHERE CUST_COUNTRY NOT IN('UK', 'USA', 'Canada')
AND GRADE>=3;
```

**Output:**
![image](https://github.com/user-attachments/assets/419880b0-d328-4993-85fd-c54052103ea9)


**Question 9**
---
![image](https://github.com/user-attachments/assets/387918b3-1646-4c01-9395-c61392fb3875)

```
DELETE FROM Doctors
WHERE specialization='Pediatrics'
and  first_name='Michael';
```

**Output:**

![image](https://github.com/user-attachments/assets/b18c0054-46d0-4b9d-9be6-f6a21c8516a7)


**Question 10**
---
![image](https://github.com/user-attachments/assets/43fb656b-362e-4b00-9452-6a808c9aeb04)

```
DELETE FROM customer
WHERE AGENT_CODE IN ('A003','A008');
```

**Output:**

![image](https://github.com/user-attachments/assets/30ced4b5-4d78-45ca-840e-1c7e85d18b98)

![Output10](output.png)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
