# Transaction

Bifurcated Env

OLTP Data Silos -> ETL (Extract, Transform, Load) -> OLAP

A txn is a sequence of actions that are executed on a shared database to perform some higher-level function 

Action classification

protected -> do not externalize their results before done

Protected actions are built upon unprotected actions

### Transaction Models

Flat -> BEGIN -> COMMIT or ROLLBACK -> limitations like no partial rollback

Savepoint -> ROLLBACK and RELEASE

Nested transactions

Savepoint

Multiple txns executed one after another -> COMMIT/BEGIN is atomic -> why this? -> partial commit for good use

Compensating Transactions -> what is logical changes??? -> how can it be done? -> just by user for now

chain, Saga transactions -> not supported natively

Concurrency control -> Atomicity and Isolation

CC schemes

2PL -> deadlock detection, prevention

T/O -> basic T/O, OCC

—

https://15721.courses.cs.cmu.edu/spring2019/papers/02-transactions/p209-yu.pdf

Concurrency control evaluation

Running in extreme environments exposes what are the main bottlenecks in the DBMS. 

Only about 5 percent were useful works if in WRITE-INTENSIVE / HIGH-CONTENTION workload

Lock Thrashing -> like domino

Timestamp Allocation -> mutex is the worst solution

Memory Allocations -> “Default libc malloc is slow. Never use it” LOL

Isolation Levels -> exactly what I saw in Mysql configs.

Criticism of isolation levels -> there are two more isolation levels -> CURSOR STAB, SNAPSHOT ISO

CURSOR STAB -> between REPEATABLE READ and READ COMMITTED -> prevent Lost Update

SNAPSHOT ISO -> Guarantees that all reads made in a txn see a consistent snapshot of the database 


