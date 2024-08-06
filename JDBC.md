### What is JDBC?
JDBC standard API is used to link Java applications and relational databases. It provides a collection of classes and interfaces that let programmers to use the Java programming language to communicate with the database. The classes and interface of JDBC allow the application to send requests which are made by users to the specified database. There are generally four components of JDBC by which it interacts with the database:

1. JDBC API-: It provides various methods and interfaces for easy communication with the database
2. JDBC Driver manager-: It loads a database-specific driver in an application to establish a connection with a database. It is used to make a database-specific call to the database to process the user request.
3. JDBC Test Suite-: It is used to test the operation(such as insertion, deletion, updation) being performed by JDBC Drivers.
4. JDBC-ODBC Bridge Drivers-: Work as adaptors(translators)

### What is JDBC Driver
These are client side adaptors(translator) that converts request from java program to a protocol that DBMS can understand
1. JDBC-ODBC Bridge driver
2. Native-API driver
3. Network Protocol driver
4. Thin driver

### What are the steps to connect to the database in Java?
There are certain steps to connect the database and Java Program as mentioned below:

1. Import the Packages
2. Load the drivers using the forName() method
3. Register the drivers using DriverManager
4. Establish a connection using the Connection class object
5. Create a statement
6. Execute the query
7. Close the connections

### What does the JDBC ResultSet interface?
JDBC ResultSet interface is used to store the resultant data coming from the database and use it in our Java Program. ResultSet object points the cursor before the first row of the result data. Using the next() method, we can iterate through the ResultSet.

### What is the JDBC Rowset?
A JDBC RowSet provides a way to store the data in tabular form. RowSet is an interface in java that can be used within the java.sql package. The connection between the RowSet object and the data source is maintained throughout its life cycle.

### What is the role of the JDBC DriverManager class?
JDBC DriverManager class acts as an interface for users and Drivers. It is used in many ways as mentioned below:
1. It is used to load a database specific driver.
2. Helps to keep track of the drivers that are available.
3. It can help to establish a connection between a database and the appropriate drivers.

### JDBC is advance version of ODBC whic is platform dependent

### Types of statement in JDBC
1. Create statement - static query without parameters like "select * from user"
2. Prepared statement - recompiled query with parameters like "select * from user where name=?"


