### Advantages
* Improves query performance when accessing a single partition
* Sequential scan vs scattered index scan
* Easy bulk loading (attach partition)
* Archive old data that are barely accessed into cheap storage

### Disadvantages
* Updates that move rows from a partition to another (slow or fail sometimes)
* Inefficient queries could accidently scan all partitions resulting slower performance
* Schema changes can be challenging