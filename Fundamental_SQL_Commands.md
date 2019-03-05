### 1. List the commands for adding, updating, and deleting data.

    `ALTER TABLE, DELETE, UPDATE, DROP TABLE, INSERT INTO, ADD COLUMN.`

### 2. Explain the structure for each type of command.

    ```
    ALTER TABLE:

    ALTER TABLE "table name here".

    DELETE:

    DELETE FROM "table name here" WHERE "column name here"

    UPDATE:

    UPDATE "table name here" SET "new cell value" WHERE "column and row goes here";

    DROP TABLE:

    DROP TABLE "table name here"

    INSERT INTO:

    INSERT INTO "table name goes here" (column name here, column name here, ...)

    VALUES (data value for column parameter, data value for column parameter, ... )

    ADD COLUMN:

    ALTER TABLE "table name goes here" ADD COLUMN "text of column goes here" "data type here"
    ```

### 3. What are some of the data types that can be used in tables? Give a real-world example of each type.

int (employee ID), money (US dollars or other currency), text (names of employees).


### 4. Decide how to create a new table to hold a list of people invited to a wedding dinner. The table needs to have first and last names, whether they sent in their RSVP, the number of guests they are bringing, and the number of meals (1 for adults and 1/2 for children).

Which data type would you use to store each of the following pieces of information?

- First and last name. text
- Whether they sent in their RSVP. boolean
- Number of guests. int
- Number of meals. float

- Write a command that creates the table to track the wedding dinner.

  ```
  CREATE TABLE wedding_dinner (
  first varchar,
  last varcahr,
  RVSP boolean,
  guests int,
  meals float  
  );
  ```

- Write a command that adds a column to track whether the guest sent a thank you card.

  `ALTER TABLE wedding ADD COLUMN card_sent text SET DEFAULT false;`

- You have decided to move the data about the meals to another table, so write a command to remove the column storing the number meals from the wedding table.

  `ALTER TABLE wedding DROP COLUMN number_of_meals;`

- The guests will need a place to sit at the reception, so write a command that adds a column for table number.

  `ALTER TABLE wedding ADD COLUMN table_number text;`

- The wedding is over and we do not need to keep this information, so write a command that deletes the table numbers   from the database.

  `ALTER TABLE wedding DROP COLUMN table_numbers;`

### 5.Write a command to create a new table to hold the books in a library with the columns ISBN, title, author, genre, publishing date, number of copies, and available copies.

```
CREATE TABLE library (
  ISBN int,
  title text,
  author varchar,
  genre varchar,
  publishing_date date,
  number_of_copies int,
  available_copies int
);
```

- Find three books and add their information to the table.
  ```
  INSERT INTO library (ISBN, title, author, genre, publishing_date, number_of_copies, available_copies, available_copies)
  VALUES
  (12345, 'Cat in the Hat', 'Dr. Suess', 'Kids', 1989, 20, 5),
  (12375, 'Bugs Life', 'Disney', 'Adventure', 1996, 19, 10),
  (12632, 'Harry Potter', 'R.L. Stien', 'Fiction', 1999, 30, 5);
  ```
- Someone has just checked out one of the books. Change the number of available copies to 1 fewer.

  `UPDATE library SET available_copies= 4 WHERE ISBN = 12345;`

- Now one of the books has been added to the banned books list. Remove it from the table.

  `DELETE from library WHERE ISBN = 12345;`

### 6.Write a command to make a new table to hold spacecrafts. Information should include id, name, year launched, country of origin, a brief description of the mission, orbiting body, if it is currently operating, and its approximate miles from Earth. In addition to the table creation, provide commands that perform the following operations:

```
CREATE TABLE spacecrafts (
  id int,
  name varchar,
  yearLaunched int,
  origin varchar,
  description varchar,
  orbiting varchar,
  currently_operating,
  miles_from_earth int,
);
```

- Add three non-Earth-orbiting satellites to the table.

```
INSERT INTO spacecrafts (id, name, yearLaunched, origin, description, orbiting, currently_operating, miles_from_earth) VALUES
(001, 'Viking', 1975, USA, 'To photograph and land on Mars.', 'Landed on Mars', FALSE, 33,900,000),
(002, 'Voyager', 1977, USA, 'To study outer solar system.', 'Interstellar Medium', TRUE, 13,000,000,000),
(003, 'Hubble', 1990, USA, 'To photograph the solar system.', 'Earth', TRUE, 340);
```

- Remove one of the satellites from the table since it has just crashed into the planet.

  `DELETE FROM spacecrafts WHERE id=001;`

- Edit another satellite because it is no longer operating and change the value to reflect that.

  `UPDATE spacecrafts SET currently_operating = false WHERE id = 002;`

### 7.Write a command to create a new table to hold the emails in your inbox. This table should include an id, the subject line, the sender, any additional recipients, the body of the email, the timestamp, whether or not you have read the email, and the id of the email chain it's in. Also provide commands that perform the following operations:

```
CREATE TABLE emails (
  id int,
  subject_line varchar,
  sender varchar,
  additional_recipients int,
  body varchar,
  timestamp time,
  read boolean,
  email_chain_id int

;)
```

- Add three new emails to the inbox.

```
INSERT INTO emails (id, subject_line, sender, additional_recipients, body, timestamp, read, email_chain_id)
VALUES
(001, 'Hello', 'Leeroy Jenkins', 1, 'Helloooo, its meeeeee', TIMESTAMP '2019-03-1 19:06:00', true, 4),
(002, 'Goodbye', 'Blue Face', 6, 'Bus down', TIMESTAMP '2019-04-3 12:11:00', false, 1),
(003, 'Why???', 'Joker', 3, 'Why so serious???', TIMESTAMP '2019-03-1 19:06:00', true, 4);
```

- You deleted one of the emails, so write a command to remove the row from the inbox table.

`DELETE FROM emails WHERE id=002;`

- You started reading an email but just heard a crash in another room. Mark the email as unread before investigating the crash, so you can come back and read it later.

`UPDATE emails SET read=false WHERE id=003;`
