# MVCC Garbage collection

MVCC DBMS needs to remove "reclaimable" physical versions

long-running queries block GC and after commit, it could cause a CPU spike

first-writer-wins makes your life easier

tombstone tuple -> empty physical version to indicate that a logical tuple is deleted

MVCC usually do not store version info in index

MVCC DUPLICATE KEY PROBLEM -> conditional inserts for PK needed

GC Design Decisions

* Index Clean up -> remove index modifications on abort
* Version Tracking / Identification -> Tuple-level and Transaction-level
* Granularity -> trade-off between reclaim versions sonner vs computing overhead
* Comparison Unit

false negative is okay

block compaction
