Index Locking and Latching

B-tree vs B+Tree -> use B+Tree because of range query

Locks vs Latches

Locks -> txn based, Latches -> internal data structure based (thread)

Lock is more high level primitives

Latch Implementation

* Blocking OS Mutex -> expensive (25ns????)
* Test-and-Set Spinlock (TAS) -> std::atomic<T> -> causes underlying hardware traffic -> not cache-friendly
* Queue-based Spinlock (MCS) -> how to delete base latch?
* RWLock

Latch Crabbing -> release latch on a parent node if its child node considered safe

Latch Crabbing does not solve Phantoms between txns -> Index Locks needed

Index locks

* Predicate Locks -> never invented in any system
* Key-Value Locks -> need virtual keys for non-existent values
* Gap Locks -> lock between keys (it’s gap)
* Key-Range Locks
* Hierarchical Locking -> In-eXclusive and eXclusive -> some kinda RWLock?

Hierarchical locking -> what’s the difference between RWLock
