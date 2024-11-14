
## Data Structure

### Tree of Virtual Container
Virtual Container (Container) -> MetaTable[20], Bloom Container

### Table 
active table

### Meta Table

### What's the use of ContainerMap?
* container unit size equals to the HTable size 

### What's the relationship between the MetaTable and Table?

### What's the structure of the barrel and Meta Index?
rid? min?

### What's the purpose of the Bloom Table and Bloom Container
BTable and BContainer should be mutually exclusive.
BTable is kept in memory.
BContainer is stored on disk.

## Dump

### active table dumper
* shift the active table
* notify writers about the new available active table
* check the containermap usage
* build bloom table
* dump table **in-detail**
    * aquire an unique mtid
    * allocate an offset from container map
    * dump barrels (buckets) to the container map's file at the offset
        *
    * return mtid
* dump metatable

### meta table dumper

### compaction dump

compaction thread -> compaction main()
1. compaction_initial()
    * allocate arena
    * 
2. compaction_feed_all()
    multiple threads read barrels to the table buffer
    file -> arena (rawitem) -> table's mempool (item) (new table only records reference of items of each bucket)
3. compaction_build_bt_all()
4. compaction_dump_and_bc_all()
    balance buckets
5. compaction_update_vc()
6. compaction_free_old()

recursive compaction()
* disable compaction for last level
* [Modified] detach