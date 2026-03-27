# BANK DATABASE MANAGEMENT SYSTEM

**Name:** PRATIK YASHWANT JADHAV 

Course: SQL

Subject: Database Management System

Tool Used: PostgreSQL 


Institute: AI_Sparks

## 1. INTRODUCTION 
A Bank Database Management System is designed to manage banking operations efficiently using a relational database. It stores and organizes important banking data such as customer information, accounts, transactions, and branchstaff details. 
This system allows the bank to maintain records digitally, reducing manual work and improving accuracy. Using SQL queries, the system enables efficient data storage, retrieval, updating, and deletion.

The project demonstrates how database systems help manage structured financial data securely and efficiently.


## 2. OBJECTIVES

The objectives of this project are:

• To create a structured database for banking operations
• To store and manage customer information
• To maintain bank account details
• To track deposits, withdrawals, and transactions
• To demonstrate SQL commands like CREATE, INSERT, SELECT, UPDATE, and DELETE
• To implement relationships between tables using primary and foreign keys

## 3. SYSTEM REQUIREMENTS
Software Requirements

• PostgreSQL/SQL Database Server

##  4. Database Name

BANK

## 5. Features

Customer information management,
Account creation and balance tracking,
Deposit and withdrawal transaction handling,
Automatic balance updates using triggers,
Staff management system,
Role-based user access control.

## 6.Database Schema



## A. Customer_details

Stores personal information about bank customers.

Column	Data Type	Description
Customer_Id	BIGINT	Primary Key
Firstname	VARCHAR(50)	Customer first name
Lastname	VARCHAR(50)	Customer last name
DOB	DATE	Date of birth
PAN	VARCHAR(10)	Unique PAN number
KYC	VARCHAR(50)	KYC document ID
Cust_address	TEXT	Customer address
Email	VARCHAR(25)	Unique email
Mobile_no	VARCHAR(10)	Unique phone number





## B. Account_Details

Stores customer bank account details.

Column	Data Type	Description
Account_number	BIGINT	Primary Key
Customer_Id	BIGINT	Foreign Key
Account_type	VARCHAR(10)	Type of account
Cash_Balance	DECIMAL(10,2)	Current balance
DateCreated	DATE	Account creation date

Relationship:
Customer_details → Account_Details (1 : Many)






## C. Transaction_Details

Records deposits and withdrawals.

Column	Data Type	Description
TransactionID	BIGINT	Primary Key
Account_number	BIGINT	Foreign Key
Transaction_Type	VARCHAR(20)	Deposit / Withdrawal
Amount	DECIMAL(10,2)	Transaction amount
Transaction_Date	TIMESTAMP	Date and time

Relationship:
Account_Details → Transaction_Details (1 : Many)






## D. Staff_details

Stores bank employee information.

Column	Data Type	Description
Staff_Id	INT	Primary Key
Frist_name	VARCHAR(50)	First name
Last_name	VARCHAR(50)	Last name
staff_position	VARCHAR(20)	Staff role
Branch	VARCHAR(50)	Branch location



## E. Trigger Implementation

A trigger is implemented to automatically update the account balance whenever a transaction is inserted.

Trigger Name:
transfer_trigger

Function:
update_balance()

Behavior:

Deposit → Adds amount to account balance

Withdrawal → Subtracts amount from account balance



## 7. Example SQL Query


Create Customer Table

CREATE TABLE Customer_details (
Customer_Id BIGINT PRIMARY KEY,
Firstname VARCHAR(50) NOT NULL,
Lastname VARCHAR(50) NOT NULL,
DOB DATE NOT NULL,
PAN VARCHAR(10) UNIQUE,
KYC VARCHAR(50),
Cust_address TEXT,
Email VARCHAR(25) UNIQUE,
Mobile_no VARCHAR(10) UNIQUE
);

Insert Customer

INSERT INTO Customer_details
VALUES
(20312364581,'Rajaram','Gaikwad','2000-02-01',
'RAJARG3541','RP1236547896',
'Swargate Pune','Rajaram564@gmail.com','9545701934');


## Roles and Users




Role-based access control is implemented to simulate different bank staff responsibilities.

Role	Description
Clerk	Handles customer and account records
Head Clerk	Manages account updates
Probationary Officer	Processes transactions
Service Manager	Supervises transaction operations
Branch Manager	Full database control

Example role creation:

CREATE ROLE clerk_anil50896 LOGIN PASSWORD 'Anil@2020';


## Relationships



Relationship	Type	Explanation
Customer → Account	1 : Many	One customer can have multiple accounts
Account → Transaction	1 : Many	One account can have many transactions
Staff → Branch	Many : 1	Many staff work in one branch





## 8. Simplified ER Structure




Customer_details
      |
      | 1
      |
      |------< Account_Details >------|
                                       |
                                       | 1
                                       |
                                  Transaction_Details



Staff_details
      |
      | Works At
      |
      Branch








## 9. OUTPUT

The database successfully stores information about customers, accounts, and transactions. Using SQL queries, the system can retrieve details such as account balances, customer information, and transaction history.

## Output Screenshots

### Customer Table


<img width="1555" height="205" alt="image" src="https://github.com/user-attachments/assets/bbed9641-db88-4eb1-b1ef-a442cef69c1b" />


### Account Table


<img width="777" height="210" alt="image" src="https://github.com/user-attachments/assets/38a7ee9b-431e-4794-8970-6550427900df" />


### Transaction Table


<img width="896" height="191" alt="image" src="https://github.com/user-attachments/assets/e7b4eb5e-5c2e-497c-b566-930bfe242302" />



### Staff Table 


<img width="909" height="207" alt="image" src="https://github.com/user-attachments/assets/a5ec1f61-ffc5-477a-b2b3-5161eb787e1a" />


### Trigger 


<img width="1612" height="84" alt="image" src="https://github.com/user-attachments/assets/60fe7cb6-e4b8-4419-a2c7-d02d80fefdbc" />






## 10. CONCLUSION

The Bank Database Management System (BDMS) project demonstrates how a relational database can be used to efficiently manage banking operations. The system successfully stores and manages important data such as customer details, account information, transactions, and staff records using structured SQL tables.

Through the implementation of primary keys, foreign keys, constraints, triggers and role-based access control, the database ensures data integrity, security and consistency. The trigger function automatically updates account balances after each transaction, which simulates real-world banking operations.


Overall, the BDMS project provides a strong foundation for understanding real-world banking database systems and practical SQL implementation.

This project helped in understanding:

• Database design
• Table relationships
• SQL queries
• Data manipulation and retrieval




