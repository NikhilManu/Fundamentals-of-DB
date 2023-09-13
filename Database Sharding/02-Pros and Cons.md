### Advantages
* Scalability of Data and Memory
* Security (users can access certain shards)
* Optimal and Smaller index size

### Disadvantages
* Complex client (aware of shard)
* Transaction across shard problem
* Rollbacks are hard.
* Schema changes are hard
* Joins across shards
* Has to be something you know in the query, or else it would need to check all of the shards
