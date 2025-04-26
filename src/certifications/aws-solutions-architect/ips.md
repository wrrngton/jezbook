# IPs

## IPV4 vs IPV6

IPV4 are "classic" IP addresses, but they are running out, so the internet is moving to IPV6. 

The IPV4 address we get with our EC2 instance will be enough. 

The format is as follows: [0-255].[0-255].[0-255].[0-255] allowing for 3.6b IPV4 addresses

## Private VS public IPs

Public IPs allow servers to be accessed via the internet. Whereas private IPs can only be accessed internally from the same network. Private networks can interact with the WWW using an internet gateway (proxy)

Private IPs can repeat, whereas public IPs cannot. 

## Elastic IPs

AWS allows Elastic IPs, which are static IP addresses you can keep and then port between services. So the IP remains static and can be applied to different services. AWS gives you 5 of these. Each can only be attached to an instance one at a time. 

> Avoid elastic IPs, instead register a DNS name to a random public IP. Or use a load balancer. 


