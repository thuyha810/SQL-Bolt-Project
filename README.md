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



