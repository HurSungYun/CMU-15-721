Overview of MVCC

Maintain multiple “PHYSICAL” versions of a single “LOGICAL” object

MVCC is old actually

Main benefits

* Write does not block
* Read only trn -> no locks
* Easily support time-travel queries -> ??? -> rows of one week ago

Multi versioning affect whole design of architectures

Snapshot isolation -> consistent snapshot

Implement MVCC -> SI

MVCC design decisions

MVCC use multiple concurrency control protocol in practice

MVTO

Version, trn-id, read-ts, begin-ts, end-ts

Read -> add read-ts

Write -> write trn-id -> Compare and Swap -> make new version

Problem -> reading data is committed or not? -> need global data structure for that

MV2PL

Trn-id should be 32-bit for CAS

No need for lock table

If trn-id is reached MAX, all thing goes wrong

Postgres solution -> frozen flag

Runs the VACCUM before the system gets close to this upper limit

Q from student -> VACCUM when open transaction exists -> A. Calculate lower bound trn and do something more

Q from student -> how to timestamp query if using frozen flag -> epoch or counter

Version Storage -> latch free linked list

for performance, use local memory

Intend to no global sync or minimal global sync

Append-Only Storage -> Oldest-to-Newest or Newest-to-Oldest -> Trade-offs

Time-Travel Storage -> Main Table and Time-Travel Table -> SQL Server, SAP HANA

Delta Storage -> Time-Travel, but store Delta

Non-Inline Attribute -> Just ref. it (string)

Garbage Collection -> Tuple level and Trn level approach

Background Vacuuming -> you know what

Cooperate Cleaning -> only works with O2N

Ten-Level GC -> IDK

Index Management -> PKey indexes always point to version chain head

InnoDB is MV-2PL and Delta store!!!!

MVCC is the best approach for supporting txns in mixed workloads. 
