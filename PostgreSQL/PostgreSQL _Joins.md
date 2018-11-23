# PostgreSQL - Joins

- ### Inner join

  - Inner Join is also known as join or simple join. This join returns all rows from multiple tables where the join conditions are satisfied.

  - Inner-join syntax.

    ```sql
    SELECT table1.column1, table2.column2...
    FROM table1
    INNER JOIN table2
    ON table1.common_filed = table2.common_field;
    ```

  - Example Inner-join query

    `` SELECT c.code,name,region,year,fertility_rate 
    FROM countries AS c 
    INNER JOIN populations AS p 
    ON c.code=p.country_code;``

- ### Inner Join Via Using

  - syntax

    ```sql
    SELECT table1.column1, table2.column2...
    FROM table1
    INNER JOIN table2
    USING(common_filed);
    ```

  - Example Inner-join via USING 

    `` select c.name as country,continent,l.name as language, official 
    from countries as c 
    inner join languages as l
    USING (code)``;

- ### Self-join

  - We can join a table against itself. This is called a self join.

  - Quary

    `` SELECT p1.country_code, 
    ​       p1.size AS size2010,
    ​       p2.size AS size2015,
    ​       ((p2.size - p1.size)/p1.size * 100.0) AS growth_perc
    FROM populations AS p1
    INNER JOIN populations AS p2
    ON  p1.country_code = p2.country_code
    AND p1.year=p2.year - 5;``

- ### Case when and then

  - Evaluates a list of conditions and returns one of multiple possible result expressions.

  - Syntax

    `` CASE input_expression   
    WHEN when_expression THEN result_expression [ ...n ][ ELSE else_result_expression ]   
    END   ``

  - Query

    `` SELECT name, continent, code, surface_area,
    ​    CASE WHEN surface_area > 2000000 THEN 'large'
    ​        WHEN surface_area > 350000 THEN 'medium'
    ​        ELSE 'small' END
    ​        AS geosize_group
    FROM countries;``

    `` SELECT country_code, size,
    ​    CASE WHEN size > 50000000 THEN 'large'
    ​        WHEN size > 1000000 THEN 'medium'
    ​        ELSE 'small' END
    ​        AS popsize_group
    INTO pop_plus
    FROM populations
    WHERE year = 2015;``
