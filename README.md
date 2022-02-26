# Mini Bank Application

In any Bank Transaction, there are several parties involved to process transaction like a merchant, bank, receiver, etc. so there are several numbers reasons that transaction may get failed, declined, so to handle a transaction in Java, there is a JDBC (Java Database Connectivity) which provides us an API to connect, execute, fetch data from any databases. It provides the language Java database connectivity standards. It is used to write programs required to access databases.

Transactions in JDBC provide us a  feature that considers a complete SQL statement as one unit,  then executes once, and if any statement fails, the entire transaction fails. To use transaction, we have to set setAutoCommit(false); manually, and once all the statements are executed successfully, making changes in the database’s commit() method will be required. 

In this Mini Banking Application, to handle a transaction, we are using JDBC Transaction to make transactions consistent.  This Application Provides Menu-Driven Console Interface to a User Using that User can perform functions like create Account, Login, View Balance And Transfer Money To The Other Customer.



>Software Prerequisite:

MySQL:
MySQL is a full-featured relational database management system (RDBMS). MySQL is a free, open-source relational database management system that uses Structured Query Language (SQL), the most popular language for adding, accessing, and processing data in a database. MySQL is noted for its speed, reliability, and flexibility

Eclipse:
Eclipse is an IDE (interactive development environment) written to develop and debug (primarily) Java code. It contains a base workspace and an extensible plug-in system for customizing the environment. 



>Databases Setup:

Step 1: Create Database name bank

Step 2: Create Table name customer

// Create a database 
CREATE DATABASE BANK; 


// Create table
CREATE TABLE `customer` (

 `ac_no` int NOT NULL AUTO_INCREMENT,

 `cname` varchar(45) DEFAULT NULL,

 `balance` varchar(45) DEFAULT NULL,

 `pass_code` int DEFAULT NULL,

 PRIMARY KEY (`ac_no`),

 UNIQUE KEY `cname_UNIQUE` (`cname`)

) ;




>Eclipse Project Setup:

step1 : Create New Project

Step2 : Create A package name banking



>File Configuration:

![Screenshot31](https://user-images.githubusercontent.com/61544732/143549148-bd117a40-6931-46f8-8cd7-60ea25ca5d04.png)


>Create a Connection class in the banking package

Step 1: Include JDBC Driver for MySQL

String mysqlJDBCDriver = "com.mysql.cj.jdbc.Driver";

Class.forName(mysqlJDBCDriver);

Step 2: Create Connection Class using MySQL username and password

String url = "jdbc:mysql://localhost:3306/mydata";

String user = "root";

String pass = "123";

con = DriverManager.getConnection(url, user, pass);


