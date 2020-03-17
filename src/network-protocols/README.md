# Network Protocols  


## Prerequisites  
* Client
* Server
* IP Address

## Key Terms  
### IP  
Stands for __Internet Protocol__. This network protocol outlines how almost all machine-to-machine communications should happen in the world. Other protocols like __TCP__, __UDP__ and __HTTP__ are built on top of IP.  

### TCP  
Network protocol build on top of the Internet Protocol (IP). Allows for ordered, reliable data delivery between machines over the public internet by creating a __connection__.  

TCP is usually implemented in the kernel, which exposes __sockets__ to applications that they can use to stream data through an open connection.  

### HTTP  
HyperText Transfer Protocol, very common network protocol implemented on top of TCP. Clients make HTTP requests, and servers respond with a response. 
 
Requests typically have the following schema:  
```
host: string (example: algoexpert.io)
port: integer (example: 80 or 443)
method: string (example: GET, PUT, POST, DELETE, OPTIONS or PATCH)
headers: pair list (example: "Content-Type" => "application/json")
body: opaque sequence of bytes
```
Responses typically have the follinwg schema:  
```
status code: integer (example: 200, 401)
headers: pair list (example: "Content-Length" => 1238)
body: opaque sequence of bytes
```

### IP Packet  
Sometimes more brodly referred to as just a (network) __packet__, an IP packet is effectively the smallest unit used to describe data being sent over __IP__, aside from bytes. An IP packet consists of:  
* an __IP header__, which contains the source and destination addresses as wellas other information related to the network
* a __payload__, which is just the data being sent over the network
