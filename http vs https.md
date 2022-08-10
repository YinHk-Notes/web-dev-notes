## Http vs Https

### Why is HTTP not secure? | HTTP vs. HTTPS

HTTP requests and responses are sent in plaintext, which means that anyone can read them. ***HTTPS corrects this problem by using TLS/SSL encryption.***

### *HTTP vs. HTTPS: What are the differences?

[***HTTPS](https://www.cloudflare.com/learning/ssl/what-is-https/) is [HTTP](https://www.cloudflare.com/learning/ddos/glossary/hypertext-transfer-protocol-http/) with [encryption](https://www.cloudflare.com/learning/ssl/what-is-encryption/).*** The only difference between the two protocols is that **HTTPS uses [TLS](https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/) ([SSL](https://www.cloudflare.com/learning/ssl/what-is-ssl/)) to encrypt normal HTTP requests and responses. As a result, HTTPS is far more secure than HTTP.** A website that uses HTTP has http:// in its URL, while a website that uses HTTPS has https://.

[](https://www.cloudflare.com/zh-tw/learning/ssl/why-is-http-not-secure/)

**What is HTTPS?**

The S in HTTPS stands for "**secure**." HTTPS uses TLS (or SSL) to encrypt HTTP requests and responses, so in the example above, instead of the text, an attacker would see a bunch of seemingly random characters.

**What is Transport Layer Security (TLS)?**

Transport Layer Security, or TLS, is a widely adopted security [protocol](https://www.cloudflare.com/learning/network-layer/what-is-a-protocol/) designed to facilitate privacy and data security for communications over the Internet. A primary use case of TLS is encrypting the communication between web applications and servers, such as web browsers loading a website.


**What is SSL?**

SSL, or Secure Sockets Layer, is an [encryption](https://www.cloudflare.com/learning/ssl/what-is-encryption/)-based Internet security [protocol](https://www.cloudflare.com/learning/network-layer/what-is-a-protocol/)

[](https://www.cloudflare.com/en-ca/learning/ssl/what-is-ssl/)


**What is the difference between TLS and SSL?**

TLS evolved from a previous encryption protocol called Secure Sockets Layer ([SSL](https://www.cloudflare.com/learning/ssl/what-is-ssl/)), which was developed by Netscape. TLS version 1.0 actually began development as SSL version 3.1, but the name of the protocol was changed before publication in order to indicate that it was no longer associated with Netscape. Because of this history, the terms TLS and SSL are sometimes used interchangeably.
