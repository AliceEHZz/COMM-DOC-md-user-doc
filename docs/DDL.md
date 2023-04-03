# Data Definition Language (DDL)

In this section, we will cover the DDL commands, which are used to create, alter, and drop databases, tables, indexes and constraints. We will go over the following SQL DDL commands and create a new database and a new table:

- CREATE
- ALTER
- DROP

By the end of this section, you will have a good understanding of how to use these commands to manage your database structure effectively. Let's open MySQL Workbench and get started!

## CREATE Command

The CREATE command is used to create new objects in sql such as tables, indexes, and constraints. Instead of creating a database by clicking on "New Schema" using mouse, this time we will use CREATE command in query script.

Follow the steps below and let's

1. Go to the "File" Menu on the left corner of your Workbench and then click on "New Query Tab".

   **insert image**

   This will give us a query text window where we can type our SQL commands and run them using the Execute button: . If a specific command is selected, then only that command is executed. If no commands are selected, all the commands in the query window are run.

   - If you just want to run a single command you can use the Cursor Execute button (insert icon). This button will only run the single command where the keyboard cursor is. The keyboard shortcut for this is CTRL + Enter on Windows or CMD+Enter (⌘+Enter) on Mac.

2. Type **CREATE DATABASE intro_to_sql;** in the query

```sql
CREATE DATABASE intro_to_sql;
```

3. Click Execute icon.

   **insert image**

   After you execute you should see this message on the bottom:

4. Click the refresh icon to confirm the new database is added to your database list.
   **insert image**

5. set the new database as default blablabla

Now we have a new database created. In the following example, we will create a table named "customers" with four columns: "id", "name", "email", and "age".

1. Copy and paste the commands below to your query.

```sql

```

**insert little reference inside code!**

The "id" column is the primary key, and the "name" column is required (NOT NULL).

1. Click Execute icon.

In this example, we are creating a table named "customers" with four columns: "id", "name", "email", and "age". The "id" column is the primary key, and the "name" column is required (NOT NULL).

## ALTER Command

The ALTER command is used to modify the structure of existing database objects such as tables, indexes, and constraints. Here's an example of altering a table using the ALTER command:

```sql
ALTER TABLE customers ADD address VARCHAR(50);
```

## DROP Command

The DROP command is used to remove existing database objects such as databases, tables, indexes, and constraints. Here's an example of dropping a database using the DROP command:

```sql
DROP TABLE customers;
```

In this example, we are dropping the "customers" table.

!!! warning

Using the DROP DATABASE command will delete a database, all of it's tables, and all the data inside all of those tables. It is also important to be careful when using the DROP command as it permanently deletes the specified database object.

## Conclusion

We hope this section has been helpful with your learning journey on the CREATE, ALTER, and DROP commands. You can easily create, modify, and delete database objects using these commands to fit your needs.

In the next section, we will cover SQL DML commands, which are used to manipulate data in the database. With these commands, you can retrieve, insert, update, and delete data from your database.

Let's continue learning!
