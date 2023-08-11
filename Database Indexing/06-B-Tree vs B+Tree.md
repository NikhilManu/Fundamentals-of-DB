### B-Tree
* Data Structure for fast traversal
* if B-Tree is of "m" degree, then node can have up to "m-1" elements
* Each element has a key and value
* The value is the data pointer to the row. Data pointer can point to primary key or the tuple
* A node means disk page

#### Limitations of B-Tree
* Elements in all nodes store both the key and the value
* Internal nodes take more space thus require more IO and can slow down traversal
* Range queries are slow because of Random Access(Direct Access)


### B+Tree
* Only stores keys in internal nodes
* Values are only stored in leaf nodes
* Internal nodes are smaller since they only store keys and they can fit more elements
* Leaf nodes are linked so once a key is found, we can find all values before and after the key. (So leaf node contains all elements)
* Great for Range queries

#### B+Tree and DBMS Considerations
* Cost of leaf pointer (Cheap)
* 1 Node fits a DBMS page (most DBMS)
* Can fit internal nodes easily in memory for fast traversal
* Leaf nodes can live in data files in the heap
* Most DBMS system use B+Tree

#### Storage Cost in Postgres vs MySQL
* B+Trees secondary index values can either point direcly to tuple (Postgres) or to the primary key (MySQL)
* if the Primary key data type is expensive this acn bloat in all secondary indexes for MySQL
* Leaf nodes in MySQL contains the full row since its an clustered index