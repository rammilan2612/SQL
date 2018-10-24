# SQL
Some codes and queries of SQL

SQL query to find percentage of sale for each month in an quarter

create table emp_profes(
id varchar(4),
qtr varchar(2),
mnth varchar(10),
sale int)


insert into emp_profes values('101','Q1','Jan',1000000)
insert into emp_profes values('102','Q1','Feb',3000000)
insert into emp_profes values('103','Q1','Mar',5000000)

insert into emp_profes values('104','Q2','Apr',2000000)
insert into emp_profes values('105','Q2','May',4000000)
insert into emp_profes values('106','Q2','Jun',6000000)

insert into emp_profes values('107','Q3','Jul',7000000)
insert into emp_profes values('108','Q3','Aug',9000000)
insert into emp_profes values('109','Q3','Sep',1100000)

insert into emp_profes values('110','Q4','Oct',8000000)
insert into emp_profes values('111','Q4','Nov',1200000)
insert into emp_profes values('112','Q4','Dec',1400000)

select * from emp_profes 

select qtr, SUM(sale) from emp_profes group by qtr

select qtr,mnth,sale, (sale*100.00)/(select SUM(sale) from emp_profes i where i.qtr=o.qtr)as 'Percentage' from emp_profes o
