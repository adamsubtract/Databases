### 1. What data types do each of these values represent?

"A Clockwork Orange" = String
42 = integer
09/02/1945 = integer
98.7 = float
$15.99 = float

### 2. Explain when a database would be used. Explain when a text file would be used.

databases should be used when data needs to be stored after the program is running,
need to search for specific data, or manipulate data.

### 3. Describe one difference between SQL and other programming languages.

SQL is a declarative language and not a procedural language.

### 4. In your own words, explain how the pieces of a database system fit together at a high level.



### 5. Explain the meaning of table, row, column, and value.

A table would be what the data you are storing or your looking at, the row would be the
what is stored at a certain id or all data in that row. The column is what is being
stored there, for example all the names would be put in a column then the emails
would be put in another, this helps keep things organized. The value is whats
being stored at a certain row-column number.

### 6. List three data types that can be used in a table.

INT, string, float.

### 7.Given this payments table, provide an English description of the following queries and include their results:
```
SELECT date, amount
     FROM payments;

     SELECT amount
     FROM payments
     WHERE amount > 500;

     SELECT *
     FROM payments
     WHERE payee = 'Mega Foods';
```

 - select the date and amount from payments

 - select the amount from payments where the amount is more than 500

 - select everything from payments where payee has a value (string in this case) of Mega Foods.

 So we are selecting date and amount payments that are more than 500, then we are selecting

 all data that has a payee value of Mega foods.


### 8. Given this users table, write SQL queries using the following criteria and include the output:

- The email and sign-up date for the user named DeAndre Data.

    SELECT email, date
    FROM   users
    WHERE  username = 'DeAndre Data'


- The user ID for the user with email 'aleesia.algorithm@uw.edu'.

    SELECT user ID
    FROM   users
    WHERE  email = 'aleesia.algorithm@uw.edu'


- All the columns for the user ID equal to 4.

    SELECT *
    FROM users
    WHERE user ID = 4
