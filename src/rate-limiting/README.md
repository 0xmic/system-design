# Rate Limiting  
Rate limiting is used to control the amount of incoming and outgoing traffic to or from a network. For example, say you are using a particular service's API that is configured to allow 100 requests/minute. If the number of requests you make exceeds that limit, then an error will be triggered. The reasoning behing implementing rate limiting is to allow for a __better flow of data__ and to __increase security__ by mitigating attacks such as DDoS.

Rate limiting is also useful if a particular user on the network makes a mistake in their request, thus asking the server to retrieve tons of information that may overload the network for everyone. With rate limiting in place, however, these types of errors or attacks are much more manageable.

__Types of rate limits:__
* User rate limiting: Associates the number of requests a user is making to an API key or IP. 
* Geographic rate limiting: Rates set for particular regions and particular time periods.
* Server rate limiting: If a developer defines a certain server to handle certain aspects of the application, rate limits can be imposed on individual servers.

## Prerequisites  
* Availability
* Key-Value Store

## Key Terms  
### Rate Limiting  
The act of limiting the number of requests sent to or from a system. Rate limiting is most often used to limit the number of incoming requests in order to prevent __DoS attacks__ and can be enforced at the IP-address level, at the user-account level, or at the region level, for example. Rate limiting can also be implemented in tiers; for instance, a type of network request could be limited to 1 per second, 5 per 10 seconds, and 10 per minute.  

### DoS Attack  
Short for "denial-of-service attack", a DoS attack is an attack in which a malicious user tries to bring down or damage a system in order to render it unavailable to users. Much of the time, it consists of flooding it with traffic. Some DoS attacks are easily preventable with rate limiting, while others can be far trickier to defend against. 

### DDoS Attack  
Short for "distributed denial-of-service attack", a DDoS attack is a DoS attack in which the traffic flooding the target system comes from many different sources (like thousands of machines), making it much harder to defend against.  

### Redis ☆  
An in-memory key-value store. Does offer some persistent storage options but is typically used as a really fast, best-effort caching solution. Redis is also often used to implement __rate limiting__.  
Website: [https://redis.io/](https://redis.io/)