HEKATON MVCC

BeginTS and commitTS

Oldest to newest

Write-write conflict -> first wins

HEKATON: TRANSACTION STATE MAP -> ACTIVE, VALIDATING, COMMITTED, TERMINATED

HEKATON TRANSACTION META DATA

Read set, write set -> pointers

Scan set -> not store actual sql string

Commit dependencies -> list of transactions, works like pub/sub

HEKATON lessons -> lock-free data structures, 

Mention skip list -> sql uses BW tree

Q. Can validation phase have cyclic dependencies -> no

HYPER MVCC -> column store

Has interesting validation part -> ???

Do not need to care writes after we start (under Snapshot isolation)

30 citations for 30 years lol

Precision Locking ????? -> prevent phantom read

Q. How to handle complex joins in precision locking? -> only where clause matters

VERSION SYNOPSES

If statements sucks (slow)

Offset for null version vectors

SAP HANA (N2O)

VERSION STORAGE

Version flag and version storage

Transactions -> store a pointer to a context object ( do not store meta data)

MVCC LIMITAIONS -> Computation and Storage Overhead (CPU Cache Miss), Shared Memory Writes (Non-locality), Timestamp Allocation (single counter)

OCC LIMITATIONS -> Frequent Aborts, Extra Read and Writes, Index Contention

CMU CICADA -> PASSED

