### How do you find related data held in two separate data tables?

By using Join statements and see if the data can join together.

### Explain, in your own words, the difference between an INNER JOIN, LEFT OUTER JOIN, and RIGHT OUTER JOIN. Give a real-world example for each.

INNER JOIN only shows what was selected from the two tables

LEFT OUTER JOIN Shows the left selected table and data that is joined between the
two selected tables

RIGHT OUTER JOIN shows the data shared between two tables and the right tables data.

An example would be married people and homeowners. They both have a name column and a SSN.
 An INNER JOIN would be if we wanted to find out people who are both married and homeowners
 An LEFT OUTER JOIN would be all married people whether or not married
 An RIGHT OUTER Join would be all homeowners whether or not married.

### Define primary key and foreign key. Give a real-world example for each.

A primary key is a unique identifier for each row in a database an example is a id number
A foreign key is a primary key that is in one table and not the other table.

An example is a employee
works in  department and the department number column in the employee  is the foreign key which links to the department

### Define aliasing.

Aliasing is abbreviating a table name when selecting and joining.

### Change this query so that you are using aliasing:
```
SELECT professor.name, compensation.salary,
compensation.vacation_days FROM professor JOIN
compensation ON professor.id =
compensation.professor_id;
```

SELECT p.name, c.salary, c.vacation_days
FROM professor AS p
JOIN compensation AS c
ON p.id = c.professor_id;

### Why would you use a NATURAL JOIN? Give a real-world example.
When you want to show column names that appear in both tables. An example would be when you have a food table that has item-id and item-name and a company table has company-id and company-name and you combine all the items in both tables
to get company-id, item-id, item-name and company-name.

### Using this Employee schema and data, write queries to find the following information:
- List all employees and all shifts.
```
SELECT employees.name, shifts.date, shifts.start_time, shifts.end_time
FROM employees JOIN shifts
ON employees.id = shifts.id;
```

### Using this Adoption schema and data, please write queries to retrieve the following information and include the results:

- Create a list of all volunteers. If the volunteer is fostering a dog, include each dog as well.
  ```
  SELECT volunteers.first_name ,
        volunteers.last_name ,
        dogs.name
        FROM volunteers
       LEFT  JOIN dogs
        ON volunteers.foster_dog_id = dogs.id;
  ```

- The cat's name, adopter's name, and adopted date for each cat adopted within the past month to be displayed as part of the "Happy Tail" social media promotion which posts recent successful adoptions.
```
SELECT cats.name, adopters.first_name, cat_adoptions.date
FROM cat_adoptions
LEFT OUTER JOIN cats
ON cats.id = cat_adoptions.cat_id
INNER JOIN adopters
ON adopters.id = cat_adoptions.adopter_id
WHERE  cat_adoptions.date < NOW() - INTERVAL '30 days' ;
```

- Create a list of adopters who have not yet chosen a dog to adopt.
```
SELECT adopters.first_name AS "Name"
FROM adopters JOIN dog_adoptions
ON adopters.id <> dog_adoptions.adopter_id;
```

- Lists of all cats and all dogs who have not been adopted.
```
SELECT dogs.name AS "Dog Name", dogs.in_foster AS "In Foster"
FROM dogs
JOIN dog_adoptions
ON dogs.id <> dog_adoptions.adopter_id;

SELECT cats.name AS "Cats Name", cats.adoption_date
FROM cats
JOIN cat_adoptions
ON cats.id <> cat_adoptions.adopter_id;
```

- The name of the person who adopted Rosco.
```
SELECT adopters.first_name, dog_adoptions.adopter_id, dogs.name, dogs.id
FROM adopters
JOIN dog_adoptions ON adopters.id = dog_adoptions.adopter_id
JOIN dogs ON dogs.id = dog_adoptions.dog_id;
```

### Using this Library schema and data, write queries applying the following scenarios and include the results:

- To determine if the library should buy more copies of a given book, please provide the names and position, in order, of all of the patrons with a hold (request for a book with all copies checked out) on "Advanced Potion-Making".
```
SELECT patrons.name, holds.isbn, books.title, holds.rank
FROM patrons
JOIN holds ON patrons.id = holds.patron_id
JOIN books ON books.isbn = holds.isbn
WHERE holds.isbn = '9136884926'
ORDER by holds.rank;
```

- List all of the library patrons. If they have one or more books checked out, list the books with the patrons.
```
SELECT patrons.id, patrons.name, transactions.isbn, books.title
FROM patrons
JOIN transactions ON patrons.id = transactions.patron_id
JOIN books ON transactions.isbn = books.isbn
ORDER BY patrons.id;
```
