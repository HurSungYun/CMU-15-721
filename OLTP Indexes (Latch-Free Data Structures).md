B+ Tree was designed for data stored on slow disks

### T-Trees

-> AVL Tree but pointers, not keys (because of memory limitation in 90s)

see range first, and then check each pointers.

Advantages -> uses less memory

Disadvantages -> difficult to rebalance, range scan is inefficient

Thus, T-Tree is ONLY used in some embedded systems now.

THE EASIEST WAY TO IMPLEMENT A DYNAMIC ORDER-PRESERVING INDEX IS TO USE A SORTED LINKED LIST (Average Cost: O(N))

it's Skip Lists.

To insert a new key, flip a coin to decide how many levels to add.

when insert, change pointers bottom to the top. (it's reasonable)

Advantages -> No Rebalance, concurrent with a CAS

Skip Lists: DELETE

first logically remove (flag) and physically remove later.

physicall remove is done in reverse order. (top to bottom)

Q. how to CAS doubly-linked Lists? -> oh it's limitation

-> so we cannot have reverse pointers in a latch-free concurrent Skip List.

update multiple addresses atomically? -> Bw-Tree

Bw-Tree

B+Tree with mapping table. (Page has Delta chain)

Bw-Tree: Garbage Collection

Bw-Tree: Structure Modifications

use split, seperator records

Why Skip List so slow?
