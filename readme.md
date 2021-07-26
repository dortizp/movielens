## MovieLens

This assignment consists of creating SQL queries that answer the questions on `movielens-part1.md` and `movielens-part2.md` files.

To query the movielens database you will need to create it on your local environment using the `movielens.sql` dump file.

`Clone` this repo, navigate to it and just execute the following script:

```bash
$ createdb -h <postgres service ip> -U postgres movielens
$ psql -h <postgres service ip> -U postgres -d movielens < movielens.sql
```

The respond should be something like this:

```bash
BEGIN
NOTICE:  table "occupations" does not exist, skipping
DROP TABLE
CREATE TABLE
INSERT 0 21
NOTICE:  table "users" does not exist, skipping
DROP TABLE
CREATE TABLE
INSERT 0 943
NOTICE:  table "ratings" does not exist, skipping
DROP TABLE
CREATE TABLE
INSERT 0 100000
NOTICE:  table "movies" does not exist, skipping
DROP TABLE
CREATE TABLE
INSERT 0 1682
NOTICE:  table "genres" does not exist, skipping
DROP TABLE
CREATE TABLE
INSERT 0 18
NOTICE:  table "genres_movies" does not exist, skipping
DROP TABLE
CREATE TABLE
INSERT 0 2891
COMMIT
```

Then you can connect using:

```bash
$ psql -h <postgres service ip> -U postgres -d movielens
psql (11.5)
Type "help" for help.

movielens=#
```

From here you can start writing your queries:

```bash
movielens=# SELECT * FROM genres;
 id |    name
----+-------------
  1 | Action
  2 | Adventure
  3 | Animation
  4 | Childrens
  5 | Comedy
  6 | Crime
  7 | Documentary
  8 | Drama
  9 | Fantasy
 10 | Film-Noir
 11 | Horror
 12 | Musical
 13 | Mystery
 14 | Romance
 15 | Sci-Fi
 16 | Thriller
 17 | War
 18 | Western
(18 rows)
```

If you want to use another management interface to interact with postgresql, we reccomend [pgAdmin](https://www.pgadmin.org/download/). Feel free to use the
management interface of your preference.

When you finish, make a Pull Request with your answers.

```
MovieLens data sets were collected by the GroupLens Research Project
at the University of Minnesota.

This data set consists of:
	* 100,000 ratings (1-5) from 943 users on 1682 movies.
	* Each user has rated at least 20 movies.
  * Simple demographic info for the users (age, gender, occupation, zip)

F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets:
History and Context. ACM Transactions on Interactive Intelligent
Systems (TiiS) 5, 4, Article 19 (December 2015), 19 pages.
DOI=http://dx.doi.org/10.1145/2827872
```
