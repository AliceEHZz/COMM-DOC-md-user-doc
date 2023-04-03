# Querying the Database with SELECT (focus only on SELECT and FROM Wk 5 lab part 2, page 1-16)

The goal of this document is to serve as an introduction to querying a database using the SELECT statement. The SELECT statement has a number of parts and can perform many different tasks for retrieving data from the database.

A SELECT statement has the following parts or clauses:

- SELECT
- FROM
- WHERE
- GROUP BY
- HAVING
- ORDER BY

Each clause in the SELECT statement (aside from SELECT itself) is optional. The individual optional clauses can be combined or omitted as needed.

Although the SELECT statement can retrieve data from multiple tables at once, in this section we will focus on retrieving different types of data from a single table using only SELECT and FROM.

By completing this section, you will know how to properly use the SELECT statement only comes from practice and with experience in a wide variety of scenarios.

## SELECT all data

SELECT and show all rows and all columns from a single table is one of the simplest SELECT statements implementing only 1 of the optional clauses - the FROM clause.

Right after the SELECT keyword we use an asterisk **'\*'** to indicate all of the columns.

The syntax for this scenario is shown below:

```sql
SELECT * FROM <table>;
```

Let's see all the rows and columns for the customer table.
Copy and execute

```sql
SELECT * FROM CUSTOMER;
```

You should get back all 10 customer rows and all 7 columns (CUS_CODE, CUS_LNAME, CUS_FNAME, CUS_INITIAL, CUS_AREACODE, CUS_PHONE, CUS_BALANCE).

**insert image**

!!! info
Remember that, although UPPERCASE and lowercase are both permitted, by convention we use UPPERCASE for SELECT keyword clauses like SELECT and FROM. This helps us with readability.

## SELECT specific columns

```sql
SELECT {column1,column2…}
FROM <table>;
```

Let's try this using customer table. We want to get back the customers name (last, first, and middle initial) and their customer balance.

Copy and execute the following command:

```sql
SELECT CUS_FNAME, CUS_INITIAL, CUS_LNAME, CUS_BALANCE
FROM CUSTOMER;
```

You should get back all 10 customer rows but only 4 columns (US_FNAME, CUS_INITIAL, CUS_LNAME, CUS_BALANCE).

**insert image**

## SELECT computed columns

Similarly to Scenario 2, we can retrieve all the rows from a table and some of the columns, but those columns could include a calculation to compute a derived value.
Remember derived values are derived from other columns and/or functions.

For good database design, we split people's names into first name, last name and middle name. But what is we want to recombine those into a single name? We could add the text for first name together with the text from last name (also known as concatenating 2 strings together).

Copy and execute the following command:

```sql
SELECT CONCAT(CUS_FNAME, ' ', CUS_LNAME) FROM CUSTOMER;
```

**insert image**

In the resultset, MySQL doesn't know what to call the column and so it names it based on the function we used. We can easily fix this, by giving the column an alias. An alias is just a nickname for the column so it looks better in the resultset.

Copy and execute

```sql
SELECT CONCAT(CUS_FNAME, ' ', CUS_LNAME) AS "Full Name" FROM CUSTOMER;
```

**insert image**

By adding the AS "Full Name" after the calculation of the derived value, we'll see our alias instead of "No column name". You should put double quotes around your alias, if your alias includes spaces.

Copy and execute

```sql
SELECT INV_NUMBER, LINE_NUMBER, P_CODE, LINE_UNITS, LINE_PRICE, LINE_UNITS * LINE_PRICE AS Subtotal
FROM LINE;
```

**image**

This gives us the subtotal for each line in the Line table by calculating the price (LINE_PRICE) multiplied by the quantity (LINE_UNITS).