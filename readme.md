![](http://i.giphy.com/KMrye8vZpv6py.gif)

# Exercise - SQL 64


[List of SQL Commands (important resource)](https://www.w3schools.com/sql/default.asp)


[Codecademy SQL Commands (also great)](https://www.codecademy.com/articles/sql-commands?r=master)

### Primary Key
![screen shot 2017-12-19 at 8 45 19 am](https://user-images.githubusercontent.com/6153182/34159939-111e3534-e499-11e7-8dc0-dc981518e0f1.png)

### NOT NULL
![screen shot 2017-12-19 at 8 47 19 am](https://user-images.githubusercontent.com/6153182/34160006-45f99a28-e499-11e7-9c45-960928c629ce.png)

Take the following schema for a N64 SQL database

``` SQL
 CREATE TABLE Games (
   id INTEGER PRIMARY KEY,
   title TEXT NOT NULL,
   year INTEGER NOT NULL,
   developers TEXT,
   genre TEXT
 );
```
Create a database with this schema and seed it with some sample data

```SQL
INSERT INTO Games(title, year, developers, genre) VALUES('The Legend of Zelda: The Ocarina of Time', 1998, 'Nintendo EAD', 'Action-Adventure');
INSERT INTO Games(title, year, developers, genre) VALUES('Super Smash Bros.', 1999, 'Hal Laboratory', 'Fighting');
INSERT INTO Games(title, year, developers, genre) VALUES('Super Mario 64', 1996, 'Nintendo EAD', 'Platforming');
INSERT INTO Games(title, year, developers, genre) VALUES('Golden Eye 007', 1997, 'Rare', 'First-Person Shooter');
INSERT INTO Games(title, year, developers, genre) VALUES('Mario Kart 64', 1996, 'Nintendo EAD', 'Racing');
INSERT INTO Games(title, year, developers, genre) VALUES('Star Fox 64', 1997, 'Nintendo EAD', 'Rail/Scrolling Shooter');
INSERT INTO Games(title, year, developers, genre) VALUES('Perfect Dark', 2000, 'Rare', 'First-Person Shooter');
INSERT INTO Games(title, year, developers, genre) VALUES('Star Wars: Shadow of the Empire', 1996, 'Lucas Arts', 'Action');
INSERT INTO Games(title, year, developers, genre) VALUES('Banjo-Kazooie', 1998, 'Rare', 'Platforming');
INSERT INTO Games(title, year, developers, genre) VALUES('Mario Party', 1998, 'Hudson Soft', 'Party Game');
INSERT INTO Games(title, year, developers, genre) VALUES('Tony Hawk''s Pro Skater' , 1996, 'Neversoft', 'Extreme Sports');
```

## Queries

Use SQL queries to complete the following tasks

1. Select the title of all games

`select title from games;`

2. Show all the years in the database.

`select year from games;`

3. Show the title of each game made by 'Rare'.

`select title from games where developers = 'Rare';`

4. Select all games that were made before 1998.

`select * from games where year < 1998;`

5. Find the average release year of all games.

`select avg(year) from games;`

6. Show the developer names of each game, in alphabetical order.

`select title, developers from games order by developers;`

7. Show the titles of games not made by 'Nintendo EAD'.

`select title, developers from games where developers != 'Nintendo EAD';`

8. Add the the game 'F-Zero X', released in 1998, made by 'Nintendo EAD', and with the genre 'Racing'.

`insert into games(title, year, developers, genre) values('F-Zero X', 1998, 'Nintendo EAD', 'Racing');`

9. Show all the game titles in descending order of their release year.

`select title, year from games order by year desc;`

10. Remove all games not made by 'Hudson Soft'.

`delete from games where developers != 'Hudson Soft';`

11. Show the average release year for games that were made by Rare or have the title `Tony Hawk''s Pro Skater` in order of their title

`select avg(year) from games where developers = 'Rare' or title = 'Tony Hawks''s Pro Skater';`

12. Show the id and title and genre of all games that were either:

  Made before 1997,

  Made by Hal Laboratory,

  Or, have the genre Platforming AND are made by Rare.

`select * from games where year < 1997 or developers = 'Hal Laboratory' or genre = 'Platforming' and developers = 'Rare';`  
