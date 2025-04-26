# EC2 storage options

Storage options for EC2 instances 

## EBS Volume

Elastic Block Store - network drive. Allows for data persistence.

Can only be mounted to 1 instance at a time. It's bound to AZ. But you can attach more than one volume to an instance

> Like a network USB stick. It's not a physical drive, it uses the network, so there is latency. 

You can move it, but you've gotta snapshot the volume.

You can decide to terminate the EBS volume on instance termination

## EBS Snapshot

- You can snapshot your volumes to act as a backup.  
- Recommended to detach volume
- Can copy across AZs - allowing volume restoration in another AZ
- Copying to archive tier is much cheaper, but restoration is longer
- Snapshot deletions can be recovered from a recycle bin
- Fast Snapshot Restore (FSR) helps with latency on restoration
- Can also create other volumes from existing snapshots, which can be in a different AZ

## EBS Volume Types

There are 6 types of EBS volume types

- GP2 / GP3 (SSD): perf/price balance
- io1 / io2 Block Express (SSD): High perf for low latency and high throughput
- st 1 (HDD): Low cost, frequent access, throughput intensive workloads
- sc 1 (HDD): Lowest cost for less frequent workloads

Characterised by SIZE | THROUGHPUT | IOPS (I/O Ops per sec)

> Only GP2/GP3 and io1 / io2 can be used at boot volumes

### General purpose SSD (gp2/gp3)

- Cost effective, low latency
- System boots
- 1GiB - 16 TiB
- Gp3: 2k - 16k IOPS & 125 MiB/s - 1k MiB/s 
- Gp2: IOPS up to 16k. volume size and IOPS are linked 

### Provisioned IOPS volumes (io1/1o2)

- Critical business apps
- Apps that nmeed more than 16k IOPS
- Great for DB workloads
- io1: 4gb - 16tb max 64k IOPS
- io2: 4gb - 64gb - max 256k IOPS

### HDD (st1/sc1)

- Can't be boot volumes
- 125gb - 16tb
- Throughpout optimised (st 1) - good for big data
- Infrequent access (low cost) - sc 1

Best resource: https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volume-types.html

### EBS multi attach

For io1/2 families you can attach same EBS volume to multiple EC2 instances in the same AZ.

This is good for high availability and concurrent writes. 

> Only good for one AZ and 16 EC2 instances at the same time

## EBS Encryption

- Data encrypted at rest
- In flight encryption
- Snapshot encryption
- Uses KMs (AES-256). 

## Elastic file system (EFS)

Allows for a network file system that allows multiple AZ instances to connect to the EFS through a security group.

![efs](assets/efs.png)

Use cases: content management, web serving, data sharing, Wordpress. Only Linux compatible (POSIX) system and scales automatically. 

It has different perf modes:

- General purpose
- Throughput mode for Max I/O

And storage classes:

- standard
- infrequent access
- archive
