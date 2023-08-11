## Index Scan
    A query execution method where database uses an index to locate and retreive the rows that match certain condition from a table.
    Here method retrieves both indexed columns and also then fetches the corresponding page where the rows lie.

## Index-Only Scan
    This is a more optimized version of Index Scan where we will get the required data from the index itself. (ie.. we dont need extra infromation from the table)

    Eg: CREATE INDEX id_idx ON grades(id) include (name)
        Here we are indexing the id and only including the column name with it. So the column 'name' will not be used for indexing.  

