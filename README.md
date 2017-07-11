
1.  Making Tech Spaces Safe for Diverse Faces
2. Toronto
    Ottawa
3.  Tilde Ann Thurium
4. one_to_many_assignment=# SELECT COUNT(name) FROM provinces;
 count
-------
    14
(1 row)

5. one_to_many_assignment=# SELECT COUNT(name) FROM provinces;
 count
-------
    14
(1 row)

one_to_many_assignment=# SELECT name FROM residences;
ERROR:  column "name" does not exist
LINE 1: SELECT name FROM residences;
               ^
one_to_many_assignment=# SELECT street FROM residences;
ERROR:  column "street" does not exist
LINE 1: SELECT street FROM residences;
               ^
one_to_many_assignment=# SELECT id FROM residences WHERE address = '4740 McDermott Street';
 id
----
  9
(1 row)

one_to_many_assignment=# SELECT persons WHERE residence_id = 9;
ERROR:  column "persons" does not exist
LINE 1: SELECT persons WHERE residence_id = 9;
               ^
one_to_many_assignment=# SELECT name FROM persons WHERE residence_id = 9;
     name
--------------
 Malvina King
 Theo Wolff
(2 rows)


6.                                              ^
one_to_many_assignment=# SELECT city_id FROM residences WHERE address = '4740 McDermott Street';
 city_id
---------
      11
(1 row)

one_to_many_assignment=# SELECT name FROM cities WHERE city_id = 11;
ERROR:  column "city_id" does not exist
LINE 1: SELECT name FROM cities WHERE city_id = 11;
                                      ^
one_to_many_assignment=# SELECT name FROM cities WHERE residence.city_id = 11;
ERROR:  missing FROM-clause entry for table "residence"
LINE 1: SELECT name FROM cities WHERE residence.city_id = 11;
                                      ^
one_to_many_assignment=# select name FROM cities WHERE id = 11;
  name
--------
 Ottawa
(1 row)

7. one_to_many_assignment=# SELECT province_id FROM cities WHERE id = 11;
 province_id
-------------
          14
(1 row)

one_to_many_assignment=# SELECT name FROM provinces WHERE id = 14;
  name
---------
 Ontario
(1 row)

8. one_to_many_assignment=# SELECT country_id FROM provinces WHERE id = 14;
 country_id
------------
          1
(1 row)

one_to_many_assignment=# SELECT name FROM countries WHERE id = 1;
  name
--------
 Canada
(1 row)

9. one_to_many_assignment=# Select * FROM persons WHERE name = 'Destini Davis';
 id |     name      | age | residence_id
----+---------------+-----+--------------
  3 | Destini Davis |  37 |            2
(1 row)

one_to_many_assignment=# SELECT city_id FROM residences WHERE id = 2;
 city_id
---------
       8
(1 row)

one_to_many_assignment=# SELECT province_id FROM cities WHERE id = 8;
 province_id
-------------
          14
(1 row)

one_to_many_assignment=# SELECT country_id FROM provinces WHERE id = 14;
 country_id
------------
          1
(1 row)

one_to_many_assignment=# SELECT name FROM countries WHERE id = 1;
  name
--------
 Canada
(1 row)

10. one_to_many_assignment=# SELECT id FROM authors WHERE name = 'Aditya Mukerjee';
 id
----
  2
(1 row)

one_to_many_assignment=# SELECT title FROM articles WHERE author_id = 2;
                          title
---------------------------------------------------------
 I Can Text You A Pile of Poo, But I Can’t Write My Name
(1 row)
