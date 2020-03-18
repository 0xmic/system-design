# Caching  


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