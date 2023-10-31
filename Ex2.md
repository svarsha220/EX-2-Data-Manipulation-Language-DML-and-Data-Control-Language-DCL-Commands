
### EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
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
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```
sql
insert into manager values(7369,'varsha',2500,500,30000,'clerk',10,'praba');
insert into manager values(7839,'aparna',3000,400,36000,'manager',null,'vaishu');
insert into manager values(8482,'yuva',4000,1000,48000,'clerk',50,'Bond');
insert into manager values(8489,'dhivya',4500,900,48000,'manager',50,'jeeva');
```
### OUTPUT:
![dbms 2 1](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/6e1969b7-48ba-40cf-8ae4-b8476fadadc6)



### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*20/100);
```
### OUTPUT:
![dbms 2 2](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/3c05fa00-ac32-4729-92ac-8c92a6c72ba8)


### Q2) Delete the records from manager table where the salary less than 3150.


### QUERY:
```
 delete from manager where salary<3150;
```

### OUTPUT:
![dbms 2 3](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/3973f042-1027-4891-af4b-5c466f3bd5c3)



### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
 select ename as "Name",salary*12 as "Annual Salary" from manager;
```

### OUTPUT:
![dbms 2 4](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/c48f9c6b-5ee6-44af-a55c-5e42d063674e)




### Q4)	List the names of Clerks from emp table.


### QUERY:
```
 select ename from manager where designation='clerk';
```

### OUTPUT:

![dbms 2 5](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/62f5d6a3-a97f-48e1-898e-1b73a8ab542f)



### Q5)	List the names of employee who are not Managers.


### QUERY:
```
 select ename from manager where designation!='manager';
```

### OUTPUT:


![dbms 2 6](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/2f7d0e0d-449c-4feb-8fb4-01f33e8c2420)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```
 select ename from manager where commission=0;
```


### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/b96590aa-285a-4f0e-9571-c1e55bfbd58c)


### Q8) List the Details of Employees who's salary is more than 30000.


### QUERY:
```
 select * from manager where annualsalary>30000;
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/96a638a9-8d39-401d-a6f2-721299fcc54e)




### Q9)	display the no of rows present in the table


### QUERY:
```
 select count(*) as rownumber from manager;
```

### OUTPUT:

![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/da8a8b28-ac7e-4073-a57b-4d2b2aa49e02)



### Q10) List the names of employees not belonging to dept no  10


### QUERY:
```
 select ename from manager where deptno NOT IN (10);
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/04c4def0-76fb-481a-9ff5-6a8034f6b810)


### Q11) Find number of rows in the table EMP

### QUERY:
```
select count(*) as rownumber from manager;
```

### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/7996c608-b18b-4e89-833e-b7373db0f5e0)


### Q12) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
 select max(salary) as maximumsal,min(salary) as minimumsal,avg(salary) as averagesal from manager;
```


### OUTPUT:

![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/a04a8be5-da43-4e3e-8b36-5171a68c60a8)



### Q13) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```
### OUTPUT:
![image](https://github.com/svarsha220/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/127709117/3d70bf89-3d92-42cb-be88-66d7ef09ca32)

### RESULT:
Thus the DML command was executed successfully
