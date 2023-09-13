### Shared Lock
* Shared locks allow multiple transactions to read the same data simultaneously
* Shared lock prevents modification until all locks have been released. 
* Shared locks are also called read locks, and are used for maintaining read integrity.

### Exclusive Lock
* Exclusive locks allow only one transaction access to read or modify data at a given time. 
* No other transactions can read or modify the data until the current transaction releases its Exclusive lock. 
* Exclusive locks are also known as write locks.