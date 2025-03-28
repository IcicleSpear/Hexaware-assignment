# ASSIGNMENT - Student Information System (SIS)
## J502 Abhishek.A.G

### CREATION OF DATABASE AND TABLES
```
create database SISDB;
use SISDB;

create table Students(student_id int primary key auto_increment,
			first_name varchar(50) not null,
			last_name varchar(50) not null,
			date_of_birth date,
			email varchar(100) unique,phone_number varchar(15));

create table Teacher(
        teacher_id int primary key auto_increment,
        first_name varchar(50) not null,
        last_name varchar(50) not null,
        email varchar(100) unique);

create table Courses(
	course_id int primary key auto_increment,
            course_name varchar(100) not null,
            credits int check (credits>0),
            teacher_id int,
            foreign key (teacher_id) references Teacher(teacher_id));
            
create table Enrollments(
            enrollment_id int primary key auto_increment,
            student_id int,
            course_id int,
            enrollment_date date,
            foreign key (student_id) references Students(student_id),
            foreign key(course_id) references Courses(course_id));

            
create table Payments(
            payment_id int primary key auto_increment,
            student_id int,
            amount decimal(10,2),
            payment_date date,
            foreign key (student_id) references Students(student_id));*/
```
## DATABASE DESCRIPTION :
 ![image](https://github.com/user-attachments/assets/4e877065-dc1b-41e6-a9cd-fd6546afa8ea)

## TABLE DESCRIPTION : 
  ![image](https://github.com/user-attachments/assets/dfceeddd-ae21-472d-a728-c8400183a162)
![image](https://github.com/user-attachments/assets/ffcd5711-6218-4fb9-a8d4-4e6957144002)
![image](https://github.com/user-attachments/assets/7f16cd06-db2d-4a63-bc58-e7c49f306fbe)
![image](https://github.com/user-attachments/assets/0b4c6bb6-2c6d-46ca-ba2a-94da6e8a7298)
![image](https://github.com/user-attachments/assets/1e35f8b6-862e-40dc-9d46-d3f0bb805465)

### Insertion Of Data
```
INSERT INTO Students (first_name, last_name, date_of_birth, email, phone_number) VALUES
('Amit', 'Sharma', '2000-05-14', 'amit.sharma@gmail.com', '9876543210'),
('Priya', 'Verma', '1999-08-22', 'priya.verma@yahoo.com', '9823456789'),
('Rahul', 'Patel', '2001-03-10', 'rahul.patel@outlook.com', '7894561230'),
('Sneha', 'Reddy', '2002-12-05', 'sneha.reddy@gmail.com', '9123456780'),
('Vikram', 'Singh', '1998-09-18', 'vikram.singh@gmail.com', '9012345678'),
('Ananya', 'Nair', '2000-01-25', 'ananya.nair@hotmail.com', '8899776655'),
('Manish', 'Kumar', '1997-06-30', 'manish.kumar@gmail.com', '9876123450'),
('Pooja', 'Mishra', '2001-11-12', 'pooja.mishra@gmail.com', '8887766554'),
('Arjun', 'Mehta', '1999-04-04', 'arjun.mehta@gmail.com', '9786543210'),
('Divya', 'Pillai', '2002-07-19', 'divya.pillai@gmail.com', '9876432109');

INSERT INTO Teacher (first_name, last_name, email) VALUES
('Suresh', 'Iyer', 'suresh.iyer@college.edu'),
('Lakshmi', 'Menon', 'lakshmi.menon@college.edu'),
('Rajesh', 'Deshmukh', 'rajesh.deshmukh@college.edu'),
('Neha', 'Kapoor', 'neha.kapoor@college.edu'),
('Arvind', 'Chatterjee', 'arvind.chatterjee@college.edu'),
('Sunita', 'Mohan', 'sunita.mohan@college.edu'),
('Vivek', 'Tripathi', 'vivek.tripathi@college.edu'),
('Kavita', 'Joshi', 'kavita.joshi@college.edu'),
('Ramesh', 'Rao', 'ramesh.rao@college.edu'),
('Meena', 'Saxena', 'meena.saxena@college.edu');

 

INSERT INTO Courses (course_name, credits, teacher_id) VALUES
('Data Structures', 4, 1),
('Database Management Systems', 3, 2),
('Operating Systems', 4, 3),
('Computer Networks', 3, 4),
('Software Engineering', 3, 5),
('Machine Learning', 4, 6),
('Artificial Intelligence', 4, 7),
('Web Technologies', 3, 8),
('Cloud Computing', 3, 9),
('Cyber Security', 4, 10);
 
INSERT INTO Enrollments (student_id, course_id, enrollment_date) VALUES
(1, 1, '2024-01-15'),
(2, 2, '2024-01-16'),
(3, 3, '2024-01-17'),
(4, 4, '2024-01-18'),
(5, 5, '2024-01-19'),
(6, 6, '2024-01-20'),
(7, 7, '2024-01-21'),
(8, 8, '2024-01-22'),
(9, 9, '2024-01-23'),
(10, 10, '2024-01-24');
 
INSERT INTO Payments (student_id, amount, payment_date) VALUES
(1, 15000.00, '2024-01-25'),
(2, 12000.00, '2024-01-26'),
(3, 13000.00, '2024-01-27'),
(4, 14000.00, '2024-01-28'),
(5, 11000.00, '2024-01-29'),
(6, 16000.00, '2024-01-30'),
(7, 17000.00, '2024-01-31'),
(8, 15500.00, '2024-02-01'),
(9, 12500.00, '2024-02-02'),
(10, 14500.00, '2024-02-03');
 ```
![image](https://github.com/user-attachments/assets/3981c98e-ded9-4705-b074-ef9c977eadf2)

![image](https://github.com/user-attachments/assets/fdd4e73f-52b6-4933-80d9-702694b153e2)

![image](https://github.com/user-attachments/assets/a08a6225-586a-4755-923b-c74b01f4188b)

![image](https://github.com/user-attachments/assets/3c598a9a-da38-43b8-af60-cc80898906b8)

![image](https://github.com/user-attachments/assets/d7213a8f-39f5-4fd2-b8a2-3db7a1a291b5)




## TASK 2 : Select, Where, Between, AND, LIKE 

### 1. Write an SQL query to insert a new student into the "Students" table with the following details: a. First Name: John b. Last Name: Doe c. Date of Birth: 1995-08-15 d. Email: john.doe@example.come. Phone Number: 1234567890
```insert into Students (first_name,last_name,date_of_birth,email,phone_number) values('John','Doe','1995-08-15','john.doe@example.com','1234567890');```

### 2. Write an SQL query to enroll a student in a course. Choose an existing student and course and insert a record into the "Enrollments" table with the enrollment date.
   ```insert into Enrollments(student_id,course_id,enrollment_date) values(2,5,'2025-03-18');```

### 3. Update the email address of a specific teacher in the "Teacher" table. Choose any teacher and modify their email address
   ```update Teacher set email='thisisupdateemail@gmail.com' where teacher_id=4;```

### 4. Write an SQL query to delete a specific enrollment record from the "Enrollments" table. Select an enrollment record based on the student and course.
   ```delete from Enrollments where student_id=6 and course_id=6;```


### 5. Update the "Courses" table to assign a specific teacher to a course. Choose any course and teacher from the respective tables.
   ``` update Courses set teacher_id=2 where course_id=3;```

### 6. Delete a specific student from the "Students" table and remove all their enrollment records from the "Enrollments" table. Be sure to maintain referential integrity.
   ```
    delete from Enrollments where student_id=7;
   delete FROM Payments WHERE student_id = 7;
   delete from Students where student_id=7;
```


### 7. Update the payment amount for a specific payment record in the "Payments" table. Choose any payment record and modify the payment amount.
   ```update Payments set amount=20000 where payment_id=6;```

## TASK 3 : Aggregate functions, Having, Order By, GroupBy and Joins
### 1. Write an SQL query to calculate the total payments made by a specific student.You will need to join the "Payments" table with the "Students" table based on the student's ID.
```
   select s.student_id,concat(first_name,' ',last_name) as student_name,sum(p.amount) as total_payment
		from Students s inner join Payments p on s.student_id=p.student_id 
    where s.student_id=5 group by s.student_id,student_name;
```
![image](https://github.com/user-attachments/assets/5efeb710-3959-47b2-b809-10c5f306928e)

### 2. Write an SQL query to retrieve a list of courses along with the count of students enrolled in each course. Use a JOIN operation between the "Courses" table and the "Enrollments" table.
  ```
      select c.course_name,count(e.student_id) 
			from Courses c inner join Enrollments e on c.course_id=e.course_id 
			group by c.course_id,c.course_name;
```
![image](https://github.com/user-attachments/assets/97da57ce-ca4c-4095-97f0-0c15eb3e1490)

 
### 3. Write an SQL query to find the names of students who have not enrolled in any course. Use a LEFT JOIN between the "Students" table and the "Enrollments" table to identify students without enrollments.
```
   select s.student_id,concat(s.first_name,' ',s.last_name) as student_name
	         from Students s left join Enrollments e on s.student_id=e.student_id
                        where e.student_id is NULL;
```
![image](https://github.com/user-attachments/assets/eaae340f-2e54-4819-b87a-2501a4003151)

### 4. Write an SQL query to retrieve the first name, last name of students, and the names of the courses they   are enrolled in. Use JOIN operations between the "Students" table and the "Enrollments" and "Courses" tables.
   ```
   select s.first_name,s.last_name,c.course_name 
		from Students s inner join Enrollments e on s.student_id=e.student_id 
                inner join Courses c on e.course_id=c.course_id
                group by s.student_id,c.course_name;
```
 ![image](https://github.com/user-attachments/assets/da15dcc6-548f-4260-9336-10a961d8928b)

### 5. Create a query to list the names of teachers and the courses they are assigned to. Join the "Teacher" table with the "Courses" table.
```
   select t.first_name,t.last_name,course_id 
			from Teacher t inner join Courses c on t.teacher_id=c.teacher_id;
```
![image](https://github.com/user-attachments/assets/273a9054-5ccc-458a-bab1-bbeef5ab79af)

### 6. Retrieve a list of students and their enrollment dates for a specific course. You'll need to join the "Students" table with the "Enrollments" and "Courses" tables.
```
   select concat(s.first_name,' ',s.last_name) as student_name,e.enrollment_date,c.course_name 
		from Students s inner join Enrollments e on s.student_id=e.student_id
 		inner join Courses c on c.course_id=e.course_id where c.course_name='Data Structures';
```
![image](https://github.com/user-attachments/assets/95c7eeed-6a9b-4609-840a-4ca0ab4d8b26)

### 7. Find the names of students who have not made any payments. Use a LEFT JOIN between the "Students" table and the "Payments" table and filter for students with NULL payment records.
```
   select concat(s.first_name,' ',s.last_name) as student_name 
	from Students s left join Payments p on s.student_id=p.student_id where p.payment_id is null;
```
![image](https://github.com/user-attachments/assets/50d87343-90c7-4290-b15b-d1fa81c24e09)
 
### 8. Write a query to identify courses that have no enrollments. You'll need to use a LEFT JOIN between the "Courses" table and the "Enrollments" table and filter for courses with NULL enrollment records.
   ```
   select c.course_id,c.course_name from Courses c left join Enrollments e 
   on c.course_id=e.course_id where e.enrollment_id is null;
```
   ![image](https://github.com/user-attachments/assets/5e0dbae2-08ed-4f95-abba-b28175374b31)

 
### 9. Identify students who are enrolled in more than one course. Use a self-join on the "Enrollments" table to find students with multiple enrollment records.
```
SELECT DISTINCT e1.student_id FROM Enrollments e1 JOIN Enrollments e2 
ON e1.student_id =  e2.student_id AND e1.course_id <> e2.course_id;
```
![image](https://github.com/user-attachments/assets/ad7062e8-c42b-4eca-a25f-0b68f1621881)

 
### 10. Find teachers who are not assigned to any courses. Use a LEFT JOIN between the "Teacher" table and the "Courses" table and filter for teachers with NULL course assignments.
``` 
    select t.first_name from Teacher t left join 
    Courses c on t.teacher_id=c.teacher_id where c.course_id is null; 
```
![image](https://github.com/user-attachments/assets/577e946f-1e31-4614-8dba-7099033cf06b)


 
## TASK 4 : Subquery and its type

### 1. Write an SQL query to calculate the average number of students enrolled in each course. Use aggregate functions and subqueries to achieve this.
```
   select avg(student_count) from (
		select course_id,count(student_id) as student_count from Enrollments group by course_id
                ) as course_count;
 ```
![image](https://github.com/user-attachments/assets/3b642d9f-2cb4-4d81-a8cb-1f1d582829db)

### 2. Identify the student(s) who made the highest payment. Use a subquery to find the maximum payment amount and then retrieve the student(s) associated with that amount.
```
select * from Students where student_id in(select student_id from Payments where amount=(select max(amount) from Payments));
```
![image](https://github.com/user-attachments/assets/92ce699a-8dde-46ff-9a4b-3e1ccfb33ae8)

### 3. Retrieve a list of courses with the highest number of enrollments. Use subqueries to find the course(s) with the maximum enrollment count.
   ```
select * from Courses where course_id in(
			select course_id from(select course_id,count(*) as enrollment_count from Enrollments group by course_id) as CourseCount
		        where enrollment_count=(select max(enrollment_count) from (select count(*) as enrollment_count from Enrollments group by course_id) as EnrollmentCount));
```
![image](https://github.com/user-attachments/assets/500876a3-a4b7-490c-841f-09bb98f510cc)

 
### 4. Calculate the total payments made to courses taught by each teacher. Use subqueries to sum payments for each teacher's courses.
```
   select t.teacher_id,concat(t.first_name,' ',t.last_name),(select max(p.amount) from Payments p 
   where p.student_id in (select e.student_id from Enrollments e 
   where e.course_id in(select c.course_id from Courses c where c.teacher_id=t.teacher_id) ) as total_payment from Teacher t;
```
![image](https://github.com/user-attachments/assets/4464655d-ff41-4699-a5af-bfd1bda92461)

### 5. Identify students who are enrolled in all available courses. Use subqueries to compare a student's enrollments with the total number of courses.
   ```
select s.student_id,s.first_name,s.last_name from Students s 
   where (select count(*) from Enrollments e
where e.student_id=s.student_id)=(select count(*) from Courses);
```
   ![image](https://github.com/user-attachments/assets/567d9791-30df-4b02-9875-5fd6cdad2d80)

### 6. Retrieve the names of teachers who have not been assigned to any courses. Use subqueries to find teachers with no course assignments.
```
  select t.teacher_id,t.first_name,t.last_name from Teacher t 
   where t.teacher_id not in
   (select distinct teacher_id from Courses where teacher_id is not null);
```
   ![image](https://github.com/user-attachments/assets/fc399a03-044a-4dab-bbf1-d17871c9a9dc)

### 7. Calculate the average age of all students. Use subqueries to calculate the age of each student based on their date of birth.
   ```
select avg(student_age) from
(select student_id,timestampdiff(year,date_of_birth,CURDATE())
   as student_age from Students)as AGE;
```
   ![image](https://github.com/user-attachments/assets/ef287048-0334-4178-bc62-a5f9ade64287)

### 8. Identify courses with no enrollments. Use subqueries to find courses without enrollment records.
```
   select c.course_id,c.course_name from Courses c
 where c.course_id not in (select distinct course_id from Enrollments where course_id is not null);
```
   ![image](https://github.com/user-attachments/assets/3f55b19e-d842-40c9-804f-945c225d6cf1)
 
### 9. Calculate the total payments made by each student for each course they are enrolled in. Use subqueries and aggregate functions to sum payments.
```
    select student_id,
		(select first_name from Students s where s.student_id=e.student_id) as first_name,
		(select last_name from Students s where s.student_id=e.student_id) as last_name,
		(select course_name from Courses c where c.course_id=e.course_id) as course_name,
		(select sum(amount) from Payments p where p.student_id=e.student_id) as fees_paid from Enrollments e;
```
![image](https://github.com/user-attachments/assets/4db7ae63-a1b4-4bd3-b6d7-f8778366665b)

### 10. Identify students who have made more than one payment. Use subqueries and aggregate functions to count payments per student and filter for those with counts greater than one.
```
  select student_id,first_name,last_name from Students
where student_id in(select student_id from Payments
group by student_id having count(payment_id)>1);
```
![image](https://github.com/user-attachments/assets/d136fc7d-7c2e-42aa-8487-1f126b092c5f)



### 11. Write an SQL query to calculate the total payments made by each student. Join the "Students" table with the "Payments" table and use GROUP BY to calculate the sum of payments for each student.
```
        select s.student_id,s.first_name,s.last_name,sum(p.amount) from Students s join Payments p on s.student_id=p.student_id group by s.student_id;
```
![image](https://github.com/user-attachments/assets/2918ddde-436a-4f92-a286-e8c8b6028a3d)


### 12. Retrieve a list of course names along with the count of students enrolled in each course. Use JOIN operations between the "Courses" table and the "Enrollments" table and GROUP BY to count enrollments.
   ```
    select c.*,count(e.student_id) as student_count from Courses c left join Enrollments e on c.course_id=e.course_id group by c.course_id;
```
![image](https://github.com/user-attachments/assets/f4b22474-9943-48f0-86b0-335d80609cc3)


### 13. Calculate the average payment amount made by students. Use JOIN operations between the "Students" table and the "Payments" table and GROUP BY to calculate the average.
```
  select s.first_name,s.last_name,s.student_id,avg(p.amount) from Students s left join Payments p on s.student_id=p.student_id group by s.student_id;   
```
![image](https://github.com/user-attachments/assets/c943fad0-2917-4232-814f-45cd8066b15a)

 











