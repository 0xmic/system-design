# Key-Value Stores  


## Prerequisites  
* Relational Database
* Non-Relational Database

## Key Terms  
### Key-Value Stores  
A Key-Value Store is a flexible NoSQL database that's often used for caching and dynamic configuration. Popular options include DynamoDB, Etcd, Redis, and ZooKeeper.

### Etcd ☆  
Etcd is a strongly consistent and highly available key-value store that's often used to implement leader election in a system.  
Website: [https://etcd.io/](https://etcd.io/)

### Redis ☆  
An in-memory key-value store. Does offer some persistent storage options but is typically used as a really fast, best-effort caching solution. Redis is also often used to implement __rate limiting__.  
Website: [https://redis.io/](https://redis.io/)

### ZooKeeper ☆  
ZooKeeper is a strongly consistent, highly available key-value store. It's often used to store important configuration or to perform leader election.  
Website: [https://zookeeper.apache.org/](https://zookeeper.apache.org/)
