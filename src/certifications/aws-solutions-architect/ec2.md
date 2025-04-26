# EC2

An EC2 instance is just a virtual machine that you hire. It stands for **Elastic Compute Cloud** and is infrastructure as a service.

You can also:

- Store data on virtual drives
- Distribute load across machines
- Scale services

You can choose what you want your virtual machine to be and its power, including CPU, RAM, networking capabilities etc. You can also choose between Mac, Linux and Windows machines.

## Bootstrapping

What the machine does at launch can be controlled using bootstrapping scripts

## EC2 instance types

https://aws.amazon.com/ec2/instance-types/
https://instances.vantage.sh/
There are different types of EC2 instances, designed for different purposes. You can find them above.

Using _m5.2xlarge_ as an example, the naming convention is:

- **m**: instance class, in this case m means general purpose
- **5**: generation (AWS improves gens over time)
- **2xlarge**: size, so the CPU and processing power

### General purpose

### Compute optimized

High performance with good CPU. Examples are of the **C** name

### Memory optimized

High RAM. High performance for databases, cache stores, big unstructured data. An example are the **R** instances

### Storage optimised

Good for high, sequential read and write access to large data sets.

Examples:

- Databases
- Cache for in memory dbs
- Online transactioning systems
- Distributed filed systems

## EC2 instance firewalls

You can control who can access the EC2 instance and how your EC2 instance interacts with the internet using security groups.

### Security groups

Security groups contain _allow_ rules that can reference IPs or groups that can access instances. Therefore they act as a firewall on EC2 instance, by regulating:

- Port access
- Authorised IP ranges
- Inbound traffic
- Outbound traffic

![](../../assets/sec-groups.png)

Groups:

- Can be attached to multiple insrtances
- Locked down to region/VPC combination
- Live outside Ec2 instances - they are their own standalone thing
- timeouts usually mean security group issue
- inbound traffic is blocked by default
- outbound traffic is authorised by default
- you can attach security groups to more than one instance

## Ports

These are the ports you must know:

![ports](assets/nlb.png)

## SSH

SSH is a CLI that can be used on Mac and Linux and Windows V > 10 (or PuTTy) below V10

EC2 instance connect also allows connection to your EC2 instances.

AWS gives you the user EC2-user already, so the SSH command to login to the server has the following components:

1. ssh ec2-user@<YOUR-PUIBLIC-IP-ADDRESS>
2. you need to use the .pem file (which contains a private key) using the -i flag (identity file flag)

The full command: `ssh -i EC2Tutorial.pem ec2-user@44.201.88.145`

> With all EC2 instances, if you experience a timeout, either when using SSH or otherwise, it's usually a security group issue

## EC2 instance connect

You can do all this in the browser, without managing keys by going to SSH Instance Connect.

## IAM Roles for EC2 instances

You should always manage EC2 instance access through IAM roles, not by adding your credentials directly into the instance using `aws configure` as this data can be accessed by other users on the instance. So instead, attach an IAM Role to the EC2 instance and manage service access through role policies. 

## EC2 pricing

There is different EC2 pricing, which you can see below depending on what's needed:

[ex2pricing](assets/sni.png)

## IPV4 vs 6

AWS will charge for IPV6 ip addresses that go over 750 hours a month. So if you have more than 1 ip address it's likely you will incur costs. 

## EC2 controls

There are a few ways to control the instances:

- **Stop**: data is kept intact for next start. OS has to boot and can take time
- **Terminate**: data and setup is lost
- **Hibernate**: RAM is preserved, OS is not stopped / restarted. RAM state is written to file in volume. 

> Hibernation helps for saving RAM state, boot up fast and want long running processes. Can be no longer than 60 days. 
