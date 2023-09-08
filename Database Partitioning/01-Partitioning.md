### What is Partitioning?
Partitioning is the idea where we break the table into smaller parts so that we can make application more scalable and performant

#### Vertical and Horizontal Parititoning
* Horizontal Partitioning splits rows into partitions
* Vertical partitioning splits columns partitions. (Done when we some column which we rarely use and dont want the column to consume the fast access drive, so we can partition and store it in a slow access drive)

### Partitioning Types
* By Range - Dates, ids
* By List - Discrete values (zip Codes)
* By Hash - Hash Functions (consistent Hashing)


NOTE: Make sure Partition Pruning is always ON