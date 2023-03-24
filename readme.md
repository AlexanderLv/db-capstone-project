# WEEK1

## 1.1 Exercise: Setting up the repository

**Scenario**
Little Lemon need you to help them set up a booking system to keep track of which guests are visiting the restaurant and at what times. In this first stage of the task, you need to:
Set up a repository, or local directory to house your code.
Record all changes made within the system as they’re implemented.
And allow others to view, review and add to your code.
You can carry out these steps using your knowledge of version control and online collaboration. Review the instructions that follow for guidance on completing these tasks.
setting up repository for project
```shell
(base) ➜  db-capstone-project git init
Initialized empty Git repository in /Users/lvyang/Downloads/db-capstone-project/.git/

(base) ➜  db-capstone-project git:(master) echo "setting up repository for project"  > readme.md

(base) ➜  db-capstone-project git:(master) ✗ git add readme.md

(base) ➜  db-capstone-project git:(master) ✗ git commit -m "adding project readme"

[master (root-commit) 4549a23] adding project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.md

(base) ➜  db-capstone-project git:(master) git remote add origin git@github.com:AlexanderLv/db-capstone-project.git

(base) ➜  db-capstone-project git:(master) git remote -v
origin  git@github.com:AlexanderLv/db-capstone-project.git (fetch)
origin  git@github.com:AlexanderLv/db-capstone-project.git (push)

(base) ➜  db-capstone-project git:(master) git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 253 bytes | 253.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:AlexanderLv/db-capstone-project.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```
![](./week1/Setting%20up%20the%20repository.jpg)

## 1.2 Exercise: Set up the MySQL instance server in MySQL Workbench

Task 1
Creating a new user is the most secure way to connect to your MySQL database. In this first task, you need to use MySQL Workbench to create a new user account.

Here is some guidance for completing this task:
- Log in to the MySQL Server using the root user
- Select Administration tab from the Navigator section
- Select Add account.
- Provide a meaningful username and a strong password
- Grant the new user the right to perform all tasks.

![1.2.1.1.jpg](./week1/1.2.1.1.jpg)

![](./week1/1.2.1.2.jpg)

Task 2
To prepare for building and managing your database, you need to be connected to a MySQL server. In this task you need to create a new MySQL connection.

Here is some guidance for completing this task:
- In the MySQL Workbench home screen, select MySQL connection tab.
- Select the plus icon to open the Setup New Connection form.
- Fill in the form to create a new server instance.
- Click the Test Connection button to check that the settings work as required.

Once you have completed this task, you can use this connection to begin working with database schemas and SQL queries.
![](./week1/1.2.2.jpg)


## 1.3 Exercise: Create an ER diagram data model and implement it in MySQL
**Scenario**

Little Lemon needs to build a robust relational database system in MySQL in which they can store large amounts of data. They then need to easily manage and find this data as required. This database system should maintain information about the following aspects of the business:  
- Bookings
- Orders
- Order delivery status
- Menu
- Customer details
- and Staff information.


**Prerequisites**

Use MySQL Workbench to create the ER diagram and to implement it in your MySQL server.


**Task Instructions**

Little Lemon wants you to use MySQL Workbench to develop a relational database system and implement it in MySQL server. Save your database capstone project files in a folder on your machine and name it db-capstone-project.


Task 1
In this task, you need to create a normalized ER diagram (that adheres to 1NF, 2NF and 3NF) with relevant relationships to meet the data requirements of Little Lemon. When creating your diagram, include the following tables:
- Bookings: To store information about booked tables in the restaurant including booking id, date and table number
- Orders: To store information about each order such as order date, quantity and total cost
- Order delivery status: To store information about the delivery status of each order such as delivery date and status
- Menu: To store information about cuisines, starters, courses, drinks and desserts
- Customer details: To store information about the customer names and contact details
- Staff information: Including role and salary.

Here is some guidance for completing this task:
- Identify entities and related attributes.
- Identify primary and foreign keys.
- Define data types and constraints.
Once you have designed your ER diagram inside your MySQL Workbench Model Editor you then need to save your data model as LittleLemonDM and export it as a PNG file.
![](./week1/LittleLemonDM-ERD.png)

Task 2
In this second task, you need to implement the Little Lemon data model inside your MySQL server. Here is some guidance for completing this task:
- Use the forward engineer method in MySQL Workbench to implement the Little Lemon data model inside MySQL server. 
- Name your database LittleLemonDB.
- Export the LittleLemonDB as a single contained SQL file and save it in the db-capstone-project folder.


Task 3
In the third and final task, you need to show the databases in the MySQL server. Write a SQL code inside MySQL Workbench SQL editor to show all your databases in MySQL server. Check if the Little Lemon database is included in the list.
![](./week1/SHOW_DATABASES.jpg)


# WEEK2

## 2.1 Exercise: Create a virtual table to summarize data
**Scenario**
Little Lemon needs to retrieve data from their database. You can use your knowledge of MySQL to help them. As part of this task, you need to- 
- Create a virtual table to summarize data- 
- Use a JOIN statement to query data from multiple tables- 
- Create a SQL statement with a subquery.

You can carry out these steps using your knowledge of virtual tables, JOIN statements and SQL queries. Review the instructions that follow for guidance on completing these tasks.


**Prerequisites**
In the previous module, you developed a data model for Little Lemon and implemented it in your MySQL server. Your database should now contain several tables including the following:
- Menus,
- Orders,
- MenuItems
- and Customers.
These tables might have a different name within your database. However, they should still contain similar data to, and resemble the relationships in, the following diagram:
![](./week2/1.png)

You also need to use MySQL Workbench SQL editor to write the required subquery, virtual table and JOIN statements.

**Task instructions**
Little Lemon need you to create some reports on the orders placed in the restaurant. Complete the following tasks to help Little Lemon obtain the relevant information about the menu’s orders.


**Task 1**
In the first task, Little Lemon need you to create a virtual table called OrdersView that focuses on OrderID, Quantity and Cost columns within the Orders table for all orders with a quantity greater than 2. 

Here’s some guidance around completing this task: 
- Use a CREATE VIEW statement- 
- Extract the order id, quantity and cost data from the Orders table- 
- Filter data from the orders table based on orders with a quantity greater than 2. 

You can query the OrdersView table using the following syntax:
```mysql
Select * from OrdersView;
```
The output result of your query (depending on the data populated in your database) should be similar to the example in the following screenshot. 

![](./week2/2.png)

**SOLUTION**
```mysql
USE LittleLemonDB;

CREATE VIEW `OrdersView` AS
SELECT OrderID, Quantity, TotalCost
FROM Orders
WHERE Quantity > 2;
```


Task 2
For your second task, Little Lemon need information from four tables on all customers with orders that cost more than $150. Extract the required information from each of the following tables by using the relevant JOIN clause: 
- Customers table: The customer id and full name- 
- Orders table: The order id and cost- 
- Menus table: The menus name- 
- MenusItems table: course name and starter name.

The result set should be sorted by the lowest cost amount.
The output result of your query (depends on the data populated in your database) should be similar to the example in the following screenshot: 
![](./week2/3.png)

**SOLUTION**
```mysql
USE LittleLemonDB;

SELECT c.CustomerID, c.FullName, o.OrderID, o.TotalCost as Cost, Menus.MenuName, MenuItems.Courses as CourseName
FROM Customers as c JOIN Orders as o ON c.CustomerID = o.CustomerID
JOIN Menus ON o.MenuID = Menus.MenuID
JOIN MenuItems ON Menus.MenuID = MenuItems.MenuID
WHERE o.TotalCost > 150
ORDER BY o.TotalCost ASC;
```

Task 3
For the third and final task, Little Lemon need you to find all menu items for which more than 2 orders have been placed. You can carry out this task by creating a subquery that lists the menu names from the menus table for any order quantity with more than 2.

Here’s some guidance around completing this task: 
- Use the ANY operator in a subquer- 
- The outer query should be used to select the menu name from the menus table- 
- The inner query should check if any item quantity in the order table is more than 2. 

The output result of your query (depends on the data populated in your database) should be similar to the following screenshot:

![](./week2/4.png)

**SOLUTION**
```mysql
USE LittleLemonDB;

SELECT MenuName FROM Menus
JOIN Orders ON Menus.MenuID = Orders.MenuID
WHERE OrderID = ANY(SELECT OrderID FROM Orders WHERE Quantity > 2);
```

## 2.2 Exercise: Create optimized queries to manage and analyze data

Task 1
In this first task, Little Lemon need you to create a procedure that displays the maximum ordered quantity in the Orders table. 
Creating this procedure will allow Little Lemon to reuse the logic implemented in the procedure easily without retyping the same code over again and again to check the maximum quantity. 
You can call the procedure GetMaxQuantity and invoke it as follows:

```mysql
CALL GetMaxQuantity();
```
The output result of your query (depending on the data populated in your database) should be similar to the output in the following screenshot: 
![](./week2/5.png)

**SOLUTION**
```mysql
USE LittleLemonDB;

DELIMITER //
CREATE PROCEDURE GetMaxQuantity()
BEGIN
SELECT Quantity as `Max Quantity in Order` FROM Orders
ORDER BY Quantity DESC
LIMIT 1;
END //
DELIMITER ;

CALL GetMaxQuantity;
```


Task 2
In the second task, Little Lemon need you to help them to create a prepared statement called GetOrderDetail. This prepared statement will help to reduce the parsing time of queries. It will also help to secure the database from SQL injections.
The prepared statement should accept one input argument, the CustomerID value, from a variable. 
The statement should return the order id, the quantity and the order cost from the Orders table. 
Once you create the prepared statement, you can create a variable called id and assign it value of 1. 
Then execute the GetOrderDetail prepared statement using the following syntax:

```mysql
SET @id = 1;
EXECUTE GetOrderDetail USING @id;
```
![](./week2/6.png)

**SOLUTION**
```mysql
USE LittleLemonDB;

PREPARE GetOrderDetail FROM 'SELECT OrderID, Quantity, TotalCost FROM Orders WHERE OrderID = ?;';

SET @id = 	1;
EXECUTE GetOrderDetail USING @id;
```

Task 3
Your third and final task is to create a stored procedure called CancelOrder. Little Lemon want to use this stored procedure to delete an order record based on the user input of the order id.
Creating this procedure will allow Little Lemon to cancel any order by specifying the order id value in the procedure parameter without typing the entire SQL delete statement.   
If you invoke the CancelOrder procedure, the output result should be similar to the output of the following screenshot:

![](./week2/7.png)

**SOLUTION**

```mysql
USE LittleLemonDB;

DELIMITER //
CREATE PROCEDURE CancelOrder(IN id INT)
BEGIN
IF EXISTS(SELECT 1 FROM Orders WHERE OrderID = id)
THEN
DELETE FROM Orders WHERE OrderID = id; 
SELECT CONCAT("Order ", id, " is cancelled.") AS Confirmation;
ELSE
SELECT CONCAT("Order ", id, " does not exist.") AS Response;
END IF;
END //
DELIMITER ;

CALL CancelOrder(1);

```

## 2.3 Exercise: Create SQL queries to check available bookings based on user input


Task 1
Little Lemon wants to populate the Bookings table of their database with some records of data. Your first task is to replicate the list of records in the following table by adding them to the Little Lemon booking table. 

You can use simple INSERT statements to complete this task.

![](./week2/8.jpg)

Your output must resemble the following screenshot:

![](./week2/9.png)

**SOLUTION**

```mysql
USE LittleLemonDB;

SET SQL_SAFE_UPDATES = 0;
DELETE FROM bookings;
ALTER TABLE bookings AUTO_INCREMENT = 1;
SET SQL_SAFE_UPDATES = 1;

INSERT INTO bookings (BookingDate, TableNumber, CustomerID)
VALUES 
	("2022-10-10", 5, 1),
	("2022-11-12", 3, 3),
	("2022-10-11", 2, 2),
	("2022-10-13", 2, 1);

```


Task 2
For your second task, Little Lemon need you to create a stored procedure called CheckBooking to check whether a table in the restaurant is already booked. Creating this procedure helps to minimize the effort involved in repeatedly coding the same SQL statements.
The procedure should have two input parameters in the form of booking date and table number. You can also create a variable in the procedure to check the status of each table.
The output of your procedure should be similar to the following screenshot:

![](./week2/10.png)

**SOLUTION**
```mysql
USE LittleLemonDB;
DROP PROCEDURE IF EXISTS CheckBooking;
DELIMITER //

CREATE PROCEDURE CheckBooking (IN booking_date DATE, IN table_no INT)
BEGIN
IF EXISTS(SELECT 1 FROM Bookings WHERE BookingDate = booking_date AND TableNumber = table_no)
THEN
SELECT CONCAT("Table " , table_no, " is already booked.") AS `Booking status`; 
ELSE
SELECT CONCAT("Table " , table_no, " is not yet booked.") AS `Booking status`; 
END IF;
END //

DELIMITER ;
```


Task 3
For your third and final task, Little Lemon need to verify a booking, and decline any reservations for tables that are already booked under another name. 

Since integrity is not optional, Little Lemon need to ensure that every booking attempt includes these verification and decline steps. However, implementing these steps requires a stored procedure and a transaction. 

To implement these steps, you need to create a new procedure called AddValidBooking. This procedure must use a transaction statement to perform a rollback if a customer reserves a table that’s already booked under another name.  

Use the following guidelines to complete this task- 
- The procedure should include two input parameters in the form of booking date and table number- 
- It also requires at least one variable and should begin with a START TRANSACTION statement- 
- Your INSERT statement must add a new booking record using the input parameter's values- 
- Use an IF ELSE statement to check if a table is already booked on the given date.- 
- If the table is already booked, then rollback the transaction. If the table is available, then commit the transaction. 

The screenshot below is an example of a rollback (cancelled booking), which was enacted because table number 5 is already booked on the specified date.

![](./week2/11.png)

**SOLUTION**
```mysql
USE LittleLemonDB;
DROP PROCEDURE IF EXISTS AddValidBooking;
DELIMITER //

CREATE PROCEDURE AddValidBooking(IN booking_date DATE, IN table_no INT, IN customer INT)
BEGIN
START TRANSACTION;
SELECT BookingID INTO @id FROM Bookings ORDER BY BookingID DESC LIMIT 1;
SET @id = @id + 1;
IF EXISTS(SELECT 1 FROM Bookings WHERE (BookingDate = booking_date AND TableNumber = table_no))
THEN
SELECT CONCAT("Table " , table_no, " is already booked - booking cancelled.") AS `Booking status`; 
ROLLBACK;
ELSE
INSERT INTO Bookings (BookingID, BookingDate, TableNumber, CustomerID)
VALUES (@id, booking_date, table_no, customer);
COMMIT;
SELECT CONCAT("Booking for table " , table_no, " is successful.") AS `Booking status`; 
END IF;
END //

DELIMITER ;
```

## 2.4 Exercise: Create SQL queries to add and update bookings

Task 1
In this first task you need to create a new procedure called AddBooking to add a new table booking record.

The procedure should include four input parameters in the form of the following bookings parameters:
- booking id,- 
- customer id,- 
- booking date- 
- and table number.

The screenshot below shows an example of the AddBooking statement:

![](./week2/12.png)

**SOLUTION**
```mysql
USE LittleLemonDB;
DROP PROCEDURE IF EXISTS AddBooking;
DELIMITER //

CREATE PROCEDURE AddBooking (IN booking_id INT, IN customer INT, IN table_no INT, IN booking_date DATE)
BEGIN
START TRANSACTION;
IF EXISTS(SELECT 1 FROM Bookings WHERE (BookingID = booking_id))
THEN
SELECT CONCAT("Booking " , booking_id, " already exists - booking cancelled.") AS `Booking status`;
ROLLBACK;
ELSEIF EXISTS(SELECT 1 FROM Bookings WHERE (BookingDate = booking_date AND TableNumber = table_no))
THEN SELECT CONCAT("Table " , table_no, " already booked - booking cancelled.") AS `Booking status`;
ROLLBACK;
ELSE
INSERT INTO Bookings (BookingID, BookingDate, TableNumber, CustomerID)
VALUES (booking_id, booking_date, table_no, customer);
COMMIT;
-- SELECT CONCAT("New booking added.") AS `Confirmation`; 
END IF; 
END //

DELIMITER ;
```

Task 2
For your second task, Little Lemon need you to create a new procedure called UpdateBooking that they can use to update existing bookings in the booking table.
The procedure should have two input parameters in the form of booking id and booking date. You must also include an UPDATE statement inside the procedure. 
The screenshot below shows an example of the UpdateBooking procedure in use.

![](./week2/13.png)

**SOLUTION**
```mysql
USE LittleLemonDB;
DROP PROCEDURE IF EXISTS UpdateBooking;
DELIMITER //

CREATE PROCEDURE UpdateBooking (IN booking_id INT, IN booking_date DATE)
BEGIN
START TRANSACTION;
IF NOT EXISTS(SELECT 1 FROM Bookings WHERE (BookingID = booking_id))
THEN
SELECT CONCAT("Booking " , booking_id, " does not exist.") AS `Message`;
ROLLBACK;
ELSE
UPDATE Bookings SET BookingDate = booking_date WHERE BookingID = booking_id;
COMMIT;
-- SELECT CONCAT("Booking ", booking_id ," updated.") AS `Confirmation`; 
END IF; 
END //

DELIMITER ;
```

Task 3
For the third and final task, Little Lemon need you to create a new procedure called CancelBooking that they can use to cancel or remove a booking.
The procedure should have one input parameter in the form of booking id. You must also write a DELETE statement inside the procedure. 
When the procedure is invoked, the output result should be similar to the following screenshot:

![](./week2/14.png)

**SOLUTION**
```mysql
USE LittleLemonDB;
DROP PROCEDURE IF EXISTS CancelBooking;
DELIMITER //

CREATE PROCEDURE CancelBooking (IN booking_id INT)
BEGIN
START TRANSACTION;
IF NOT EXISTS(SELECT 1 FROM Bookings WHERE (BookingID = booking_id))
THEN
SELECT CONCAT("Booking " , booking_id, " does not exist.") AS `Message`;
ROLLBACK;
ELSE
DELETE FROM Bookings WHERE BookingID = booking_id;
COMMIT;
-- SELECT CONCAT("Booking ", booking_id ," cancelled.") AS `Confirmation`; 
END IF;
END //

DELIMITER ;
```

# WEEK3

## 3.1 Exercise: Set up the Tableau Workspace for data analysis

Task 1
In this first task, you need to connect to Little Lemon data stored in the Excel Sheet called LittleLemonDB. Then filter data in the data source page and select the United States as the country.
Here’s some guidance for completing this task:
- Open Tableau. In the Connection Pane select Excel, then navigate to the data source.
- In the data source page, select Filter Tab.

Task 2
In the second task, you need to create two new data fields called First Name and Last Name. Related values should be extracted from the Full Name field.
Here’s some guidance for completing this task:
- You can use the Split feature in Tableau.
- Rename the new fields.

Task 3
For your third task, you need to create a new data field that stores the profits for each sale, or order as shown in the screenshot below.

Here’s some guidance for completing this task:
- Select Sales field in the Data Pane, then select Create Calculated field.- 
- Name the calculated field Profit- 
- Write a formula that deducts Cost from Sales. 

Once you complete these tasks you should be ready to perform data analytics and to create visual charts. 

![](./week3/1.png)


## 3.2 Exercise: Create interactive dashboard for sales and profits

Task 1
In the first task, you need to create a bar chart that shows customers sales and filter data based on sales with at least $70.

Here’s some guidance for completing this task:
- Drag and drop relevant fields from the data pane into the shelves section- 
- Use a suitable colour scheme- 
- Filter sales based on sales >= $70- 
- Name the chart Customers sales.

If you roll over a bar, the customer names and sale figures should be displayed as shown below.

![](./week3/2.png)

Task 2
In the second task, you need to create a line chart to show the sales trend from 2019 to 2022. 

Here’s some guidance for completing this task:
- Drag and drop relevant fields from the data pane- 
- Use a suitable colour scheme- 
- Filter data to exclude 2023- 
- Name the chart Profit chart.

Your chart should show the trend of sales from 2019 to 2022 only as shown below. 

![](./week3/3.png)

Task 3
In the third task, you need to create a Bubble chart of sales for all customers. The chart should show the names of all customers. Once you roll over a bubble, the chart should show the name, profit and sale.

Here’s some guidance for completing this task:
- Drag and drop relevant fields from the data pane- 
- Use a suitable colour scheme- 
- Name the chart Sales Bubble Chart.

Your chart should show the following Bubble chart.

![](./week3/4.png)

Task 4
In this task, you need to compare the sales of the three different cuisines sold at Little Lemon. Create a Bar chart that shows the sales of the Turkish, Italian and Greek cuisines.

You need to display sales data for 2020, 2021, and 2022 only. Each bar should display the profit of each cuisine. 

Here’s some guidance for completing this task:
- Drag and drop relevant fields from the data pane- 
- Use a suitable color scheme- 
- Name the worksheet Cuisine Sales and Profits- 
- Sort data in descending order by the sum of the sale.

Your chart should be similar to the following example:

![](./week3/5.png)

Task 5
In this final task, you need to create an interactive dashboard that combines the Bar chart called Customers sales and the Sales Bubble Chart. Once you click a bar, and roll over the related bubble, the name, sales and profit figures should be displayed in the Bubble chart as shown below.

![](./week3/6.png)


## 3.3 Exercise: Set up the client project

Task 1
Your first task is to navigate to your terminal and ensure that Python is installed and available on the command path. To complete this task, type the following syntax:
```python
python --version
```

Task 2
Having established that an up-to date version of python is installed on your machine you will need to install Jupyter. You can install Jupyter using the following code:
```python
python -m pip install jupyter
```

Task 3 Verify that a connection can be made with your database by calling the connection method from the connector class: 
```python
!pip install mysql-connector-python
import mysql.connector as connector

connection = connector.connect(user = "alex", password = "pwd@1234", db="LittleLemonDB")
```

## 3.4 Exercise: Add query functions

Task One
In the previous exercise you created a Python environment. In the first task of this exercise, you are tasked with extending the environment to connect with your database and interact with the data it holds. 

Your first step is to import the connector module, enter your user details and connect with the database (Hint: you can use an alias when importing the module).

This gives you access to all the functionality available from the connector API, which can be accessed through the variable named connector (or whichever alias you choose). 

To connect with your database, you can call the connect method of the connector class and pass in your details using the following code: 
```python
connection = connector.connect(user = "your_username", password = "your_password", db = "database_name") 
```
This code should look very familiar to you from the previous course, apart from the parameter db. DB stands for database. When instantiating the connection, you can pass the database name here in place of calling the USE command later. 

The final step is to instantiate an instance of cursor to pass queries and return results (Hint: the cursor is part of the connection class outlined above).

**SOLUTION**
```python
connection = connector.connect(user = "alex", password = "pwd@1234", db="LittleLemonDB")
cursor = connection.cursor()
```

Task two
In this second task, you now need to query the database to show all tables within the database. 
Having established a connection in the first task, you need to execute a test query to ensure that there are no issues. You can do this by executing, or passing, a generic query that returns a snapshot of the database tables. 
You need to execute the query on the cursor using the code that follows. The cursor, as you should recall, is the bridge through which you can pass queries and return results.
```python
show_tables_query = "SHOW tables" 
cursor.execute(show_tables_query)
```
As before, a variable is used to hold the query. To gain a general insight, the query asks to display all tables within the database. 
The second line calls the cursor execute method. This method takes the Python string and ports it into a viable SQL statement. It then passes it to the database and returns the result. 
To view the results of your query, you can create another variable called results (Hint: the cursor has a method that can return all results in one call). 
To view the tables that are associated with a database, you can print out the results variable using the following code: 
```python
print(results)
```

**SOLUTION**
```python
show_tables_query = "SHOW TABLES" 
cursor.execute(show_tables_query)
results = cursor.fetchall()

# Printing tables in database
for row in results:
    print(row)
```

Task 3
Query with table JOIN
For the third and final task, Little Lemon need you to return specific details from your database. They require the full name and contact details for every customer that has placed an order greater than $60 for a promotional campaign. 
You can use the following steps to implement this functionality in your database directory:

Step One: Identify which tables are required. To complete the query, you first need to identify which table has the required data. 
The bill paid can be found in Orders as TotalCost and the customer contact information can be found in the Customers table. 
When selecting attributes from a specific table, specify the table name, followed by a dot and the target attribute as below (Hint: select the column attributes that you will need). 

Step Two: Next, specify a table (Hint: The FROM keyword allows you to identify a table.)
To join two tables, specify the type of JOIN and the attribute to join the table on. The tables must be joined on an attribute that is common to both tables (such as a common column).

Step Three: Finally, include a clause to filter the data on. (Hint: the WHERE clause can be used to add conditional parameters.) 
When you have completed these steps, wrap this query as a string and pass it to the .execute() method of the cursor class. When executed, your SELECT query must extract the full name, contact details and bill amount for every customer who spent more than $60.

**SOLUTION**
```python
query_stmt = """
SELECT Customers.FullName, Customers.ContactNumber, Orders.TotalCost AS `BillAmount`
FROM Customers
JOIN Orders
ON Customers.CustomerID = Orders.CustomerID
WHERE Orders.TotalCost > 60;
"""
cursor.execute(query_stmt)
results = cursor.fetchall()

# Printing results
print(cursor.column_names)
for row in results:
    print(row)

cursor.close()
connection.close()
```
