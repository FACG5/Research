# HTTP vs HTTPS
> HTTP : HyperText Transfer Protocol.

> HTTPs :Hyper Text Transfer Protocol Secure.

![alt text](https://www.instantssl.com/images/http-vs-https.png)

### How does HTTPS work?
HTTPS takes the well-known and understood HTTP protocol and simply layers a SSL/TLS **encryption layer on top of it.**


+ It verifying that you are talking directly to the server that you think you are talking to.

+ Ensuring that only the server can read what you send it and only you can read what it sends back.

**Servers and clients still speak exactly the same HTTP to each other,** but over a secure SSL encrypted connection.

# HTTP - No protection from attackers

![](https://cascadingmedia.com/assets/images/insites/2015/01/https-everywhere/http-active-attacker-7a91cf87.png)

# HTTPS - Protects you from attackers

![](https://cascadingmedia.com/assets/images/insites/2015/01/https-everywhere/https-active-attacker-ed110ae9.png)

### What are TLS/SSL certificates?

 ***SSL*** *(Secure Sockets Layer)* - it's the technology for keeping an internet connection secure and safeguarding any sensitive data.

 > + SSL certificates have a key pair: a public and a private key.

  ***These keys work together to establish an encrypted connection.*** The certificate also contains what is called the “subject,” which is the identity of the certificate/website owner.

 + To get a certificate, you must create a Certificate Signing Request (CSR) on your server. This process creates a private key and public key on your server. The CSR data file that you send to the SSL Certificate issuer (called a Certificate Authority or CA) contains the public key. ***The CA uses the CSR data file to create a data structure to match your private key without compromising the key itself.*** The CA never sees the private key.

> + TLS*** *(Transport Layer Security)* - an updated, more secure version of SSL.

### Why is this important to implement in your projects?

You should always protect all of your websites with HTTPS!

+ HTTPS is a requirement for many new browser features, **particularly those required for progressive web apps.**

+ HTTPS protects the privacy and security of your users

  **it prevents intruders** from being able to passively listen to communications between your websites and your users.

+ SSL is the backbone of our secure Internet and it protects your sensitive information as it travels across the world's computer networks.

+ SSL Encrypts Sensitive Information:
**The primary reason why SSL** is used is to keep sensitive information sent across the Internet encrypted so that only the intended recipient can understand it.

+ SSL Provides Authentication:
**This means** you can be sure that you are sending information to the right server and not to an imposter trying to steal your information.


>> BY Kan'an Lubna and Asala  :smile:s