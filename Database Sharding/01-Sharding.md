### Sharding
* Database sharding is a technique for distributing data across multiple database servers. This is done to improve the performance and scalability of a database.
* A single database server can only handle a limited amount of data and traffic. Sharding helps to solve this problem by distributing the data across multiple servers. This allows each server to handle a smaller amount of data.
* We use Consistent Hashing to recognize the correct database shard to hit.

#### Horizontal Partioning Vs Sharding
* HP splits big table into multiple tables in the same database
* Sharding splits big table into multiple tables across multiple database servers
* HP table name changes (or schema)
* Sharding everything is the same but server changes

