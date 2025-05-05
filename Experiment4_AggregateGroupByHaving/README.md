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
![image](https://github.com/user-attachments/assets/408857b5-4b76-46cf-9325-6361d8452d39)

```
select date(AppointmentDateTime) as "AppointmentDate",count(AppointmentID) as TotalAppointments
from Appointments
group by AppointmentDateTime;
```


**Output:**

![image](https://github.com/user-attachments/assets/fd081a84-5ab3-421c-9ab7-1a1aa98be381)


**Question 2**
---
![image](https://github.com/user-attachments/assets/0608c196-0ba9-44bf-ad6a-920ffbdd8abe)

```
select InsuranceCompany,count(*) as "TotalExpiredPatients"
from Insurance
group by InsuranceCompany;
```

**Output:**

![image](https://github.com/user-attachments/assets/68176128-065a-4bc6-a723-d3144874ee4f)


**Question 3**
---
![image](https://github.com/user-attachments/assets/1e1249ce-8998-434d-8efc-e66a9cb9fdcd)

```
select InsuranceCompany,count(PatientID) as "TotalPatients"
from Insurance
group by InsuranceCompany;
```

**Output:**

![image](https://github.com/user-attachments/assets/ef9e7175-f8c1-444a-a18b-ecd93bffa209)


**Question 4**
---
-![image](https://github.com/user-attachments/assets/87cf0bda-773e-4686-b0ae-ecadd453c417)

```
select sum(income) as total_income
from employee
where age>=40;
```

**Output:**



**Question 5**
---
![image](https://github.com/user-attachments/assets/df859242-7e06-455e-8285-02a73fb3c9e7)

```
select sum(inventory) as "total"
from fruits
where unit="LB";
```

**Output:**

![image](https://github.com/user-attachments/assets/7935bf5a-0669-450b-abf9-525e6f2f764c)

**Question 6**
---
![image](https://github.com/user-attachments/assets/eecade6c-2831-4836-8e56-f8e1a555c052)

```
select avg(length(email)) as avg_email_length
from customer
```

**Output:**

![image](https://github.com/user-attachments/assets/c2f7b4e3-b130-4b31-b5bd-09a53f9671b4)


**Question 7**
---
![image](https://github.com/user-attachments/assets/e27fb201-787d-45e7-8bb4-98bce94022dd)

```
select name,max(length(name)) as "length"
from customer
```

**Output:**

![image](https://github.com/user-attachments/assets/86753f17-6990-4a37-a181-bb5741f25bc5)


**Question 8**
---
![image](https://github.com/user-attachments/assets/63a19620-7e73-4e97-a663-d8bb6be10153)


```
select city,sum(income) as "Income"
from employee
group by city
having sum(income)>200000;
```

**Output:**

0![image](https://github.com/user-attachments/assets/0610adff-115a-4f1c-9268-1aac2de4bed3)


**Question 9**
---
![image](https://github.com/user-attachments/assets/1a211bc9-62dc-487b-a4ae-6add51ef8e9c)

```
select age,max(income) as "MAX(income)"
from employee
group by age
having max(income)>2000000;
```

**Output:**

![image](https://github.com/user-attachments/assets/47aff8b1-a325-49fc-8454-9fa4ad0762d1)


**Question 10**
---
![image](https://github.com/user-attachments/assets/b2e56c29-53b6-4084-be3e-d6bd432dbe45)

```
select category_id,min(price) as "Price"
from products
group by category_id
having min(price)<10;
```

**Output:**


![image](https://github.com/user-attachments/assets/e281293d-9e58-43f0-b63d-0eda47df28d2)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
