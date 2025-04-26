## SSL / TLS Basics

SSL refers to Secure Socket Layer and is a way to encrypt network traffic that is in flight.

For AWS it refers to encrypting traffic between the client and the load balancer. Traffic between the load balancer and instances are handled over plain HTTP.

The S in HTTPS refers to 'secure', which means the traffic is using SSL.    

Nowadays, traffic is encrypted using TLS (Transport Layer Security), which is a newer version of SSL, but people still refer to it as SSL.

SSl certs are issued by a Certificate Authority (CA) and have an expiration date. 

![](assets/ssl.png)

## Load Balancer and SSL

- LB uses an X.509 Certificate
- ACM (AWS Certificate Manager) manages certs
- You must set a default SSL cert
- Clients can use SNI (Server Name Indication) to specify the hostname they reach


## Server Name Indication (SNI)

- This helps manage multiple SSLs on one Server
- Client must indicate server hostname to get the right SSL

![](assets/sni.png)

## Load Balancer Support

- *CLB*: supports 1 SSL
- *ALB*: supports multiple with SNI
- *NLB*: support multiple with SNI
