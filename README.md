CREATE TABLE DEPARTMENT_TABLE(
DEPARTMENT_ID INT primary key, 
DEPARTMENT_NAME VARCHAR2(15)
);

CREATE TABLE DESIGNATION_TABLE(
DESIGNATION_ID INT primary key,
DESIGNATION_NAME VARCHAR2(15)
);


CREATE TABLE ADDRESS_TABLE(
Address_id int primary key,
door_number int,
street VARCHAR2(15),
Landmark VARCHAR2(15),
area VARCHAR2(15),
pincode NUMBER(7),
district VARCHAR2(20),
State VARCHAR2(20)
);


Create table Employee_table(
emp_id int primary key,
emp_FirstName VARCHAR2(20),
emp_LastName VARCHAR2(20),
emp_Date_Of_join date,
emp_Date_of_Birth date,
emp_dept_id int,
emp_designation_id int,
emp_grade VARCHAR2(2),
emp_gender VARCHAR2(6),
emp_salary NUMBER(10,2),
emp_marital_status VARCHAR2(10),
emp_address_id int,
emp_contact NUMBER(15)
);


Create table Login_details(
login_id int primary key,
login_username VARCHAR2(20),
login_password VARCHAR2(30),
login_role VARCHAR2(10),
emp_id_ref int
);


ALTER TABLE Employee_table
ADD CONSTRAINT FK_department_id
FOREIGN KEY (emp_dept_id) REFERENCES Department_table(department_id);


ALTER TABLE Employee_table
ADD CONSTRAINT FK_dedignation_id
FOREIGN KEY (emp_designation_id) REFERENCES DESIGNATION_TABLE(DESIGNATION_ID);



ALTER TABLE Employee_table
ADD CONSTRAINT FK_address_id
FOREIGN KEY (emp_address_id) REFERENCES ADDRESS_TABLE(Address_id);



ALTER TABLE Login_details
ADD CONSTRAINT FK_emp_id
FOREIGN KEY (emp_id_ref) REFERENCES Employee_table(emp_id);




