# Replication And Sharding  
### Replication
When designing a performant system, it is important to ensure that the database layer is performant.

In a system with only one database, if that database goes down then the system has no access to its data. This is where replication comes in. By having data replicated across multiple databases, the system is more tolerant to individual database failures. 

Replication can also help to reduce latency but partitioning databases across different geographical jurisdictions.

There are many different ways to architect replication amongst databases - notably with a Master-Master 

__Master-Slave Replication__
The master serves reads and writes, replicating writes to one or more slaves, which serve only reads. Slaves can also replicate to additional slaves in a tree-like fashion. If the master goes offline, the system can continue to operate in read-only mode until a slave is promoted to a master or a new master is provisioned.

![Master-Slave](./master-slave.png)

__Master-Master Replication__
Both masters serve reads and writes and coordinate with each other on writes. If either master goes down, the system can continue to operate with both reads and writes. 

![Master-Master](./master-master.png)

### Sharding
Sharding distributes data across different databases such that each database can only manage a subset of the data. Taking a users database as an example, as the number of users increases, more shards are added to the cluster.

![Sharding](./sharding.png)

Sharding results in less read and write traffic, less replication, and more cache hits. Index size is also reduced, which generally improves performance with faster queries. If one shard goes down, the other shards are still operational, although you'll want to add some form of replication to avoid data loss. There is no single central master seializing writes, allowing you to write in parallel with increased throughput.

## Prerequisites  
* Availability
* Latency
* Throughput
* Redundancy
* Databases
* Reverse Proxy

## Key Terms  
### Replication  
The act of duplicating  data from one database server to others. This is sometimes used to increase the redundancy of your system and tolerate regional failures for instance. Other times you can use replication to move data closer to your clients, thus decreasing the latency of accessing specific data.

### Sharding  
Sometimes called __data partitioning__, sharding is the act of splitting a database into two or more pieces called __shards__ and is typically done to increase the throughput of your database. Popular sharding strategies include:
* Sharding based on the client's region
* Sharding based on the type of data (e.g. user data gets stored in one shard, payments data gets stored in another shard)
* Sharding based on the hash of a column (only for structured data)

### Hot Spot  
When distributing a workload across a set of servers, that workload might be spread unevenly. This can happen if your __sharding key__ or your __hashing function__ are suboptimal, or if your workload is naturally skewed: some servers will receive a lot more traffic than others, thus creating a "hot spot".