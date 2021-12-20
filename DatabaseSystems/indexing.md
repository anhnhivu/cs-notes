# Indexing

### Placing File Records on Disk

- record type: `struct employee {}`
- data type: `char name[30]`

### Methods for organizing record of a file on disk

**Heap file**
- heap/ pile file
- simplest file structure, no particular order
- new records inserted at the end of the file -> insertion is efficient
- linear search, waste memory in the middle when deleting

**Sorted file**
- sequential file
- sorted by values of an ordering field -> key
- inserting and deleting are expensive

```
 --------------------- -------------------------------- ------------------------------------
| Type of Organzation |  Access/ Search method         |  Average blocks to access a record |
 --------------------- -------------------------------- ------------------------------------
| Heap (unordered)    | sequential scan/ linear search |  b/2                               |
 --------------------- -------------------------------- ------------------------------------
| Ordered             | sequential scan/ linear search |  b/2                               |
 --------------------- -------------------------------- ------------------------------------
| Ordered             | binary search                  |  log2(b)                           |
 --------------------- -------------------------------- ------------------------------------
```

**Hasing technique**

Internal Hasing
- hash table
- common hash function: `h(K) = K mod M`
- collision
- typically kept 70-90% full

External Hashing 
- for disk files
- the space is made of buckets

### single-level ordered indexes
primary, clustering, secondary index

- primary: ordered on a key field
- nondense index: number of entries < number of records
- clustering: ordered on a non-key field

```
 --------------------- ----------------------- -------------------------------
|  Indexing field     |  is ordered           |  is unordered                 |
 --------------------- ----------------------- -------------------------------
|  is key             | Primary (nondense)    |  Secondary (dense)            |
 --------------------- ----------------------- -------------------------------
|  is nonkey          | Clustering (nondense) |  Secondary (dense/ nondense)  |
 --------------------- ----------------------- -------------------------------
```



