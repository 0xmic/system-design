# Security And HTTPS  
**What is HTTPS?**  
Hypertext transfer protocol secure (HTTPS) is the secure version of HTTP, which is the primary protocol used to send data between a web browser and a website. HTTPS is encrypted in order to increase security of data transfer. This is particularly important when users transmit sensitive data, such as by logging into a bank account, email service, or health insurance provider.  

Any website, especially those that require login credentials, should use HTTPS. In modern web browsers such as Chrome, websites that do not use HTTPS are marked differently than those that are.  

**How does HTTPS work?**  
HTTPS uses an encryption protocol to encrypt communications. The protocol is called Transport Layer Security (TLS), although formerly it was known as Secure Sockets Layer (SSL). This protocol secures communications by using what’s known as an asymmetric public key infrastructure. This type of security system uses two different keys to encrypt communications between two parties:  
* The private key - this key is controlled by the owner of a website and it’s kept, as the reader may have speculated, private. This key lives on a web server and is used to decrypt information encrypted by the public key.  
* The public key - this key is available to everyone who wants to interact with the server in a way that’s secure. Information that’s encrypted by the public key can only be decrypted by the private key.  

**Why is HTTPS important?**  
HTTPS prevents websites from having their information broadcast in a way that’s easily viewed by anyone snooping on the network. When information is sent over regular HTTP, the information is broken into packets of data that can be easily “sniffed” using free software. This makes communication over the an unsecure medium, such as public Wi-Fi, highly vulnerable to interception. In fact, all communications that occur over HTTP occur in plain text, making them highly accessible to anyone with the correct tools, and vulnerable to on-path attacks.  

**Before encryption:**  
```
This is a string of text that is completely readable
```

**After encryption:**  
```

ITM0IRyiEhVpa6VnKyExMiEgNveroyWBPlgGyfkflYjDaaFf/Kn3bo3OfghBPDWo6AfSHlNtL8N7ITEwIXc1gU5X73xMsJormzzXlwOyrCs+9XCPk63Y+z0=
```
In websites without HTTPS, it is possible for Internet service providers (ISPs) or other intermediaries to inject content into webpages without the approval of the website owner. This commonly takes the form of advertising, where an ISP looking to increase revenue injects paid advertising into the webpages of their customers. Unsurprisingly, when this occurs, the profits for the advertisements and the quality control of those advertisements are in no way shared with the website owner. HTTPS eliminates the ability of unmoderated third parties to inject advertising into web content.  

![Third Party Content](./third-party-content.png)

**How is HTTPS diffrent from HTTP?**  
Technically speaking, HTTPS is not a separate protocol from HTTP. It is simply using TLS/SSL encryption over the HTTP protocol. HTTPS occurs based upon the transmission of TLS/SSL certificates, which verify that a particular provider is who they say they are.  

When a user connects to a webpage, the webpage will send over its SSL certificate which contains the public key necessary to start the secure session. The two computers, the client and the server, then go through a process called an SSL/TLS handshake, which is a series of back-and-forth communications used to establish a secure connection.  

**How does a website start using HTTPS?**  
Many website hosting providers and other services will offer TLS/SSL certificates for a fee. These certificates will be often be shared amongst many customers. More expensive certificates are available which can be individually registered to particular web properties.  

## Prerequisites  
* Client  
* Server  
* IP Packet  
* HTTP  

## Key Terms  
### Man-In-The-Middle Attack  
An attack in which the attacker intercepts a line of communication that is thought to be private by its two communicating parties.  

If a malicious actor intercepted and mutated an IP packet on its way from a client to a server, that would be a man-in-the-middle attack.  

MITM attacks are the primary threat that encryption and HTTPS aim to defend aginst.  

### Symmetric Encryption  
A type of encryption that relies on only a single key to both encrypt and decrypt data. The key must be known to all parties involved in communication and must therefore typically be shared between the parties at one point or another.  

Symmetric-key algorithms tend to be faster than their asymmetric counterparts.  

The most widely used symmetric-key algorithms are part of the Advanced Encryption Standard (__AES__).  

### Asymmetric Encryption  
Also knwon as public-key encryption, asymmetric encryption relies on two keys - a public key and a private key - to encrypt and decrypt data. The keys are generated using cryptographic algorithms and are mathematically connected such that data encrypted with the public key can only be decrypted with the private key.  

While the private key must be kept secure to maintain the fidelity of this encryption paradigm, the public key can be openly shared.  

Asymmetric-key algorithms tend to be slower than their symmetric counterparts.  

### AES  
Stands for __Advanced Encryption Standard__. AES is a widely used encryption standard that has three symmetric-key algorithms (AES-128, AES-192, and AES-256).  
Of note, AES is considered to be the "gold standard" in encryption and is even used by the U.S. National Security Agency to encrypt top secret information.  

### HTTPS  
The **H**yper**T**ext **T**ransfer **P**rotocol **S**ecure is an extension of **HTTP** that's used for secure communication online. It requires servers to have trusted certificates (usually **SSL certificates**) and uses the Transport Layer Security (**TLS**), a security protocol built on top of **TCP**, to encrypt data communicted between a client and a server.  

## TLS  
The **T**ransport **L**ayer **S**ecurity protocol over which **HTTP** runs in order to achieve secure communication online. "HTTP over TLS" is also known as **HTTPS**.  

### SSL Certificate  
A digital certificate granted to a server by a **certificate authority**. Contins the server's public key, to be used as part of the **TLS handshake** process in an **HTTPS** connection.  

An SSL certificate effectively confirms that a public key belongs to the server claiming it belongs to them. SSL certificates are a crucial defense against **man-in-the-middle attacks**.  

### Certificate Authority  
A trusted entity that signs digital certificates - namely, SSL certificates that are relied on in **HTTPS** connections.  

### TLS Handshake  
The process through which a client and a server communicating over **HTTPS** exchange encryption-related information and establish a secure communication. The typical steps in a TLS handshake are roughly as follows:  
* The client sends a **client hello** - a string of random bytes - to the server.  
* The server responds with a **server hello** - another string of random bytes - as well as its **SSL certificate**, which contains its **public key**.  