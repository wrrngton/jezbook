# EC2 Placement Groups

Placement groups allow you to define where your EC2 instances are deployed on AWS infrastructure. 

A placement group is either:

1. *A cluster*: puts your instances in a low latency group in the same AZ. This helps with networking as instances are close to one another. Drawback is if the AZ fails, they all fail. **use case**: Good for big data jobs, apps that need low latency between instances.
2. *Spread*: Think of this as opposite to clusters. Each instance is on different hardware across different AZs. This means reduced failure risk. Limited to 7 AZ per placement group. **Use case**: maximum high availability.
3. *Partition*: spreads instances across different partitions within an AZ. Each partition represents a rack in AWS. Instances are distributed across different hardware racks and AZs in same region. **use cases**: Big data application, which are petition aware. 

![placement groups](assets/glb.png)



