Ex Query:

    SELECT * FROM T
    WHERE F1=1 AND F2=4 

    CREATE INDEX ON T(F1) => F1_IDX
    CREATE INDEX ON T(F2) => F2_IDX


There is so many was so solve this Query
 
#### Case 1:
Database Optimizers decide to use both of them.

* Query's F1_IDX and gets all the ids that matches
* Query's F2_IDX and gets all the ids that matches
* Then it does an intersection on both results (will do union in case of OR)

When does it decide to take both index? When the resultset is not too large or too small.

#### Case 2:
When the Optimizer decide to use one index over the other.
Database does this when they know result of one index is very large. Since this is AND condition they only need to take 
smaller result and reapply the other condition on to the current result.

#### Case 3:
No indexes are used. (Full Table scan)
Database does this when it know the search will yeild so many rows that its going to be faster to do a full table scan.
Here Table statistics are very critical.


