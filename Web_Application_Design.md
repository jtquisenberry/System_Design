# Web Application Design with Distributed Systems

## References
* http://www.aosabook.org/en/distsys.html

## Considerations
* Performance (Speed - low latency)
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
* Collapsed forwarding. - The process of grouping identical or similar requests together, receiving a response, and then submitting the response to each client.
* Collapsing of spatially close data. The process of grouping requests for a resource based on geography. 

## Horizontal Scaling of Web Servers
* Horizontal Scaling: Adding additional machines.
* Vertical Scaling: Adding additional resources to a single machine. 
* Adding more web servers is possible with a "shared-nothing" strategy. 
* Requires exactly the same code across servers.
* Can be spun up quickly with Kubernetes.

## Caching
* Local Cache: Stores results of most recent request. This prevents re-querying data from SQL.
* Global Cache: If the load balancer sends requests to random nodes, there may be cache misses. Some cache contains the necessary response, but it does not happen to be the cache that received the latest request. Use a global cache in this casse.
* Global Cache: Usually put on its own server. It is responsible for eviction of least recently used results. 
* Global Cache: Usually in a system that uses this architecture, if a response is not found in a cache, the cache is responsible for querying the data layer. It is also possible for the request layer to query the data layer.
* Global Cache: can reduce availability.
* In Python, this is called "request caching". In C#, it is called "response caching".
* Distributed cache: Cache is spread across request nodes.
* Distributed cache: If one node goes down, the worst case is that the node queries the database.

## Data Store Selection
* SQL: Common scaling techniques.
* NoSQL: Very low latency.
* In-memory cache, such as Redis, very fast.

## SQL Farm
* Write to one.
* Perform transaction replication.
* Read from many.

## Sharding
* The horizontal partition of data storage, i.e. storing a single dataset across servers.
* Can have servers that serve only one subset of clients.

## Partitioning
* The horizontal storage of data across servers. 
* It might be that this term is more apt in the case of file servers, rather than SQL servers.
* Determination of which server a file is on can be accomplished using an index (ID, Server pair). 
* It can also be accomplished using a file naming convention where the name of the file specifies the containing server.
* SAN




