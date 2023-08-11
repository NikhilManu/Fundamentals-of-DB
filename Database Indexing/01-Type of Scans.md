
### Table Scan
A table scan involves reading each and every row in a table to find the required data.This usually done when no suitable index exist or when the 
query retrieves a large portion of the table.

### Index Scan
    An index scan involves using an index structure to locate the rows that satisfy the query condition. This can be faster than the table scan for
    the queries that retrieves a small portion of the table. The DB engine uses the index to directly access the relevant rows, avoiding the need to
    read the entire table.

    Note: When creating composite index in postgres, lets say
    eg: create index grades(a, b)
        Here index is for either a OR for both a and b. b doesnt have a index alone

### Bitmap Index Scan
    We know that Index scan is not best if we retrieve large portion of the table, because of Random Access(Direct Access). But there might be a case
    where we need a significant amount of data, and doing index scan is better than table scan.
    Here we can do the Bitmap index scan, Here for each index which satisfy the where condition we mark the bit as 1 for corresponding page number and
    we retrieve the rows at the end.

    if there are multiple where conditions (eg: SELECT * FROM T WHERE col1 < 20 AND col2="data")
    Here, a bitmap for col1 < 20 is created and then another bitmap for col2="data2" is created. Finally AND operation is performed on them to get the
    pages which satisfy the condition.

    Note: Recheck of the where condition will be done again finally. This is required because database stores data in pages inside the heap, so one
    page may contain multiple rows, since we are fetching the page as whole from bitmap, some pages may contain data which doesn't satisfy the condition.