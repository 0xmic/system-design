# Load Balancers  


## Prerequisites  
* Reverse Proxy

## Key Terms  
### Load Balancer  
A type of __reverse proxy__ that distributes traffic across servers. Load balancers can be found in many parts of a system, from the DNS layer all the way to the database layer.  

### Server-Selection Strategy  
How a __load balancer__ chooses servers when distributing traffic amongst multiple servers. Commonly used strategies include round-robin, random selection, performance-based selection (choosing the server with the best performance metrics, like the fasteset response time or the least amount of traffic), and IP-based routing.

### Hot Spot  
When distributing a workload across a set of servers, that workload might be spread unevenly. This can happen if your __sharding key__ or you __hashing function__ are suboptimal, or if your workload is naturally skewed: some servers will receive a lot more traffic than others, thus creating a "hot spot".  

### Nginx ☆  
Pronounced "engine X" - not "N jinx", Nginx is a very popular webserver that's often used as a __reverse proxy__ and __load balancer__. Website: [http://www.nginx.com/](https://www.nginx.com/)