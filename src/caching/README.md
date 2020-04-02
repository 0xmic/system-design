# Caching  
Caching is the process of storing data in a location that is different from the original location in order to retrieve that data faster. Caching can be found at the client, server and/or database level. You can also have caches inbetween servers. Caching can even occur at the hardware level.

Caching is helpful when performing many network requests. By caching results of network requests, if a client has a re-request that data, it can find it at a location closer than the database. Caching is also helpful when computing computationally long operations.

If there are multiple clients making requests to a server, you can introduce caching in order to reduce the amount of times you read from the database as to not overload it. 

Caches can also store posts made to a server. Right-through caches post data at both the server and database level, overwriting what is being stored at both levels. Right-through caches are useful for data consistency, but take additional time to write to multiple sources. Right-back caches have servers update and leave databases alone. The system will then asynchronously update the database. The downside of right-back caching is that if a cache goes down before a database is updated, data may get lost. 

Caches can become 'stale' if they haven't been updated with the most consistent data. Staleness is more acceptable in some instances than others - i.e. YouTube video viewcount vs comment posts. 

In general, if the data you are dealing with is immutable, caching is great. However, if data is mutable, then things are tricker as data is stored in more than one place. Caching is useful when storing data that is immutable, there is only a single entity reading or writing data, if you don't care about consistency and staleness of data, or if you can design a system to clear stale data in the cache.

Caches don't have infinite space, which necessitates the needs for eviction policies to get rid of old data in caches. Popular policies are "Least Recently Used" (LRU), "Least Frequently Used" (LFU), "Last In First Out" (LIFO), or "First In First Out" (FIFO).

## Prerequisites  
* Latency
* Throughput
* Memory

## Key Terms  
### Cache  
A piece of hardware of software that stores data, typically meant to retrieve that data faster than otherwise.  

Caches are often used to store responses to network requests as well as results of computationally-long operations.  

Note that data in a cache can become __stale__ if the main source of truth for that data (i.e., the main database behind the cache) gets updated and the cache doesn't.  

### Cache Hit  
When requested data is found in a cache.  

### Cache Miss  
When requested data could have been found in a cache but isn't. This is typically used to refer to a negative consequence of a system failure or of a poor design choice. For example:  

_If a server goes down, our load balancers will have to forward requests to a new server, which will result in cache misses._

### Cache Eviction Policy  
The policy by which values get evicted or removed from a cache. Popular cache eviction policies include __LRU__ (least-recently used), __FIFO__ (first in first out), and __LFU__ (least-frequently used).  

### Content Delivery Network  
A __CDN__ is a third-party service that acts like a cache for your servers. Sometimes, web applications can be slow for users in a particular region if your servers are located only in another region. A CDN has servers all around the world, meaning that the latency to a CDN's servers will almost always be far better than the latency to your servers. A CDN's servers are often referred to as __PoPs__ (Points of Presence). Two of the most popular CDN's are __Cloudflare__ and __Google Cloud CDN__.