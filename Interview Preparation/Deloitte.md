## ToDos:
- [x] About the company. ✅ 2022-12-01
- [ ] About My Self and How I can fit in the company.
- [ ] # Cosmic Byte CB-GK-26 Pandora TKL

## About the Company

“Deloitte” is the brand under which tens of thousands of dedicated professionals in independent firms throughout the world collaborate to provide audit & assurance, consulting, risk and financial advisory, risk management, tax, and related services to select clients. These firms are members of Deloitte Touche Tohmatsu Limited, a UK private company limited by guarantee (“DTTL”). Each DTTL member firm provides services in particular geographic areas and is subject to the laws and professional regulations of the particular country or countries in which it operates.


## SQL 
-   `id` - this is going to be the primary key of the table and would be the unique identifier of each user.

### Data types

The most common data types that you would come across are:

-   `CHAR`(size): Fixed-length character string with a maximum length of 255 bytes.
-   `VARCHAR`(size): Variable-length character string. Max size is specified in parenthesis.
-   `TEXT`(size): A string with a maximum length of 65,535 bytes.
-   `INTEGER`(size) or `INT`(size): A medium integer.
-   `BOOLEAN` or `BOOL`: Holds a true or false value.
-   `DATE`: Holds a date.

### Operations

#### 1. Create Database
- `CREATE DATABASE demo`
- db name should be unique.

#### 2. Create Table
```sql
CREATE TABLE users
(
    id INT,
    username VARCHAR(255),
    about TEXT,
    birthday DATE,
    active BOOL
);
```

#### 3. Dropping tables

You can drop or delete tables by using the `DROP TABLE` statement.
Let's test that and drop the table that we've just created:  
```sql
DROP TABLE users;
```

#### 4. Allowing NULL values

By default, each column in your table can hold NULL values. In case that you don't wanted to allow NULL values for some of the columns in a specific table, you need to specify this during the table creation or later on change the table to allow that.

For example, let's say that we want the `username` column to be a required one, we would need to alter the table create statement and include `NOT NULL` right next to the `username` column like this:  

```sql
CREATE TABLE users
(
    id INT,
    username VARCHAR(255) NOT NULL,
    about TEXT,
    birthday DATE,
    active BOOL
);
```

#### 5. Specifying a primary key

The primary key column, which in our case is the `id` column, is a unique identifier for our users.

We want the `id` column to be unique, and also, whenever we add new users, we want the ID of the user to autoincrement for each new user.

This can be achieved with a primary key and `AUTO_INCREMENT`. The primary key column needs to be `NOT NULL` as well.

If we were to alter the table creation statement, it would look like this:  

```sql
CREATE TABLE users
(
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(255) NOT NULL,
    about TEXT,
    birthday DATE,
    active BOOL
);
```

#### 6. Updating tables

In the above example, we created a new table and then dropped it as it was empty. However, in a real-life scenario, this would really be the case.

So whenever you need to add or remove a new column from a specific table, you would need to use the `ALTER TABLE` statement.

Let's say that we wanted to add an `email` column with type varchar to our `users` table.

The syntax would be:  

```sql
ALTER TABLE users ADD email VARCHAR(255);
```

If you wanted to drop a specific column, the syntax would be:  

```sql
ALTER TABLE table_name DROP COLUMN column_name;
```

#### 7. INSERT

To add data to your database, you would use the `INSERT` statement.
Let's use the table that we created in the last chapter and insert 1 user into our `users` table:  

```sql
-- INSERT INTO table(fields) VALUES(values_for_field)
INSERT INTO users(username, email, active) VALUES('bobby', 'bobby@bobbyiliev.com', true);
```

Rundown of the insert statement:
-   `INSERT INTO users`: first, we specify the `INSERT INTO` keyword, which tells MySQL that we want to insert data into the `users` table.
-   `users (username, email, active)`: then, we specify the table name `users` and the columns that we want to insert data into.
-   `VALUES`: then, we specify the values that we want to insert in.

#### 8. UPDATE

In order to modify data in your database, you could use the `UPDATE` statement.

The syntax would look like this:  

```
UPDATE users SET username='bobbyiliev' WHERE id=1;
```

#### 9. DELETE

As the name suggests, the `DELETE` statement would remove data from your database.

The syntax is as follows:  

```
DELETE FROM users WHERE id=1;
```

Similar to the `UPDATE` statement, if you don't specify a `WHERE` clause, all of the entries from the table will be affected, meaning that all of your users will be deleted.

#### 1. What is the difference b/w DROP and TRUNCATE statements?
the DROP command is used to remove the whole database or table indexes, data, and more. Whereas the TRUNCATE command is used to remove all the rows from the table.

#### 2. What is an Alias in SQL?
SQL aliases are used to give a table, or a column in a table, a temporary name. Aliases are often used to make column names more readable. An alias only exists for the duration of that query. An alias is created with the `AS` keyword.

#### 3. How to display even no. of row in an employee table
SQL Server: `where column_name % 2 = 0;`
Postgres, MySQL, Oracle: `WHERE mod(column_name,2) = 0`

#### 4. Display last 50% of records from the employee table.
```sql
SELECT * FROM
(SELECT top 50 percent * FROM Employee ORDER BY ID DESC)
ORDER BY ID;
```

#### 5. Select all records from employee table whose name is "Himanshu" and "Rahul"


## HR Questions

Deloitte's history, such as when the company was founded, its aims, beliefs, and organizational structure, among other topics.

### History
- The firm was founded by [William Welch Deloitte](https://en.wikipedia.org/wiki/William_Welch_Deloitte "William Welch Deloitte") in London in 1845
- Always One Step Ahead" (AOSA)
- Audit provides the organization's traditional accounting and audit services, as well as internal auditing,
#### Questions
-   Tell me about yourself. (You can focus a little bit on your family history, your educational qualifications, and then go on to your professional development. When talking about yourself, attempt to include details that will convince the interviewer that you are qualified for the position.)
-   Are you willing to relocate to various parts of India?
-   What are your expectations from this role?
-   Where do you see yourself in 5 years?
-   Tell me about your projects and internships.
-   What made you want to find a new job? (This is a frequently asked question among experienced professionals seeking a job change. Saying you're quitting your current job to pursue a promotion is the simplest approach to react to this question. Make sure you're not criticizing or undermining your current employer.)

1. Why Deloitte?
	- 
2. Why analyst?
	- What is analyst?
	- Why I fit into the role?
3. Tell me bout you self.
	1. What are you doing now?
	2. What you did before?
	3. What next you want to do?
4. Tell us the time you worked in a team?
5. Why you want to work in the sector?
6. Challenge and how you overcome it.
7. How do you handle pressure.
	1. Time management, Being organized.
	2. Willing to go extra mile to get work done.
	3. doing work under pressure with hard deadline(IITJ Voting)
	4. I'm not afraid to help people. 









