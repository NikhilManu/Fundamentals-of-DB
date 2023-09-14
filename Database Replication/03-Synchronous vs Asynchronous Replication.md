#### Synchronous Replication
* A write transaction to the master will be blocked until it is written to the backup/standby nodes
* We dont need to wait for it write to all backup node. We can configure it to do like - First 2 or First 1 or Any

#### Asynchronous Repliation 
* A write transaction is considered successful if it is written to the master, then asynchronously the writes are applied to backup nodes