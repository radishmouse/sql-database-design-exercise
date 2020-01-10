
Using the `sql-intro` code for reference, create database projects for each of the following topics:

- pets and owners
- books and authors
- paintings and artists
- teams and players
- cities and states


Please include:

- a `schema.sql` for your `create table` statements
- a `seed.sql` for your `insert into` statements
- `npm` scripts to reset the database as needed ;)

Here is an example of some queries you can make:

```sql

-- show me all of miles davis' albums
select * from albums where artist_id=1;

-- show me the title of 1 album of miles davis'
select title from albums where artist_id=1 limit 1;

-- what is the id for artist whose name starts 
-- with "miles"
select id from artists where name ilike 'miles%';
-- select id from artists where name='Miles Davis';

-- show me all albums for an artist whose name starts
-- with "miles"
select * from albums where artist_id=(select id from artists where name ilike 'miles%');
-- after Postgres runs the "inner query", it can now run this query:
--select * from albums where artist_id=(1);
```