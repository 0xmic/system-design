# Latency and Throughput  
Latency is the time between making a request and beginning to see a result. Some define latency as the time between making a request and the completion of the response, but this definition does not clearly distinguish the psychologically significant time spent waiting, not knowing whether a request has been accepted or understood. You will also see latency defined as the inverse of throughput, but this is not useful because latency would then give you the same information as throughput. Latency is measured in units of time, such as seconds.

Throughput is the number of items processed per unit time, such as bits transmitted per second, HTTP operations per day, or millions of instructions per second (MIPS). It is conventional to use the term “bandwidth” when referring to throughput in bits per second. Throughput is found by adding up the number of items and dividing by the sample interval. This calculation may produce correct but misleading results because it ignores variations in processing speed within the sample interval.

Although high throughput systems often have low latency, there is no causal link. Large disks tend to have better throughput but worse latency; the disk is physically bigger, so the arm has to seek longer to get to any particular place. The latency of packet network connections also tends to increase with throughput. As you approach your maximum throughput, there are simply more or larger packets to put on the wire, so a packet will have to wait longer for an opening, increasing latency. This is especially true for Ethernet, which allows packets to collide and simply retransmits them if there is a collision, hoping that it retransmitted them into an open slot. It seems obvious that increasing throughput capacity will decrease latency for packet switched networks. However, while latency due to traffic congestion can be reduced, increasing bandwidth will not help in cases in which the latency is imposed by routers or sheer physical distance.

## Prerequisites  
* Disk
* Memory

## Key Terms  
### Latency  
The time it takes for a certain operation to complete in a system. Most often this measure is a time duration, like milliseconds or seconds. You should know these orders of magnitude:  
* __Reading 1 MB from RAM__: 250 microseconds
* __Reading 1 MB from SSD__: 1000 microseconds
* __Transfer 1 MB over Network__: 10 milliseconds
* __Reading 1 MB from HDD__: 20 milliseconds
* __Inter-Continental Round Trip (1 packet)__: 150 milliseconds

### Throughput  
The number of operations that a system can handle properly per time unit. For instance, the throughput of a server can often be measured in requests per seoncd (RPS or QPS).