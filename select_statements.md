### Write out a generic SELECT statement.
SELECT first
FROM employees
WHERE last LIKE 'A%'

### Create a fun way to remember the order of operations in a SELECT statement, such as a mnemonic.

Samurai's Fight Women Lowkey

### Given this dogs table, write queries to select the following pieces of data:

Intake teams typically guess the breed of shelter dogs, so the breed column may have multiple words (for example, "Labrador Collie mix").

Display the name, gender, and age of all dogs that are part Labrador.

SELECT name, gender, age
FROM dogs
WHERE breed LIKE '%Labrador%';

Display the ids of all dogs that are under 1 year old.

SELECT id
FROM dogs
WHERE age < 1;

Display the name and age of all dogs that are female and over 35lbs.

SELECT name
FROM dogs
WHERE gender='female' AND weight > 351;

Display all of the information about all dogs that are not Shepherd mixes.

SELECT *
FROM dogs
WHERE breed NOT LIKE '%shepherd%';

Display the id, age, weight, and breed of all dogs that are either over 60lbs or Great Danes.

SELECT id, age, weight, breed
FROM dogs
WHERE weight > 60 OR breed = 'Great Danes';

### Given this cats table, what records are returned from these queries?

SELECT name, adoption_date FROM cats;

| name     | adoption_date            |
| -------- | ------------------------ |
| Mushi    | 2016-03-22T00:00:00.000Z |
| Seashell |                          |
| Azul     | 2016-04-17T00:00:00.000Z |
| Victoire | 2016-09-01T00:00:00.000Z |
| Nala     |                          |

SELECT name, age FROM cats;

| name     | age |
| -------- | --- |
| Mushi    | 1   |
| Seashell | 7   |
| Azul     | 3   |
| Victoire | 7   |
| Nala     | 1   |

### From the cats table, write queries to select the following pieces of data.
Display all the information about all of the available cats.

SELECT *
FROM cats

Display the name and sex of all cats who are 7 years old.

SELECT name, sex
FROM cats
WHERE age > 7;

Find all of the names of the cats, so you don’t choose duplicate names for new cats.

SELECT name
FROM cats

### List each comparison operator and explain when you would use it. Include a real world example for each.

> greater than - used to compare values and find largest. 9 apples > 8 apples.

< less than - used to compare values and find smallest. 7 apples < 8 apples.

= equal to - used to compare values. 3 apples = 3 apples.

>= greater than or equal to - used to compare values and find the largest, or one that is equal to the comparison. 9 apples >= 9 apples.

<= less than or equal to - used to compare values and find the smallest, or one that is equal to the comparison. 9 apples <= 9 apples.

!= not equal to - used to compare values and find out if they are equal to each other. 4 apples != 6 apples.

<> greater than or less than - used to compare values much like the !=. 1 apple <> 3 apples.

LIKE used with strings. We can use like along with '%' to find partial matches within strings. 'Dirty Dancing' could be found with LIKE '%Dirty%'.

BETWEEEN is used to determine if values are between or equal to parameters. BETWEEN 3 AND 7 would return 3, 4, 5, 6, and 7.

IS DISTINCT FROM is used like the <> operator, but can also be used in case one of the values could be null. 0 IS DISTINCT FROM (no value entered).

IS TRUE/IS FALSE is used to find out if an expression IS TRUE/FALSE, always returns either true or false. (value) IS TRUE would return if there is a value.

IS NULL is used to find out if the contacts of a cell are null. (empty cell) IS NULL, would return cells with null value.

AND requires both comparisons to be true.  WHERE pub_date > 1969 AND < 1980, would return everything between 1970 and 1979.

OR requires one or the other comparisons to be true.  WHERE pub_date = 1969 OR = 1980, would return years 1969 or 1980.

NOT requires expression to be false. WHERE pub_date NOT 1997 would return everything not not from 1997.


### 7. From the cats table below, what data would be returned from these queries?

SELECT name FROM cats WHERE gender = 'F’;
		Seashell
		Nala


SELECT name FROM cats WHERE age <> 3;
		Mushi
		Seashell
		Victoire
		Nala


SELECT ID FROM cats WHERE name != ‘Mushi’ AND gender = 'M’;
		00003
		00004
