### SQL Pagination With Offset is very Slow

`SELECT title FROM news OFFSET 100 LIMIT 10`

* Offset by design means fetch and drop x number of rows
* Here in this ex, (We are req for Page 10) the db will fetch first 110 rows and drop the first 100 rows

#### Problem of Reading Twice  

`SELECT title FROM news OFFSET 110 LIMIT 10`

Consider a user requested for Page 11, meanwhile a new insertion took place which may push down the data that you read early causing you to read it again.


### Simple Solution

`SELECT title, id fROM news ORDER BY id desc LIMIT 10`

This query is returned to the user first, from this user can see what is the last ID it saw.
For ex lets say last ID was 1100

`SELECT title, id FROM news where id < 1100 ORDER BY desc LIMIT 10`

This query will only work with 10 Rows rather than fetch and dropping like what offset did
