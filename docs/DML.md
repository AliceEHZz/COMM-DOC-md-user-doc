# Data Manipulation Language (DML)

In this section, we will cover some basic DML commands, which sre used to insert, update, and delete rows from the tables. We will go iver the following DML commands and manipulate the data in the table:

- ```INSERT```

- ```UPDATE```

- ```DELETE```

By the end of this section, you will have a good understanding of how to use these commands to manage your table effectively. Let's continue practicing in  MySQL Workbench!

## SQL INSERT

The ```INSERT``` statement is used to add new rows of data to a table. You can add commands in your current SQL file.

Copy the code chunk below to your SQL file and execute:

``` sql
INSERT INTO employees
(EMP_FNAME, EMP_LNAME, EMP_SALARY, EMP_BONUS)
VALUES
('John', 'Smith', 50000, 1000),
('Jane', 'Doe', 60000, 3000),
('Bob', 'Johnson', 70000, 500);
```

After you execute you should see this message in your Action Output:

**3 row(s) returned**

This statement updates the salary of all employees with the last name "Doe" to 60000 in the employees table. You should be able to see the changes in the table.

![Image title](./images/insert.png)

## SQL UPDATE

The ```UPDATE``` statement is used to modify existing rows of data in a table.

Copy the code chunk below to your SQL file and execute:

``` sql
UPDATE employees
SET EMP_SALARY = 65000
WHERE EMP_LNAME = 'Doe';
```

After you execute you should see this message in your Action Output:

**3 row(s) returned**

This statement updates the salary of all employees with the last name "Doe" to **65000** in the employees table.

!!! Tips (move to troubleshooting)

    If you get an error message below, you can either manually disable the safe mode or add a line of code above the update code chunk.

    ``` sql
    SET SQL_SAFE_UPDATES = 0;
    ```

    This line code will also disable the safe mode for you. Then, you can try to execute the code chunk again.

    11:13:12 UPDATE employees SET EMP_SALARY = 65000 WHERE EMP_LNAME = 'Doe' Error Code: 1175. You are using safe update mode and you tried to update a table without a WHERE that uses a KEY column.  To disable safe mode, toggle the option in Preferences -> SQL Editor and reconnect. 0.015 sec

!!! warning needed

    Be careful with the WHERE clause: The WHERE clause determines which records in the table will be updated. If you forget to include a WHERE clause, the update will be applied to all records in the table, which could lead to unintended consequences. Make sure you double-check your WHERE clause to ensure that it is targeting only the records you want to update.

![Image title](./images/update.png)

## SQL DELETE

The ```DELETE``` statement is used to remove rows of data from a table.

Copy the code chunk below to your SQL file and execute:

``` sql
DELETE FROM employees
WHERE EMP_LNAME = 'Doe';
```

After you execute you should see this message in your Action Output:

**1 row(s) affected**

This statement deletes all rows from the employees table where the last name is "Doe".

!!! warning needed

    Be careful with the WHERE clause: The WHERE clause determines which records in the table will be deleted. If you forget to include a WHERE clause, the delete operation will remove all records in the table, which could lead to unintended consequences. Make sure you double-check your WHERE clause to ensure that it is targeting only the records you want to delete.

![Image title](./images/delete.png)

## Conclusion

We hope this section has been helpful with your learning journey on the ```INSERT```, ```UPDATE```, and ```DELETE``` commands. You can easily insert, update, and delete table objects using these commands to fit your needs.

In the next section, we will cover SQL DQL commands, which are used to retrieve data in the database. With these commands, you can select wanted data from your database.

Let's continue learning!
