# ElastiCache

## Overview

ElastiCache is Amazon's offering for managed Redis or Memcached.

Caches are in-memory dbs with high perf and low latency. They allow quick access to data without having to reach the DB disk.

This helps:

- Latency
- Reduce load on DB resources
- Makes application stateless

> AWS will take care of maintenance, patching, optimisations, monitoring, failure etc for you

## Architecture

Apps query the cache, but if it misses, then it will read from DB.

Caches should have an invalidation strategy

![cache architecture](assets/elasticache.png)

## Use session store

Another good use case is for a session store for a user's session:

![cache architecture](assets/session-store.png)

## Elasticcache security

- ElastiCache support IAM Auth for Redis
- IAM is only used for API level access, though
- There is also Redis auth, which allows you to create a user/pw combination for Redis cluster and is an extra layer of security
- Memcached supports SASL based auth

## ElastiCache patterns

1. **LazyLoading**: this involves writing all data to cache for quick access. Data can quickly become stale. 
1. **Write Throgh**: When data is written to the the db, also write to cache  
1. **Session store**: Store temporary data in cache (such as session info)

## Redis use case

> Important for the exam

- Gaming leaderboards are computationally complex
- **Redis sorted sets** guarantees uniqueness and element ordering
- Each time an element is added, it's ranked in realtime, then added in correct order:


![](assets/redis-sorted-sets.png)
