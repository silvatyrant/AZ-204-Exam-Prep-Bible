# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
Azure Cache (for Redis)
-----------------------
### General

### Tech Tips

### High Availability / Scalability
* [Best practices](https://docs.microsoft.com/en-us/azure/architecture/checklist/resiliency-per-service#azure-cache-for-redis)
  * [Configure Geo-replication](https://docs.microsoft.com/en-us/azure/redis-cache/cache-how-to-geo-replication).
    * Two Premium-tier Azure Cache for Redis instances.
    * Primary cache is write and replicates to secondary which is read-only.
  * [Configure data persistence](https://docs.microsoft.com/en-us/azure/redis-cache/cache-how-to-premium-persistence).
    * Persist data stored in the cache.
    * Allows for snapshots, which can be loaded in the case of hardware failure.

### Notable Limits**
|Resource												|Limit  |
|-------------------------------------------------------|-------|
|Cache size												|1.2 TB |
|Databases												|64     |
|Maximum connected clients								|40,000 |
|Azure Cache for Redis replicas, for high availability	|3      |
|Shards in a premium cache with clustering				|10		|


### Labs

```
- configure cache and expiration policies for Azure Redis Cache
- implement secure and optimized application cache patterns 
- including data sizing,
connections, encryption, and expiration
```

### Related Services