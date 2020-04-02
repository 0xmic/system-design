# Availability  
Availability can be thought of as how resistent a system is to failure - if a server or database goes down. This can also be described as fault-tolerance. Most systems have an implied guarantee of availability. 

There are varying degrees of availability that are expected from different services. Airplane software is expected to be more available than a simple webpage. 

Availability is typically measured by the amount of time a system is up over a given year. 

Many service providers have SLAs - an agreement between a service provider and a customer - on a system's availability, amongst other things. 

Ensuring high levels of availability is difficult and comes with trade-offs with other attributes of a system. When designing systems, it is important to ask what parts of a system will require high availability, and what parts are okay to fail.

In order to make a system highly available, it is important to reduce single points of failure. This is done through redundancy of servers, databases, loadbalaners, etc. You can introduce redundancy into different parts of a system by simply adding more machines. Redundancy is passive when you have multiple components in a system running at the same time, and if at any point in time one component dies, the others are able to continue running. Active redundancy is when multiple machines are working together, typically with only one or few doing work. If the component doing work fails, another component will take over. 

## Prerequisites  
* Process
* Server
* Node/Instance/host

## Key Terms  
### Availability  
The odds of a particular server or service being up and running at any point in time, usually measured in percentages. A server that has 99% availability will be operational 99% of the time  (this would be described as having two __nines__ of availability).  

### High Availability  
Used to describe systems that have particularly high levels of availability, typically 5 nines or more; sometimes abbreviated "HA".  

### Nines  
Typically referes to percentages of uptime. For example, 5 nines of availability means an uptime of 99.999% of the time. Below are the downtimes expected per year depending on those 9s:  
```
- 99% (two 9s): 97 hours
- 99.9% (three 9s): 8.7 hours
- 99.99%: 52 minutes
- 99.999%: 5 minutes
``` 

### Redundancy  
The process of replicating parts of a system in an effort to make it more reliable.  

### SLA  
Short for "service-level agreement", an SLA is a collection of guarantees given to a customer by a service provider. SLAs typically make guarantees on a system's availability, amonst other things. SLAs are made up of one or multiple SLOs.  

### SLO  
Short for "service-level objective", an SLO is a guarantee given to a customer by a service provider. SLOs typically make guarantees on a system's availability, amonst other things. SLOs constitue an SLA.