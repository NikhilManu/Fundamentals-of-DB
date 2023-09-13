### Deadlock
A deadlock is a situation in which two or more processes are blocked, waiting for each other to release a resource. This can happen when two processes are each holding a resource that the other process needs.

The four necessary conditions for deadlock to occur are:
* Mutual exclusion: Each resource can only be used by one process at a time.
* Hold and wait: A process is holding at least one resource and waiting for another resource to become available.
* No preemption: A resource cannot be taken away from a process that is currently using it.
* Circular wait: There is a set of processes P1, P2, ..., Pn such that P1 is waiting for a resource held by P2, P2 is waiting for a resource held by P3, ..., Pn is waiting for a resource held by P1.