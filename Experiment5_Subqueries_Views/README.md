# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/c66388f5-cc3f-46e9-bb22-722b6eb4b593)

```
select student_id,student_name,subject,grade
from GRADES g
where grade=(
           select max(grade)
           from GRADES
           where subject=g.subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/bbb2be8a-ed70-4f3f-8ea1-92421bc65eb3)


**Question 2**
---
![image](https://github.com/user-attachments/assets/31bbfcc2-68b7-4269-a08b-66c2208910b3)

```
select *
from CUSTOMERS
where salary>1500;
```

**Output:**

![image](https://github.com/user-attachments/assets/14ec009c-bf86-468b-b05f-e6ccc291f6a3)


**Question 3**
---
![image](https://github.com/user-attachments/assets/28d42fd1-9692-41fd-81d0-6a02bfaf1af0)

```
select student_name,grade
from GRADES g
where grade=(
           select min(grade)
           from GRADES
           where subject=g.subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/eb7c3164-3ef9-4760-b75a-53bb17a35405)


**Question 4**
---
![image](https://github.com/user-attachments/assets/8891723a-36dc-48b9-bd0c-5fde76108055)

```
select ord_no,purch_amt,ord_date,customer_id,salesman_id
from orders
where salesman_id in(
       select salesman_id s
       from salesman
       where city ="London");
```
**Output:**

![image](https://github.com/user-attachments/assets/521dbbc0-581d-4c0c-84db-6081f74f1a23)

**Question 5**
---
![image](https://github.com/user-attachments/assets/cfe5b171-e303-49af-ac57-48791f52ac56)


```
select *
from CUSTOMERS
where ADDRESS="Delhi";
```

**Output:**

![image](https://github.com/user-attachments/assets/f90530be-c244-4d9b-bb65-a20691257545)


**Question 6**
---
![image](https://github.com/user-attachments/assets/7d96918c-6914-4dbb-b4e7-a3ffefbea76d)

```
select customer_id,cust_name,city,grade,salesman_id
from customer
where customer_id=(
        select salesman_id-2001
        from salesman 
        where name="Mc Lyon"
        LIMIT 1);
```

**Output:**

![image](https://github.com/user-attachments/assets/91e1c38d-8ebc-4e59-8c1b-848a86321bf7)


**Question 7**
---

![image](https://github.com/user-attachments/assets/9f677d5f-ca82-4219-843a-1dca11f8397d)



```
SELECT id,name,age,city,income
from Employee
where age<(
     select avg(age)
     from Employee
     where income>1000000);
```

**Output:**

![image](https://github.com/user-attachments/assets/6ab98f5a-84e6-438a-b977-a28c974ccff1)





**Question 8**
---

![image](https://github.com/user-attachments/assets/5aa97bd0-ad4b-47ae-bc73-183109c3fc22)


```
select ord_no,purch_amt,ord_date,customer_id,salesman_id
from orders
where salesman_id in(
      select DISTINCT salesman_id
      from orders
      where customer_id=3007);
```

**Output:**


![image](https://github.com/user-attachments/assets/756c0c12-246a-403e-b348-984422425457)


**Question 9**
---

![image](https://github.com/user-attachments/assets/448126a5-ce07-4d91-bbe0-3bd624980b97)

```
select ord_no,purch_amt,ord_date,customer_id,salesman_id
from ORDERS
where purch_amt>(
    select avg(purch_amt)
    from ORDERS
    where ord_date="2012-10-10"
);
```


**Output:**


![image](https://github.com/user-attachments/assets/4a677f5c-4a48-4d36-8200-adc592f7fd4f)


**Question 10**
---

![image](https://github.com/user-attachments/assets/d9f2f1a1-a19e-4a09-990f-7a999f52df61)

```
select student_name,grade
from GRADES g
where grade=(
     select max(grade)
     from GRADES
     where subject=g.subject);
```

**Output:**


![image](https://github.com/user-attachments/assets/1d9060f8-9ca1-4916-af51-541949b63fd3)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
