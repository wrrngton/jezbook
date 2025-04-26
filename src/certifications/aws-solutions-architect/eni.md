# Elastic Netowrk Interfaces (ENI)

https://aws.amazon.com/blogs/aws/new-elastic-network-interfaces-in-the-virtual-private-cloud/

ENIs are a virtual network card that give EC2 instances network access.

Each ENI can have:

1. a private iPV4 (or more)
2. one elastic IPv4
3. one public IPv4
4. security groups
5. a MAC address

They are AZ bound and can be moved to other EC2 instances. 

>  Network cards are a hardware component that allow computers to connect to networks
> ENIs are outside of the EC2 instance, although they affect them they just aren't shared by the instance

Each EC2 instance has one network interface.

Moving an ENI between instances allows for quick failover. 
