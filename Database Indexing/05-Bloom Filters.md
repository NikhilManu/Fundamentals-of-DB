### Check if User Exists Efficiently with Bloom Filter

In many applications, a common task is to check if a username exists. Rather than querying the database every time, we can employ a clever optimization using a Bloom Filter to significantly enhance efficiency.

#### How a Bloom Filter Works
A Bloom Filter is a smart data structure that begins with an array of bits, initially all set to zero.

We utilize multiple hash function to map each username to specific positions within the array, and then we set the corresponding bits to one.

#### Username Query:
Imagine a request comes in, such as GET /username?q=jack.
Before going to the database, we can quickly check the Bloom Filter.

If the bit at the position determined by Hash(jack) is 0, it implies that the user "jack" doesn't exist.

If the bit is 1, it suggests there might be a user named "jack".
However, we need to confirm this against the database to be certain.

#### Disadvantage
If the Bloom Filter fills completely, then every call will go to the Database.