## Key Column Indexing
    Key Columns are the columns that uniquely identify each row in a table. Indexing key columns is crucial for maintaining data integrity
    and ensuring efficient data retrieval for primary key lookups and join operations.
    Primary Key Indexes are automatically created when a primary key constraint is defined on a column or set of columns

## Non-Key Column Indexing
-----------------------
    Non-Key Columns are columns that are not part of any primary key or unique key constraint. Indexing non-key column can improve the query
    performance for filtering, searching and sorting operations involving these columns
    But Non-Key column indexes consume additional storage space and may have overhead on data modification operations.

