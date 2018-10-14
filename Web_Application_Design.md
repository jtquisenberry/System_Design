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
* A hardware or software appliance that routes a request to one of several request nodes (web servers).
* May route on the basis of.
  * Random
  * Round-robin
  * Which node is least busy.
  * Sticky - the user continues to use the same node throughout the session. 
    * Preserves session data.
* Session Data: If a client may be routed to different nodes, there is the challeng of storing session data. This can be overcome using:
  * Cookies
  * Browser caches.

## CDN
* Replicate data in different geographic locations. 
* The replicated data may consist entirely of caches.

## Proxy Servers
* Often include caches. 
  * If so, it is best to check the cache first due to the speed of accessing cache data in memory. 
* Collapsed Forwarding (Requests): - The process of grouping identical or similar requests together, receiving a response, and then submitting the response to each client.
* Collapsing Forwarding (Location of Data in Data Store): The process of grouping requests based on the location on disk or in a database of the data.

## Horizontal Scaling of Web Servers (Request Layer)
* Horizontal Scaling: Adding additional machines.
* Vertical Scaling: Adding additional resources to a single machine. 
* Adding more web servers is possible with a "shared-nothing" strategy. 
* Requires exactly the same code across servers.
* Can be spun up quickly with Kubernetes.

## Caching - Reading
* Generally: Stores the results of the most recent requests in memory.
  * Python calls this "request caching".
  * C# calls this "response caching". 
* Local Cache: Each request node (web server) stores a cache containing only the responses is processed.
* Global Cache: A separate server stores a cache of all respondes processed by any node.
  * Use a global cache to prevent cache misses that may occur with a local cache if the client is routed to different nodes for each request. 
  * Usually in a system that uses this architecture, if a response is not found in a cache, the cache is responsible for querying the data layer. However, it is also possible for the request layer to query the data layer.
  * If the global cache goes down, then all requests must be submitted to the data store. Otherwise, the entire system goes down.
* Distributed Cache: Cache is spread across request nodes.
  * If one node goes down, the worst case is that the node queries the database.
* Eviction: The removal of cached responses when the cache becomes full.
  * Often accomplished with Least Recently Used strategy.

## Queues - Writing
* Asynchronous handling of write requests. 
* Requests are submitted to a queue, and any worker agent can start work on a request.
* Queue initially responds only that the request has been received.
* Can retry failed requests.
* May give the illusion of system availability. 

## Data Store Selection
* SQL: Common scaling techniques.
  * Best with relational data with many joins.
* NoSQL: Very low latency.
  * Best when there are not many joins.
  * Good if the schema must be changed frequently. 
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

## Indexing
* A mechanism for identifying the locatio of a resource.
  * Which drive or server contains a file?
  * Which page of a book contains searched text?
* Not just a concept for SQL.
