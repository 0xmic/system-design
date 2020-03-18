# Hashing  

## Prerequisites  
* Hashing Function
* Load Balancer

## Key Terms  
### Consistent Hashing  
A type of hashing that minimizes the number o keys that need to be remapped when a hash table gets resized. It's often used by load balancers to distribute traffic to servers; it minimizes the number o requests that get forwarded to different servers when new servers are added or when existing servers are brought down.  

### Rendezvous Hashing  
A type of hashing also coined __highest random weight__ hashing. Allows for minimal re-distribution of mappings when a server goes down.  

## SHA  
Short for "Secure Hash Algorithms", the SHA is a collection of cryptographic hash functions used in the industry. These days, SHA-3 is a popular choice to use in a system.
