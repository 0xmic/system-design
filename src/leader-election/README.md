# Leader Election  
A __distributed algorithm__ is an algorithm that runs on a distributed system - a collection of independent computers that do not share their memory. Each processor has its own memory and they communicate via communication networks. Communication in networks is implemented in a process on one machine communicating with a process on another machine. Many algorithms used in distributed systems require a coordinator that performs functions needed by other processes in the system. __Election algorithms__ are designed to choose a coordinator.

### Election Algorithms:
Election algorithms, or __consensus algorithms__, choose a process from a group of processors to act as a coordinator. If the coordinator process crashes due to some reason, then a new coordinator is elected on another processor. Election algorithms basically determine where a new copy of the coordinator should be restarted.

Election algorithms assume that every active process in the system has a unique priority number. The process with highest priority will be chosen as a new coordinator. Hence, when a coordinator fails, this algorithm elects that active process which has the highest priority number. Then, this number is sent to every active process in the distrubted system.

## Prerequisites  
* Availability
* High Availability
* Redundancy
* Strong Consistency
* Eventual Consistency

## Key Terms  
### Leader Election  
The process by which nodes in a cluster (for instance, servers in a set of servers) elect a so-called "leader" amonst them, responsible for the primary operations of the service that these nodes support. When correctly implemented, leader election guarantees that all nodes in the cluster know which one is the leader at any given time and can elect a new leader if the leader dies for whatever reason.

### Consensus Algorithm  
A type of complex family of algorithms used to have multiple entities agree on a single data value, like who the "leader" is amongst a group of machines. Two popular consensus algorithms are __Paxos__ and __Raft__.  

### Paxos & Raft  
Two consensus algorithms that, when implemented correctly, allow for the synchronization of certain operations, even in a distributed setting.  

### Etcd ☆  
Etcd is a stringly consistent and highly available key-value store that's often used to implement leader election in a system. Etcd impelents Raft as a consensus algorithm.  
Website: [https://etcd.io/](https://etcd.io/)

### ZooKeeper ☆  
ZooKeeper is a strongly consistent, highly available key-value store. It's often used to store important configuration or to perform leader election.  
Website: [https://zookeeper.apache.org/](https://zookeeper.apache.org/)