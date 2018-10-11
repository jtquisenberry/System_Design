# jqSystems
## References
* https://www.giantstride.gr/sql-indexing-part2/




# Indexes

## Storage
* B-Tree Structure
* Storage in root, intermediate, and leaf nodes.
* Storage in 8K data pages.

## Clustered vs. Unclustered
* Clustered: Changes the order in which rows are physically stored. 
 * One clustered index per table.
* Unclustered: Contains only a pointer back to the rows.
<br> For tables that have a clustered index, the unclustered index contains the clustered index keys. 

## Covering Index
* An index that covers all of the fields needed to resolve a query.


## Scan vs.Seek
* Scan looks through all records of the table -slow.
* Seek: 
