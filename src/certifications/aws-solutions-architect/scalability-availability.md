## Vertical vs horizontal scalability

### Vertical

This means adding more power to existing instance. For example turning EC2 instance from a T2 to a T3 instance - so adding more compute.

- There are hardware limits to how much this can scale
- Common use case fo non-distributed systems like a database
- RDS and ElastiCache can scale vertically

> AWS terms: scale up / down

### Horizontal 

Involves adding more instances for the application. Instead of increasing capacity of existing machines, we add new machines. 

So going from one machine to two machines for the same application is an example of horizontal scaling.

- Common use case for web apps
- Implies distributed systems

> AWS terms: scale out / in 

## Availability

This refers to application uptime. It usually involves running same application across multiple AZs so that if one data centre crashes, your app will be active in another so there is no downtime.

AWS examples:

- Auto Scaling Group multi AZ
- Load Balancer multi AZ
