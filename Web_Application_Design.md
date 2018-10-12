# jqSystems

## References
* http://www.aosabook.org/en/distsys.html

## Considerations
* Speed - low latency
* Reliability
* Fault tolerance
* Storage
<br>


# API


## API Domain Modeling Examples
1. Refer to the object being acted on: `users`, `statuses`, `friendships`.
2. If GET, the state what is being retrieved `list`, `ids`, `id:1`
3. If POST, state the operation. `create`, `destroy`, `update`.
4. Use a common interface - singular or plural nounds. Consistent verbs.
<br> Examples from Twitter: https://developer.twitter.com/en/docs/api-reference-index.html


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
