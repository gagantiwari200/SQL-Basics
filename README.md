create database if not exists dress_data;
use dress_data;

create table if not exists dress(
Dress_id int(40) ,
Style varchar(60) ,
Price varchar(40) ,  
Rating varchar(30) ,
Size varchar(50) ,
Season varchar(40) , 
Neckline varchar(40) ,
`Sleeve Length` varchar(30) ,
Waistline varchar(40) ,
Material varchar(60) , 
`Fabric Type` varchar (30) , 
Decoration varchar(40) ,
`Pattern Type` varchar(30) ,
Recommendation  varchar(60));

LOAD DATA INFILE 
'D:/AttributeDataSet.csv'
into table dress
FIELDS TERMINATED by ','
ENCLOSED by '"'
lines terminated by '\n'
IGNORE 1 ROWS;

SELECT * from dress;

create table if not exists Dress1(
Dress_id int auto_increment,
Student_name varchar(40),
Student_email varchar(40),
Student_address varchar(60),
Primary key (dress_id));

SELECT * from dress1;

Insert into Dress1 values(1,'Gagan','sky@yahoo.com','Pune'),
(2,'Avni','Avni@yahoo.com','Nashik'),
(3,'Guru','Guru@yahoo.com','Mumbai'),
(4,'Ashoka','Ashoka@yahoo.com','Bangalore'),
(5,'Aakash','Aaksh@yahoo.com','Jaipur'),
(6,'Yash','Yash@yahoo.com','Chandigarh'),
(7,'Sky','sky@yahoo.com','Indore');


create table if not exists Dress2(
Dress_id int not NULL auto_increment,
Student_name varchar(40),
Student_email varchar(40),
Student_address varchar(60),
Primary key (dress_id));

Insert into Dress2(Student_name, Student_email, Student_address) values('Avish','Avish@yahoo.com','Pune'),
('Avni','Avni@yahoo.com','Nashik'),
('Guru','Guru@yahoo.com','Mumbai'),
('Ashoka','Ashoka@yahoo.com','Bangalore'),
('Aakash','Aaksh@yahoo.com','Jaipur'),
('Yash','Yash@yahoo.com','Chandigarh'),
('Sky','sky@yahoo.com','Indore');

SELECT * from dress2;

create table if not exists dress3(
Dress_id int,
Student_name varchar(40),
Student_email varchar(40),
Student_address varchar(60),
Student_fees int check(Student_fess >10000));

Insert into Dress3 values(1,'Avish','Avish@yahoo.com','Pune',30000),
(2,'Avni','Avni@yahoo.com','Nashik',30000),
(3,'Guru','Guru@yahoo.com','Mumbai',40000),
(4,'Ashoka','Ashoka@yahoo.com','Bangalore',44000),
(5,'Aakash','Aaksh@yahoo.com','Jaipur',80000),
(6,'Yash','Yash@yahoo.com','Chandigarh',70000),
(7,'Sky','sky@yahoo.com','Indore',40000);

create table if not exists Dress4(
Dress_id int,
Student_name varchar(40),
Student_email varchar(40),
Student_address varchar(60) check (Student_address = 'Pune'),
Student_fees int CHECK(Student_fees >10000));

Insert into Dress4 values(1,'Avish','Avish@yahoo.com','Mumbai',20000);

Insert into Dress4 values(1,'Avish','Avish@yahoo.com','Pune',20000);

Alter table Dress4 add constraint check (Dress_id > 0);

Insert into Dress4 values(1,'Kanika','Knika@yahoo.com','Pune',30000);

create table if not exists Dress5(
Dress_id int not null auto_increment,
Student_name varchar(40),
Student_email varchar(40),
Student_address varchar(60) check (Student_address = 'Pune'),
Student_fees int CHECK(Student_fees >10000));

create table if not exists class6(
Dress_id int not null default 0,
Student_name varchar(40),
Student_email varchar(40),
Student_address varchar(60) check (Student_address = 'Pune'),
Student_fees int CHECK(Student_fees >10000));

Insert into class6(Student_name, Student_email, Student_address, Student_fees) values('Kanika','Knika@yahoo.com','Pune',52000);

select * from class6;

create table if not exists class7(
Dress_id int auto_increment ,
Student_name varchar(40) NOT NULL default 'Unknown',
Student_email varchar(40) unicode NOT NULL,
Student_address varchar(60) check (Student_address = 'Pune'),
Student_fees int CHECK(Student_fees >10000),
primary key (Dress_id));

select * from class7;
Insert into class7(Student_name, Student_email, Student_address, Student_fees) values('Rakesh','Rakesh@yahoo.com','Pune',52000),
('Avni','Avni@yahoo.com','Pune',62000),
('Guru','Guru@yahoo.com','Pune',57000),
('Ashoka','Ashoka@yahoo.com','Pune',82000),
('Aakash','Aaksh@yahoo.com','Pune',53000),
('Yash','Yash@yahoo.com','Pune',55000),
('Sky','sky@yahoo.com','Pune',52089);
