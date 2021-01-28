## Mode SQL Practice

Link: https://mode.com/sql-tutorial/introduction-to-sql/

**`Q`:**

Write a query that only shows rows for which the month_name starts with the letter "N" or an earlier letter in the alphabet.

**`NOTE`:**

"group" appears in quotations above because GROUP is actually the name of a function in SQL. The double quotes (as opposed to single: ') are a way of indicating that you are referring to the column name "group", not the SQL function. In general, putting double quotes around a word or phrase will indicate that you are referring to that column name.

```json
SELECT *
  FROM tutorial.billboard_top_100_year_end
 WHERE "group" LIKE 'Snoop%'
```

In this example, the results from the Billboard Music Charts dataset will include rows for which "group" starts with "Snoop" and is followed by any number and selection of characters.

To ignore case when you're matching values, you can use the ILIKE command:

```json
SELECT *
  FROM tutorial.billboard_top_100_year_end
 WHERE "group" ILIKE 'snoop%'
```

You can also use _ (a single underscore) to substitute for an individual character:

```json
SELECT *
  FROM tutorial.billboard_top_100_year_end
 WHERE artist ILIKE 'dr_ke'
```

BETWEEN includes the range bounds (in this case, 5 and 10) that you specify in the query.

WHERE artist = NULL will not work—you can't perform arithmetic on null values.

NOT is also frequently used to identify non-null rows, but the syntax is somewhat special—you need to include IS beforehand. Here's how that looks:

```sql
SELECT *
  FROM tutorial.billboard_top_100_year_end
 WHERE year = 2013
   AND artist IS NOT NULL
```