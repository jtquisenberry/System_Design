# jqSystems
## References
* https://www.giantstride.gr/sql-indexing-part2/




# Indexes
* Improves speed of reads.
* Decreases speed of INSERT, UPDATE, DELETE, MERGE.

## Storage
* B-Tree Structure
* Storage in root, intermediate, and leaf nodes.
* Storage in 8K data pages.

## Clustered vs. Unclustered
* Clustered: Changes the order in which rows are physically stored. Contains the data pages of the table.
 * One clustered index per table.
* Unclustered: Contains only a pointer back to the rows.
 * For tables that have a clustered index, the unclustered index contains the clustered index keys. 
 * If lookup is too costly, engine resorts to a scan.
 * Can be slower because key lookups are done on the clustered index. This does not apply to covering indexes?

## Covering Index
* An index that covers all of the fields needed to resolve a query.


## Scan vs.Seek
* Scan looks through all records of the table -slow.
* Seek: 
