# Web Application Design with Distributed Systems

## References
* http://www.aosabook.org/en/distsys.html

## Considerations
* Speed - low latency
* Reliability
* Availability
* Manageability
* Scalability
* Cost


## Load Balancers
* Direct a request to one of several request nodes (web servers).
* May direct to a server based on
 * Which one is least busy.
 * Random
 * Sticky - the user continues to use the same node throughout the session. 
* Session Data: If a client may be routed to different nodes, there is the challeng of storing session data. This can be overcome by:
 * Cookies
 * Browser caches.

## CDN
* Replicate data in different geographic locations. 
* The replicated data may consist entirely of caches.

## Proxy Servers
* Often include caches. If so, it is best due check the cache first due to the speed of accessing cache data in memory. 
* 













# SQL

## Data Store
* SQL: Common scaling techniques.
* NoSQL: Very low latency.
* In-memory cache, such as Redis, very fast.

## SQL Farm
* Write to one.
* Perform transaction replication.
* Read from many.

## Hardware
* Cost verus speed of memory and disk.
* Alternatives to memory.
 * Caches
 * Proxies
 * Indexes 
 * Load balancers

## What is sharding?

Can have servers that serve only one subset of clients.




# Web Applications
Also called a request layer.

## Configuration
* Horizontally scalable because "share nothing".
* Traditional load balancing.
* Require exactly the same code across servers.

## Caching
* Local Cache: Stores results of most recent request. This prevents re-querying data from SQL.
* Global Cache: If the load balancer sends requests to random nodes, there may be cache misses. Some cache contains the necessary response, but it does not happen to be the cache that received the latest request. Use a global cache in this casse.
* Global Cache: Usually put on its own server. It is responsible for eviction of least recently used results. 


## Deployment of Multiple Applicatin Servers
* Kubernetes automatically spin up. 
