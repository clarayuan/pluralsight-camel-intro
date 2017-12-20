# Order Fulfillment Processor

## Installation Overview

This is the installation guide for setting up the order fulfillment processor application that acts as the case study for 
Pluralsight's Introduction to Integration with Apache Camel. The case study is a custom implementation of a mediator. You 
will be able to follow along with the course using this case study project as the base for demonstrations. The case study 
was developed using the following:

..* Implemented on Windows 8.1, 64-bit
..* IntelliJ 2016.2.5
..* JDK 1.7.0_45
..* Maven 3
..* Spring 4
..* PostgreSQL 9.3
..* Apache Tomcat 7.0.54
..* Apache ActiveMQ 5.10.0
..* Apache Camel 2.13.2
..* Hawt.io 1.4.14

## Component Installation

Below are the instructions on a per-component basis. The installation assumes Windows, so you will need to follow the instructions 
that pertain to your OS if you are not using Windows.

### Java

The case study depends on Java. The course makes use of Java SDK 1.7.0_45. The SDK can be downloaded here:

   http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html

Following installation, you will need to configure your environment variables based on your OS

### IntelliJ

My preference for an integrated development environment is IntelliJ. You can 
find the download for IntelliJ here:

   https://www.jetbrains.com/idea/download/#section=windows

### Maven

I use Apache Maven for build and dependency management. You can download Maven here:

   http://maven.apache.org/download.cgi

After installation, you will need to configure your environment variables based on your OS. You can also skip installation of 
Maven and use the Eclipse Maven plug-in if you are developing with Eclipse as your IDE.

### PostgreSQL

I chose to use PostgreSQL for the project's database. PostgreSQL is a free, open-source database. PostgreSQL can be 
downloaded from the following URL:

   http://www.postgresql.org/download/windows/

The installation should include PGAdmin III, which is a graphical editor for PostgreSQL.

The scripts to create the database for the case study project can be found in the project directory:

   order-fulfillment-processor\src\main\sql\postgresql\ddl

Scripts include:

..* create-orders-db.sql = Creates the login, database and schema for the project.
..* create-orders.sql = Drops and re-creates the database table schema
..* drop-orders-db.sql = Drops the orders database

The script to load initial data can be found in the project directory:

   order-fulfillment-processor\src\main\sql\postgresql\dml\load-orders.sql
	
To initially create the database:

1. Log in to PGAdmin III and connect using the postgres user (password is 123)
2. Create the login for orders using the create statement found in create-orders-db.sql
3. Create the database for orders using the create statement found in create-orders-db.sql
4. Disconnect from the server, then right click the database, select properties and enter the user name as orders.
5. Connect to the server using the orders user name. 
6. Open the query tool and run the create-orders.sql file, then run the load-orders.sql file.

To re-load the database:

1. Log in to PGAdmin III and connect using the orders user
2. Open the query tool and run the create-orders.sql file, then run the load-orders.sql file.
	
### Apache Tomcat

I used Apache Tomcat 7.0.54 as a server runtime in Eclipse. Below are instructions for adding the runtime in Eclipse:

1. Download Tomcat 7 from http://tomcat.apache.org/
2. Unzip the file to a directory on your hard drive
3. In Eclipse, click the Window -> Preference menu and then select Server -> Runtime Environments from the Preferences popup
4. Click the Add button.
5. Select Tomcat 7 and click next
6. Enter the installation directory you unzipped Tomcat to and click Finish

### Apache ActiveMQ

I used Apache ActiveMQ 5.10.0 for messaging. Below are instructions for installation:

1. Download ActiveMQ 5.10 from http://activemq.apache.org/
2. Unzip the file to a directory on your hard drivev
3. Open a command prompt and navigate to the bin directory of the activemq installation you unzipped
4. Run the command activemq.bat start
5. Verify the broker started by navigating to http://localhost:8161/ and logging in with admin/admin

### Hawt.io

I used Hawt.io version 1.4.14. Below are instructions for installation:

1. Downloaded Hawt.io 1.4.14 WAR file from http://hawt.io/
2. In Eclipse, I selected the File -> import menu, then selected Web -> WAR
3. I selected the hawt.io WAR file I downloaded and then selected next
4. I kept all the selections unchecked and clicked finish to import the WAR.
5. I added the project to Tomcat in Eclipse
6. You can then verify the installation from http://localhost:8080/hawtio-default-1.4.14

### Order Fulfillment Project Installation

Below are instructions for getting the Order Fulfillment Processor running in IntelliJ Tomcat:

1. Once the server is started, open a browser to http://localhost:8080/ofp/orderHome

If you want to run order processing, click Orders -> Process Orders

If you want to reset the orders back to new status, click Orders -> Reset Orders

## Contact Information

If you have any questions, please feel free to contact me:

Michael Hoffman
mike@michaelhoffmaninc.com
@mhi_inc