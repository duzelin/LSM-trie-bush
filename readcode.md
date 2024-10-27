
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