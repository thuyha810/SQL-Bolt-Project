# SQL-Bolt-Project
- from [sqlbolt](https://sqlbolt.com/)

## Lesson 1: SELECT queries 101
1. Find the title of each film:
```sql
select title
from movies;
```
2. Find the director of each film:
```sql
select director
from movies;
```
3. Find the title and director of each film:
```sql
select title, director
from movies;
```
4. Find the title and year of each film:
```sql
select title, year
from movies;
```
5. Find all the information about each film:
```sql
select *
from movies;
```

## Lesson 2: Queries with constraints (Pt. 1)
1. Find the movie with a row id of 6:
```sql
select title
from movies
where id = 6;
```
2. Find the movies released in the years between 2000 and 2010:
```sql
select title
from movies
where year between 2000 and 2010;
```
3. Find the movies not released in the years between 2000 and 2010:
```sql
select title
from movies
where year not between 2000 and 2010;
```
4. Find the first 5 Pixar movies and their release year:
```sql
select title, year 
from movies
limit 5;
```

## Lesson 3: Queries with constraints (Pt. 2)
1. Find all the Toy Story movies:
```sql
select *
from movies
where title like ("%Toy Story%")
```
2. Find all the movies directed by John Lasseter:
```sql
select *
from movies
where director = "John Lasseter"
```
3. Find all the movies (and director) not directed by John Lasseter:
```sql
select *
from movies
where director != "John Lasseter"
```
4. Find all the WALL-* movies:
```sql
select *
from movies
where title like("%WALL-%")
```
## Lesson 4: Filtering and sorting Query results
1. List all directors of Pixar movies (alphabetically), without duplicates:
```sql
select distinct director
from movies
order by director asc
```
2. List the last four Pixar movies released (ordered from most recent to least):
```sql
select *
from movies
order by year desc
limit 4
```
3. List the first five Pixar movies sorted alphabetically:
```sql
select title 
from movies
order by title asc
limit 5 
```
4 List the next five Pixar movies sorted alphabetically:
```sql
select title 
from movies
order by title asc
limit 5 offset 5
```
## Lesson 5: Simple SELECT Queries
1. List all the Canadian cities and their populations:
```sql
select city, population
from north_american_cities 
where country = 'Canada'
```
2. Order all the cities in the United States by their latitude from north to south:
```sql
select city
from north_american_cities
where country ='United States'
order by latitude desc
```
3. List all the cities west of Chicago, ordered from west to east:
```sql
select city
from north_american_cities
where longitude < -87.629798
order by longitude
```
4. List the two largest cities in Mexico (by population):
```sql
select city
from north_american_cities
where country ='Mexico'
order by population desc
limit 2
```
5. List the third and fourth largest cities (by population) in the United States and their population:
```sql
select city, population
from north_american_cities
where country = 'United States'
order by population desc
limit 2 offset 2
```
## Lesson 6: Multi-table queries with JOINs
1. Find the domestic and international sales for each movie:
```sql
select title, domestic_sales, international_sales
from boxoffice b
inner join movies m
on b.movie_id = m.id
```
2. Show the sales numbers for each movie that did better internationally rather than domestically:
```sql
select title, domestic_sales, international_sales
from boxoffice b
inner join movies m
on b.movie_id = m.id
where international_sales > domestic_sales
```
3. List all the movies by their ratings in descending order:
```sql
select title
from movies m
inner join boxoffice b
on m.id = b.movie_id
order by b.rating desc
```
## Lesson 7: OUTER JOINs
1. Find the list of all buildings that have employees:
```sql
select distinct building
from employees
```
2. Find the list of all buildings and their capacity
```sql
select distinct building_name, capacity 
from buildings
```
3. List all buildings and the distinct employee roles in each building (including empty buildings)
```sql 
select b.building_name, e.role
from buildings b
left join employees e
on b.building_name = e.building
```
## Lesson 8: A short note on NULLs
1. Find the name and role of all employees who have not been assigned to a building
```sql
select name, role
from employees
where building is null
```
2. Find the names of the buildings that hold no employees
```sql
select b.building_name
from buildings b
left join employees e
on b.building_name = e.building
where building is null
```
## Lesson 9: Queries with expressions







