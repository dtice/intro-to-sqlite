# A Beginner's Guide to the Shell and Basic SQLite3 Syntax

# Starting with the Shell

This section is going to cover a few very basic commands in the terminal and is designed for a user that is not familiar with the terminal. If you are familiar with basic shell commands you should skip down to the download section.   

## Windows 

**Getting started:** Under your computers search directory bar search for “command prompt.” 

  

#### Commands 

	 dir - prints contents of current directory 
	 cd - change directory to file specified 
	 rm- remove directory 
	 md - make directory 
	 ren - rename a file 
	 
	 
	 
## Mac OS X

**Getting started:** Under your computers search directory bar search for “terminal.” 

  

Once in the command prompt you will start at your home directory file system.  this file system you will have a bunch of different options for commands to enter to change directories and manipulate the file system on your computer.

  

#### Commands

	 ls - Prints the files in your current directory 
	 cd - change your directory to file specified  
	 pwd - prints directory to current file  
	 Mkdir - makes a new directory 
	 Rmdir - removes an empty directory 
	 Control + c - quits almost any applications 
	 Up and down arrows - cycle through old commands 
  

**TIP:** It is faster to change to specified directories if you drag and drop files straight into terminal. This can be done on all systems.
  
  
  

## Linux 

**Getting started:** Under your computers search directory bar search for “terminal.” 

  

#### Commands

	 pwd - print current file path 
	 ls - print files in current directory  
	 cd - change current directory 
	 mkdir - create new directory 
	 rmdir- remove directory 
	 rm - remove a file 
	 touch - create a file 
	 cp - copy file 
	 help - display commands in terminal 
	 mv - move files 
   

### TEXT EDITORS

The terminal on all system come already equipped with some basic text editors that can be used to write code to execute in the terminal. We will be referencing Nano and Vim throughout this tutorial, but feel free to use your favorite text editor.

  

##### Nano

Nano is a very basic text editor and is perfect for users who are just getting started with the terminal. Nano offers usability but sacrfrices customizability and can be very cumbersome to an experienced programmer. To start up Nano type “nano” followed by the filename you want to edit.

  
  

#### Vim

Vim is not as basic as nano and requires a sort of language to edit things. Vim will take a lot of practice to get used to but with experience vim is easier to naviagte and customize due to the fact it has a ton of shortcuts built in. To start up vim simply type “vim” into the command line.
//


# Installing SQLite3
The first step to installing SQLite3 is determining what operating system your computer is running as the steps for each differ. The three operating systems that we will be covering are Windows, Mac OSX, and Linux respectively. Navigate to the section that 

## Windows
### Download
* First navigate to the SQLite3 download page located at: https://www.sqlite.org/download.html 
* Then scroll down to find the section titled “Precompiled Binaries for Windows” and download it 

### Install
* First create a new folder named “sqlite” where you would like to install SQLite3
* Then extract the contents of the downloaded file to your new directory
* You should now see sqlite3.exe in the new folder
### Installation Verification
We now need to verify that SQLite3 is properly installed on our device<br /> 
First open the command prompt as shown in section one<br /> 
Then navigate to the directory where you installed SQLite3<br /> 
Next type 
     
	 
	sqlite3
	 
	 
You should receive this output


	SQLite version 3.7.15.2 2013-01-09 11:53:05
	Enter ".help" for instructions
	Enter SQL statements terminated with a ";"
	sqlite> 
	 
	 
	 
You have now successfully installed SQLite3 


## Mac OS X
Today almost every version of OSX is shipped with SQLite3 already installed. So chances are your computer is already running SQLite. <br /> 
To verify 

### Verify
First navigate to the shell as shown in part one of the tutorial
Use this command to check if you have SQLite3 installed<br /> 
   	 
	 
	sqlite3
	 
	 
Output


	SQLite version 3.7.15.2 2013-01-09 11:53:05
	Enter ".help" for instructions
	Enter SQL statements terminated with a ";"
	sqlite> 
	 
	 
	 
    

If you don't see this output then you do not have SQLite3 installed. Follow the below instructions to install SQLite3 to your computer
### Download
* First navigate to the SQLite3 download page located at: https://www.sqlite.org/download.html
* Then find the section labeled autoconf-*.tar.gz and download it 



### Install

Open the shell<br /> 
Navigate to the directory where you downloaded the file in the previous step<br /> 
Then run this command to install SQLite3
    
	
	$tar xvfz sqlite-autoconf-3071502.tar.gz
	$cd sqlite-autoconf-3071502
	$./configure --prefix = /usr/local
	$make
	$make install
	 
	 
You can then verify that you have properly installed SQLite3 using the above method


## Linux
Today almost every version of Linux is shipped with SQLite3 already installed. Chances are your computer is already running SQLite. 

### Download
First navigate to the SQLite3 download page located at: https://www.sqlite.org/download.html<br /> 
Then find the section labeled autoconf-*.tar.gz and download it 



### Install
Open the shell<br /> 
Navigate to the directory where you downloaded the file in the previous step<br /> 
Then run this command to install SQLite3
    
	
	$tar xvfz sqlite-autoconf-3071502.tar.gz
	$cd sqlite-autoconf-3071502
	$./configure --prefix = /usr/local
	$make
	$make install
	
	
You can then verify that you have properly installed SQLite3 using the above method


# Your First SQL File

Although you can interact with the SQLite3 interpreter from the command line and return the results of queries, one may often find themselves wanting some form of automation. Just like in any other programming language, you can write your queries, line-by-line, in a file with the “.sql” extension and the interpreter will execute them iteratively. 

The first step in any SQL file is to identify the database that you will be manipulating, or create a new one. To save some time, you can simple create a new empty file called “sample_database.sql”, then copy and paste the commands, in order, from this website. This newly created .sql file will generate a sample database with `CUSTOMERS`, `ORDERS`, and `AGENTS` tables and some dummy entries in each.

The next step is to create your first custom SQL file in which you will query and change the database that we have just created. Create a new file in the same folder as “sample_database.sql” and name it “my_first_query.sql”. At the top of this new file, add the line “.read sample_database.sql”. This will import the sample database into your file.


## Your First Queries

Finally, we can get to some real queries! At this point, if you run your file, you may notice that it acts the same way as if you simply ran “.read sample_database.sql” from the command line interpreter. Let’s make it a little more interesting. Add the following lines to your file after the “.read” statement:
```sql
INSERT INTO `CUSTOMERS`
	(`CUST_CODE`,`CUST_NAME`,`CUST_CITY`,`WORKING_AREA`,
	`CUST_COUNTRY`,`GRADE`,`OPENING_AMT`,`RECEIVE_AMT`,
	`PAYMENT_AMT`,`OUTSTANDING_AMT`,`PHONE_NO`,
	`AGENT_CODE`) 
VALUES 
	(‘C00110’,’Charles’,’Spokane’,’Spokane’,’USA’,2,8000.00,2000.00,
	1000.00,0000.00,5099985247,’A003’);
	
SELECT * FROM `CUSTOMERS` WHERE `CUST_CODE`=’C00110’;

UPDATE `CUSTOMERS` 
	SET `CUST_NAME`=”CHARLIE” 
	WHERE `CUST_NAME`=”CHARLES”;
    
DELETE FROM `CUSTOMERS` WHERE `CUST_NAME`=”CHARLIE”;
```
Whew! If you didn’t copy and paste, that was probably a lot of typing. So what does all this mean? Well, when it comes to database software, there are 4 basic functions, easy to remember with a mnemonic device: CRUD. This stands for Create, Read, Update, Destroy. As you might see in the example, the first statement is the `INSERT` statement which CREATED a row in the table. The second statement is the `SELECT` statement which returns or READS a row or multiple rows from the table. The third statement is the `UPDATE` statement, which changed existing data in the table based on conditions defined by the writer of the statement. The last statement is the `DELETE` statement which removes a row or rows from the table based on a condition, similar to the update command.


## WHERE
 
On every query statement, you can specify conditions on which you want data read, updated, or destroyed. That’s where the `WHERE` clause comes in. You can think of the `WHERE` clause as narrowing down the search of data that you are trying to do. For example, a select statement such as this:
```sql
SELECT `CUST_NAME` 
	FROM `CUSTOMERS` 
	WHERE `CUST_CITY`='New York';
```
Could be read in the following manner:

```
Give me the names 
	Of all customers 
	WHERE the city they live in is New York.
```
The `WHERE` clause is very important for specifying the data that you’d like to work with. It is essentially narrowing down the search for the data that you are looking for. You can combine these clauses using the `AND` keyword in the following manner:
```sql
	SELECT `CUST_NAME`
		FROM `CUSTOMERS`
		WHERE `CUST_CITY`='New York'
			AND `CUST_NAME`='Albert';
```
You can tag on as many of these `AND` statements as you want in order to narrow down your search.


## JOIN

Due to the nature of relational databases, one can not simply `SELECT` data in another table while looking at data in another table. This is where the different `JOIN` keywords comes into play. Let’s say that you had one table with `CUSTOMER` information and another with `ORDERS` information:
```sql
	SELECT * FROM `CUSTOMER` AS `C`
		INNER JOIN `ORDERS` AS `O`
			ON `C`.`CUST_CODE`=`O`.`CUST_CODE`;
```
Since every customer has a `CUST_CODE` and every `ORDER` has a `CUST_CODE`, we can perform an `INNER JOIN` with the `ORDERS` table `ON  ORDERS.CUST_CODE=CUSTOMER.CUST_CODE`. This will essentially tack on information about the customer’s order to the end of each `CUSTOMER` entry. If there is more than one order for a customer, it will create a duplicate `CUSTOMER` entry in the `JOIN` table with different `ORDER` information tacked on. You can think of the `AS` keyword as assigning an alias for the table. Every reference to the `CUSTOMER` table when using the `AS` keyword should be written as `C` instead of `CUSTOMER`. There are multiple types of JOINs; you can think of joins as a Venn diagram between 2 tables:<br>

![alt text](https://www.w3schools.com/sql/img_innerjoin.gif "Inner Join") ![alt text](https://www.w3schools.com/sql/img_leftjoin.gif "Left Join") ![alt text](https://www.w3schools.com/sql/img_fulljoin.gif "Outer Join")

An inner join would be selecting the entries that share a common column between the two tables that you joined. 


## GROUP AND ORDER
Grouping in SQL is fairly self explanatory. It takes a database the user has created and orders that given database using columns in a specific way. For example: If you have a database about customers for a store, and you have information on each user such as: what country they are from or how old they are. Then you could use the “GROUP BY” command to group the customers by any column you would like. 
```sql
SELECT `CustomerID`, `Country`
	FROM `Customers`
	GROUP BY `Country`;
```
This short query allows the user to select the Country column from the Customer database and then groups the customers by the country they are from. 

Along with grouping, ordering goes right along with it. Once you have a column in a database that you would like to organize in a certain way, then you can proceed to using the ORDER function of SQL. With the ORDER command you are able to grab a column, the Country column, and order it in almost any way needed. When ordering you can use a Max command that returns the maximum value of the column. Similar to Max, the MIN just returns the minimum value of the column.
```sql
SELECT `CustomerID`, `Country`
	FROM `Customers`
	GROUP BY `Country`;
	ORDER BY COUNT(`CustomerID`) DESC;
```
This takes the list of columns that we grouped earlier then orders it from high to low.
The count function simply returns in the total number of rows in a table. The only way it can count is when the location WHERE is specified. If a column has no rows that match the count will simple return 0.
  

After completing this tutorial, if you'd like to know more please visit [this](https://www.sqlite.org/lang.html) link to view the official SQlite documentation.



