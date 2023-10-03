
EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/bcafe163-fe65-4e52-ab19-86b96dd35d9b)


### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update managers set salary=salary+(salary*10/100);
```
### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/db9e264f-fb44-4d20-bac3-ebd3f446fbf6)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete managers where salary<2750;
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/3b578d0f-0eed-4591-aef6-593d1b98233b)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
ename AS "Name",
salary*12 AS "Annual Salary"
FROM
managers;
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/8d09c40e-1eac-4228-a666-3bb19a4728b0)



### Q5)	List the names of Clerks from emp table.


### QUERY:
```
select ename from managers where designation='clerk';
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/f2d658f3-4718-454a-941d-b0179a9d2f5e)



### Q6)	List the names of employee who are not Managers.


### QUERY:
```
select ename from managers where designation!='manager';
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/8c2185de-9d63-4538-b934-ab9efde9bfa2)



### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from managers where commission=0;
```


### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/05c4ec8d-1f11-4ef3-bf56-8d0da3e53d7d)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from managers where ename LIKE 'S%' OR ename LIKE '%S';
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/d832afaa-7541-432a-a149-a8806d265cf1)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation,deptno,hiredate from managers order by hiredate ASC;
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/2c703a98-b9ff-4e50-8324-e07267f0cbf5)



### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from managers where hiredate < '30 SEP 81';
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/eacac57c-b59f-4336-9d5c-97aab57008aa)



### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select ename,deptno,salary from managers ORDER BY deptno ASC,salary desc;
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/fbc50c88-c403-4b50-bf28-7306c29dfb2f)



### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from managers where deptno NOT IN (30,40,10);
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/dd793adc-6779-46a1-a38f-cb3f9b7ce578)


### Q13) Find number of rows in the table EMP

### QUERY:
```
select count(*) as rownumber from managers;
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/277a1c8c-0733-40f0-bc44-e7f6bd2e09b7)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimumsal,AVG(salary)
as averagesal from managers;
```


### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/42d20f69-d9af-4fba-bcb3-5e90d68b566b)



### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```
### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/3d70bf89-3d92-42cb-be88-66d7ef09ca32)


