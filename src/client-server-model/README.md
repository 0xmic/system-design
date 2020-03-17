# Client Server Model  


## Key Terms  
### Client  
A machine or process that requiests data or service from a server.  
Note that a single machine or piece of software can be oth a client and a server at the same time. For instance, a single machine could act as a server for end users and as a client for a database.  

### Server  
A machine or process that provides data or service for a client, usually by listening for incoming netowrk calls.  
Note that a single machine or piece of software can be both a client and a server at the same time. For isntance, a single machine could act as a server for end users and as a client for a database.  

### Client-Server Model  
The paradigm by which modern systems are designed, which consists of clients requesting data or service from servers and servers providing data or service to clients.  

### IP Address  
An address given to each machine connected to the public internet. IPv4 addresses consist of four numbers separated by dots: __a.b.c.d__ where all four numbers are between 0 and 255. Special values include:  
* __127.0.0.1__: Your own local machine. Also referred to as __localhost__.
* __192.168.x.y__: Your private network. For instance, your machine and all machines on your private wifi network will usually have the __192.169__ prefix.  

### DNS  
Short for Domain Name System, it describes the entities and protocols involved in the translation from domain names to IP Addresses. Typically, machines make a DNS query to a well known entity which is responsible for returning the IP address (or multiple ones) of the requestsed domain name in the reponse.
