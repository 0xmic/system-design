# Proxies  
A (forward) proxy server acts as a gateway between a client and a server. It’s an intermediary server separating end users from the websites they browse. Proxy servers provide varying levels of functionality, security, and privacy depending on your use case, needs, or company policy.

If you’re using a (forward) proxy server, internet traffic flows through the proxy server on its way to the address you requested. The request then comes back through that same proxy server (there are exceptions to this rule), and then the proxy server forwards the data received from the website to you.

Modern proxy servers do much more than forwarding web requests, all in the name of data security and network performance. Proxy servers act as a firewall and web filter, provide shared network connections, and cache data to speed up common requests. A good proxy server keeps users and the internal network protected from the bad stuff that lives out in the wild internet. Lastly, proxy servers can provide a high level of privacy.

While forward proxies act on behalf of a client, reverse proxies act on behalf of a server. If a client sends a request to a server using a reverse proxy, the reverse proxy will actually go to the reverse proxy (unbeknownst to the client). The reverse proxy will forward the request to the server, which will return the response to the reverse proxy and back to the client. Clients are unaware if they are interacting with a server behind a reverse proxy.

Reverse proxies are useful to filter out requests that a server should ignore. Reverse proxies can take care of logging metrics, or caching different data. Reverse proxies can also act as load balancers - servers that distribute request load between multiple servers. 

### How Does a Proxy Server Operate?
A proxy server is basically a computer on the internet with its own IP address that your computer knows. When you send a web request, your request goes to the proxy server first. The proxy server then makes your web request on your behalf, collects the response from the web server, and forwards you the web page data so you can see the page in your browser.

When the proxy server forwards your web requests, it can make changes to the data you send and still get you the information that you expect to see. A proxy server can change your IP address, so the web server doesn’t know exactly where you are in the world. It can encrypt your data, so your data is unreadable in transit. And lastly, a proxy server can block access to certain web pages, based on IP address.

## Prerequisites  
* Client
* Server

## Key Terms  
### Forward Proxy  
A server that sits between a client and servers and acts on behalf of the client, typically used to mask the client's identity (IP address). Note that forward proxies are often referred to as just proxies.  

### Reverse Proxy  
A server that sits between clients and servers and acts on behalf of the servers, typically used for logging, load balancing, or caching.  

### Nginx ☆  
Pronounced "engine X" - Not "N jinx", Nginx is a very popular webserver that's often used as a __reverse proxy__ and __load balancer__. Website: [https://www.nginx.com/](https://www.nginx.com/)
