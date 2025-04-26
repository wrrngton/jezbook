# Amazon Machine Image (AMI)

AMIs are customisations of an EC2 instance.

It's basically a snapshot of an instance that can be used to launch new, customised EC2 instances. This helps with faster boot times. 

So far we have been launching using Amazon's own Linux AMIs. But we can:

- Create our own AMIs
- Used 3rd party vendor AMIs (can cost)

This allows for the following:

- Create an instance in one AZ
- Create AMI from that instance
- Launch a new instance from that AMI in another AZ


