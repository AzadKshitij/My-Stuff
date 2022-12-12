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








