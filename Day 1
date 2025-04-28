--create database Day_1
--use Day_1

--Solving 1 - 5 SQL Quires 

--CREATE TABLE Department (
--    DepartmentID INT PRIMARY KEY,
--    DepartmentName VARCHAR(50)
--);

--CREATE TABLE Employee (
--    EmployeeID INT PRIMARY KEY,
--    Name VARCHAR(100),
--    DepartmentID INT,
--    Salary DECIMAL(10,2),
--    HireDate DATE,
--    FOREIGN KEY (DepartmentID) REFERENCES Department(DepartmentID)
--);


--INSERT INTO Department (DepartmentID, DepartmentName) VALUES
--(1, 'HR'),
--(2, 'IT'),
--(3, 'Finance'),
--(4, 'Marketing'),
--(5, 'Sales'),
--(6, 'Operations'),
--(7, 'Customer Support'),
--(8, 'Legal'),
--(9, 'Engineering'),
--(10, 'R&D');


--INSERT INTO Employee (EmployeeID, Name, DepartmentID, Salary, HireDate) VALUES
--(1, 'Alice Johnson', 1, 70000, '2021-03-15'),
--(2, 'Bob Williams', 1, 80000, '2020-07-22'),
--(3, 'Charlie Smith', 1, 95000, '2018-06-10'),
--(4, 'David Brown', 2, 120000, '2022-01-05'),
--(5, 'Emma Davis', 2, 110000, '2019-09-12'),
--(6, 'Frank Miller', 2, 130000, '2017-08-03'),
--(7, 'Grace Wilson', 3, 90000, '2023-04-14'),
--(8, 'Hank Taylor', 3, 95000, '2021-11-30'),
--(9, 'Ivy Moore', 3, 105000, '2018-05-21'),
--(10, 'Jack White', 4, 60000, '2020-03-25'),
--(11, 'Katie Lewis', 4, 75000, '2019-08-17'),
--(12, 'Liam Hall', 4, 85000, '2022-10-29'),
--(13, 'Michael Scott', 5, 72000, '2017-02-11'),
--(14, 'Natalie King', 5, 78000, '2021-06-19'),
--(15, 'Oscar Peterson', 5, 92000, '2018-11-23'),
--(16, 'Paul Reed', 6, 100000, '2023-09-05'),
--(17, 'Quinn Foster', 6, 98000, '2019-12-15'),
--(18, 'Ryan Clark', 6, 115000, '2018-03-08'),
--(19, 'Sophia Green', 7, 65000, '2020-08-21'),
--(20, 'Tom Baker', 7, 70000, '2022-07-14'),
--(21, 'Uma Harris', 7, 74000, '2021-09-09'),
--(22, 'Victor Lee', 8, 86000, '2017-06-22'),
--(23, 'Wendy Carter', 8, 91000, '2020-02-18'),
--(24, 'Xavier Morris', 8, 97000, '2019-04-25'),
--(25, 'Yara Nelson', 9, 95000, '2021-07-13'),
--(26, 'Zane Carter', 9, 98000, '2018-04-06'),
--(27, 'Anna Collins', 10, 105000, '2023-11-15'),
--(28, 'Ben Adams', 10, 112000, '2019-07-08'),
--(29, 'Chloe Sanders', 1, 89000, '2022-05-17'),
--(30, 'Daniel Roberts', 2, 125000, '2017-12-22'),
--(31, 'Eva Richardson', 3, 93000, '2020-06-03'),
--(32, 'Felix Turner', 4, 82000, '2023-01-15'),
--(33, 'Gina Myers', 5, 72000, '2019-02-07'),
--(34, 'Harry Scott', 6, 99000, '2018-09-12'),
--(35, 'Isla Thompson', 7, 67000, '2021-11-19'),
--(36, 'James Walker', 8, 95000, '2023-08-25'),
--(37, 'Kelly Bennett', 9, 88000, '2017-05-20'),
--(38, 'Loren Brooks', 10, 107000, '2022-07-31'),
--(39, 'Mason Phillips', 1, 93000, '2019-04-14'),
--(40, 'Nina Sanders', 2, 119000, '2017-08-29'),
--(41, 'Owen Foster', 3, 96000, '2021-03-21'),
--(42, 'Penny Ross', 4, 83000, '2020-11-22'),
--(43, 'Quentin Davis', 5, 78000, '2023-06-12'),
--(44, 'Rachel Moore', 6, 112000, '2018-10-17'),
--(45, 'Sam Parker', 7, 68000, '2022-09-05'),
--(46, 'Tina Evans', 8, 97000, '2019-01-07'),
--(47, 'Umar Khan', 9, 89000, '2017-06-26'),
--(48, 'Vera James', 10, 110000, '2021-05-14'),
--(49, 'Will Grant', 1, 91000, '2020-07-09'),
--(50, 'Xena Carter', 2, 122000, '2023-02-18');

--Find the top 3 highest-paid employees in each department.

--with cte as (
--select 
--d.DepartmentName,e.Salary,
--DENSE_RANK() over(partition by d.departmentname order by salary desc) as rn
--from employee e
--join Department  d
--on e.DepartmentID = d.DepartmentID)
--select 
--DepartmentName,Salary
--from cte
--where rn <=3


 --2.Find the average salary of employees hired in the last 5 years.

--select 
--AVG(Salary) as Avg_Salary
--from Employee
--where HireDate >= DATEADD(Year,-5,(select MAX(year(hiredate)) from Employee))


--3.Retrive Department Name where there are more than 5 employees

--select 
--d.DepartmentName,COUNT(e.EmployeeID) as cnt
--from Employee e
--join Department d
--on e.DepartmentID =d.DepartmentID
--group by d.DepartmentName
--having COUNT(e.EmployeeID) >5


--4.Find the employees whose salry is less than the average salary of employees hired in  the last 5 years.

--select * from Employee
--where Salary <(
--select 
--AVG(Salary) as Avg_Salary
--from Employee
--where HireDate >= DATEADD(Year,-5,(select MAX(year(hiredate)) from Employee)))


--5.Find Employees with a Salary Above the Department Average

--select 
--Name,b.DepartmentID,Salary
--from Employee a
--join (
--select 
--d.DepartmentID,AVG(Salary) as Avg_Sal
--from Employee e
--join Department d
--on e.DepartmentID = d.DepartmentID
--group by d.DepartmentID) b
--on a.DepartmentID = b.DepartmentID
--where Salary>Avg_Sal
--order by b.DepartmentID





      

