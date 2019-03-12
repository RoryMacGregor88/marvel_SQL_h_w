# SQL Homework

The local cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'

```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:

```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1.  Return ALL the data in the 'movies' table.

SELECT * FROM movies;

id |                title                | year | show_time
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 23:40
  2 | The Incredible Hulk                 | 2008 | 17:30
  3 | Iron Man 2                          | 2010 | 20:40
  4 | Thor                                | 2011 | 16:30
  5 | Captain America: The First Avenger  | 2011 | 13:10
  6 | Avengers Assemble                   | 2012 | 20:30
  7 | Iron Man 3                          | 2013 | 23:05
  8 | Thor: The Dark World                | 2013 | 23:10
  9 | Batman Begins                       | 2005 | 18:00
 10 | Captain America: The Winter Soldier | 2014 | 16:10
 11 | Guardians of the Galaxy             | 2014 | 17:15
 12 | Avengers: Age of Ultron             | 2015 | 23:35
 13 | Ant-Man                             | 2015 | 15:00
 14 | Captain America: Civil War          | 2016 | 21:35
 15 | Doctor Strange                      | 2016 | 20:40
 16 | Guardians of the Galaxy 2           | 2017 | 22:45
 17 | Spider-Man: Homecoming              | 2017 | 22:40
 18 | Thor: Ragnarok                      | 2017 | 17:40
 19 | Black Panther                       | 2018 | 22:00

2.  Return ONLY the name column from the 'people' table

SELECT name FROM people;

name          
------------------------
Jennifer Archibald
Katharina Bitzan
Myriam Boran
David Boyle
Alasdair Carstairs
Eric Cross
Amy Edwardson
Jordan Davidson
Stephen Gibson
Mark King
Rory MacGregor
Robert Marshall
Becky Nielsen
Grant Rutherford
Kanokwan Sritawan
Montgomery Stanczak
Lidia Stopinska-Cherek
Ben Svajko/ Barker
Maria Toscano
Annabel Treshansky
Charlie Walker
Jon Zarecki

3.  Oops! Someone at CodeClan got Mateusz's name wrong! Change it to reflect Mateusz' proper name ('Montgomery' should be 'Mateusz').

UPDATE people SET name = 'Mateusz Stanczak' WHERE name = 'Montgomery Stanczak';

name          
------------------------
Jennifer Archibald
Katharina Bitzan
Myriam Boran
David Boyle
Alasdair Carstairs
Eric Cross
Amy Edwardson
Jordan Davidson
Stephen Gibson
Mark King
Rory MacGregor
Robert Marshall
Becky Nielsen
Grant Rutherford
Kanokwan Sritawan
Montgomery Stanczak
Lidia Stopinska-Cherek
Ben Svajko/ Barker
Maria Toscano
Annabel Treshansky
Charlie Walker
Jon Zarecki
(22 rows)

UPDATE 1

4.  Return ONLY your name from the 'people' table.

SELECT name FROM people WHERE name = 'Rory MacGregor';

name      
----------------
Rory MacGregor
(1 row)

5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM movies WHERE title = 'Batman Begins';

DELETE 1

6.  Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people (name) VALUES ('Jarrod Bennie');

UPDATE 1

7.  Jordan Davidson has abandoned us. Remove him from the table of people.

DELETE FROM people WHERE name = 'Jordan Davidson';

DELETE 1
DELETE 1

8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, year, show_time) VALUES ('Avengers: Infinity War', 2018, '00:00');

DELETE 1
DELETE 1
INSERT 0 1
INSERT 0 1

9.  The cinema would also like to make the Guardians movies a back to back feature. Find out the show time of "Guardians of the Galaxy" and set the show time of "Guardians of the Galaxy 2" to start two hours later.

UPDATE movies SET show_time = '19:15' WHERE title = 'Guardians of the Galaxy 2';

DELETE 1
DELETE 1
INSERT 0 1
UPDATE 1

## Extension

1.  Research how to delete multiple entries from your table in a single command.

--if you want to delete entire rows, instead of
DELETE FROM movies WHERE something...,
you would just leave out the WHERE and it would delete all rows.
There's a lot more, but that one seemed the most direct. 
