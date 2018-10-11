# jqSystems



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



# Web Applications.
1. Traditional load balancing.
2. Require exactly the same code across servers.


## Deployment of Multiple Applicatin Servers
* Kubernetes automatically spin up. 
