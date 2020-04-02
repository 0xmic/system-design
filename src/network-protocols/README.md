# Network Protocols  
__Network Protocols__ are a set of guidelines governing the exchange of information in a simple, dependable and secure way. Network protocols are formal standards and policies comprised of rules, methodology, and configurations that define communication between two or more device over a network. To effectively send and receive information, devices on the two sides of a communication exchange must follow protocols.

Network protocols are used in standardized architectures that collectively transmit data from one person to another across the globe. The two most common architectures are the OSI (Open Systems Interconnection) Model, and the TCP/IP (Transmission Control Protocol/Internet Protocol) Model. 

## TCP/IP
The TCP/IP model is a concise version of the OSI model. It contains four layers, unlike seven layers in the OSI model. The layers are:
1. Process/Application Layer
2. Host-to-Host/Transport Layer
3. Internet Layer
4. Network Access/Link Layer

The diagrammatic comparison of the TCP/IP and OSI model is as follows:
![TCP/IP & OSI Model Comparison](./TCP:IP_OSI.png)

### 1. Network Access/Link Layer
This layer corresponds to the combination of Data Link Layer and Physical Layer of the OSI model. It looks out for hardware addressing and the protocols present in this layer allows for the physical transmission of data.

### 2. Internet Layer
This layer parallels the functions of OSI’s Network layer. It defines the protocols which are responsible for logical transmission of data over the entire network. The main protocols residing at this layer is the Internet Protocol (IP).

IP is responsible for delivering packets from the source host to the destination host by looking at the IP addresses in the packet headers. IP has 2 versions: IPv4 and IPv6. IPv4 is the one that most of the websites are using currently. But IPv6 is growing as the number of IPv4 addresses are limited in number when compared to the number of users.

### 3. Host-to-Host/Transport Layer
This layer is analogous to the transport layer of the OSI model. It is responsible for end-to-end communication and error-free delivery of data. It shields the upper-layer applications from the complexities of data. The two main protocols present in this layer are:

* Transmission Control Protocol (TCP) – known to provide reliable and error-free communication between end systems. It performs sequencing and segmentation of data. It also has acknowledgment feature and controls the flow of the data through flow control mechanism. It is a very effective protocol but has a lot of overhead due to such features. Increased overhead leads to increased cost.
* User Datagram Protocol (UDP) – On the other hand does not provide any such features. It is the go-to protocol if your application does not require reliable transport as it is very cost-effective. Unlike TCP, which is connection-oriented protocol, UDP is connectionless.

### 4. Application Layer
This layer performs the functions of top three layers of the OSI model: Application, Presentation and Session Layer. It is responsible for node-to-node communication and controls user-interface specifications. Some of the protocols present in this layer are: HTTP, HTTPS, SSH, SMTP, DNS. 

* HTTP and HTTPS – HTTP stands for Hypertext transfer protocol. It is used by the World Wide Web to manage communications between web browsers and servers. HTTPS stands for HTTP-Secure. It is a combination of HTTP with SSL(Secure Socket Layer). It is efficient in cases where the browser need to fill out forms, sign in, authenticate and carry out bank transactions.
* SSH – SSH stands for Secure Shell. It is a terminal emulations software similar to Telnet. The reason SSH is more preferred is because of its ability to maintain the encrypted connection. It sets up a secure session over a TCP/IP connection.

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
* an __IP header__, which contains the source and destination addresses as well as other information related to the network
* a __payload__, which is just the data being sent over the network
